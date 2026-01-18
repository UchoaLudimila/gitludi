## 📄 Estrutura do conteúdo sobre Funções Agregadas

### 🔹 1. Introdução
- O que são: funções que **realizam cálculos sobre um conjunto de registros** e retornam um único valor.  
- Por que são importantes: permitem análises rápidas, como contar registros, calcular médias ou somar valores.  

---

### 🔹 2. Principais funções

#### **COUNT**
- Conta o número de registros.  
```sql
SELECT COUNT(*) AS total_clientes
FROM clientes;
```
👉 Retorna quantos clientes existem na tabela.

---

#### **SUM**
- Soma os valores de uma coluna numérica.  
```sql
SELECT SUM(valor) AS total_vendas
FROM pedidos;
```
👉 Retorna o valor total das vendas.

---

#### **AVG**
- Calcula a média dos valores.  
```sql
SELECT AVG(valor) AS media_vendas
FROM pedidos;
```
👉 Retorna a média dos valores dos pedidos.

---

#### **MIN e MAX**
- Retorna o menor e o maior valor.  
```sql
SELECT MIN(valor) AS menor_pedido, MAX(valor) AS maior_pedido
FROM pedidos;
```
👉 Mostra o menor e o maior valor de pedido.

---

### 🔹 3. Uso com GROUP BY
- As funções agregadas ficam ainda mais poderosas quando combinadas com **GROUP BY**, permitindo calcular métricas por categoria.  

Exemplo:  
```sql
SELECT cliente_id, SUM(valor) AS total_por_cliente
FROM pedidos
GROUP BY cliente_id;
```
👉 Retorna o total de vendas por cliente.

---

### 🔹 4. Dica final
- Sempre use **alias** (`AS nome_coluna`) para deixar os resultados mais claros.  
- Funções agregadas são fundamentais para relatórios e dashboards.  

---
