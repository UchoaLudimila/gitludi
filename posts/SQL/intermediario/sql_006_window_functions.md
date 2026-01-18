# 🪟 Operadores de Janela (Window Functions) em SQL

## 📌 O que são Window Functions?
As *funções de janela* permitem realizar **cálculos sobre um conjunto de linhas relacionadas**, mantendo a granularidade dos dados.  
Diferente das funções agregadas (`SUM`, `AVG`, etc.), que agrupam linhas, as Window Functions **retornam um valor para cada linha individual**, considerando uma “janela” de dados definida com `OVER()`.

---

## 🧠 Principais usos
- **Rankings e ordenações**: `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`
- **Cálculos acumulados**: `SUM()`, `AVG()` com `OVER()`
- **Comparações entre linhas**: `LAG()`, `LEAD()`
- **Percentis e distribuição**: `NTILE()`, `PERCENT_RANK()`

---

## 🧪 Exemplos práticos

### 1. `ROW_NUMBER()`
```sql
SELECT 
  nome_funcionario,
  departamento,
  salario,
  ROW_NUMBER() OVER (PARTITION BY departamento ORDER BY salario DESC) AS ranking_salario
FROM funcionarios;
```

### 2. Cálculo acumulado com `SUM()`
```sql
SELECT 
  mes,
  vendas,
  SUM(vendas) OVER (ORDER BY mes) AS vendas_acumuladas
FROM relatorio_vendas;
```

### 3. Comparando linhas com `LAG()` e `LEAD()`
```sql
SELECT 
  mes,
  vendas,
  LAG(vendas, 1) OVER (ORDER BY mes) AS vendas_mes_anterior,
  LEAD(vendas, 1) OVER (ORDER BY mes) AS vendas_mes_seguinte
FROM relatorio_vendas;
```

### 4. Distribuição em grupos com `NTILE()`
```sql
SELECT 
  nome_funcionario,
  salario,
  NTILE(4) OVER (ORDER BY salario DESC) AS quartil_salario
FROM funcionarios;
```

### 5. Ranking com `RANK()` vs `DENSE_RANK()`
```sql
SELECT 
  nome_funcionario,
  departamento,
  salario,
  RANK() OVER (PARTITION BY departamento ORDER BY salario DESC) AS rank_salario,
  DENSE_RANK() OVER (PARTITION BY departamento ORDER BY salario DESC) AS dense_rank_salario
FROM funcionarios;
```

---

## 🔄 Comparação rápida

| Função         | Uso principal                  | Exemplo prático                  |
|----------------|--------------------------------|----------------------------------|
| `ROW_NUMBER()` | Sequência única                | Numerar linhas                   |
| `RANK()`       | Ranking com empates            | Classificação de salários        |
| `DENSE_RANK()` | Ranking sem pular números      | Classificação contínua           |
| `LAG()`        | Valor da linha anterior        | Comparar vendas mês a mês        |
| `LEAD()`       | Valor da linha seguinte        | Previsão/planejamento            |
| `NTILE(n)`     | Divisão em grupos estatísticos | Quartis, decis, percentis        |

---

## ⚡ Boas práticas
- Sempre combine `PARTITION BY` para segmentar dados.  
- Use `ORDER BY` dentro do `OVER()` para garantir consistência.  
- Prefira CTEs (`WITH`) para organizar consultas complexas.  
- Evite misturar funções de janela diretamente em filtros (`WHERE`) — use subqueries ou CTEs.

---

# 🧩 Desafio: Analisando Vendas com Window Functions

## 📊 Dataset fictício
Tabela `vendas`:

| mes   | vendas |
|-------|--------|
| Jan   | 1000   |
| Fev   | 1200   |
| Mar   | 900    |
| Abr   | 1500   |
| Mai   | 1100   |

---

## 🎯 Objetivo
Mostrar:
1. O valor de vendas do mês  
2. O acumulado até aquele mês  
3. A diferença em relação ao mês anterior  

---

## 💻 Solução
```sql
SELECT 
  mes,
  vendas,
  SUM(vendas) OVER (ORDER BY mes) AS vendas_acumuladas,
  vendas - LAG(vendas, 1) OVER (ORDER BY mes) AS diferenca_mes_anterior
FROM vendas;
```

### Resultado esperado
| mes   | vendas | vendas_acumuladas | diferenca_mes_anterior |
|-------|--------|-------------------|------------------------|
| Jan   | 1000   | 1000              | NULL                   |
| Fev   | 1200   | 2200              | 200                    |
| Mar   | 900    | 3100              | -300                   |
| Abr   | 1500   | 4600              | 600                    |
| Mai   | 1100   | 5700              | -400                   |

---

# 📊 Média Móvel de 3 Meses

## 💻 Consulta
```sql
SELECT 
  mes,
  vendas,
  AVG(vendas) OVER (
    ORDER BY mes 
    ROWS BETWEEN 2 PRECEDING AND CURRENT ROW
  ) AS media_movel_3_meses
FROM vendas;
```

### Resultado esperado
| mes   | vendas | media_movel_3_meses |
|-------|--------|----------------------|
| Jan   | 1000   | 1000.0               |
| Fev   | 1200   | 1100.0               |
| Mar   | 900    | 1033.3               |
| Abr   | 1500   | 1200.0               |
| Mai   | 1100   | 1166.7               |

---

## 🚀 Desafio
> "Você consegue adaptar essa consulta para calcular também a **média móvel de 6 meses**?"
