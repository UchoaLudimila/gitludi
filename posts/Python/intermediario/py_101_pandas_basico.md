# Python 101 – Introdução ao Pandas

## O que é Pandas?

Pandas é uma biblioteca Python amplamente utilizada em Ciência de Dados para:
- Manipulação de dados tabulares
- Limpeza de dados
- Análise exploratória
- Leitura e escrita de arquivos (CSV, Excel, etc.)

O Pandas trabalha principalmente com duas estruturas:
- **Series** (vetores unidimensionais)
- **DataFrame** (tabelas bidimensionais)

---

## Importando a biblioteca Pandas

O padrão é importar o Pandas com o apelido `pd`:

```python
import pandas as pd
````

---

## Series

Uma `Series` é uma estrutura unidimensional, semelhante a uma coluna de uma tabela.

```python
idades = pd.Series([25, 30, 22, 40])
idades
```

---

## DataFrame

Um `DataFrame` é uma tabela, composta por linhas e colunas.

```python
dados = {
    "nome": ["Ana", "Bruno", "Carlos"],
    "idade": [25, 30, 22],
    "cidade": ["SP", "RJ", "BH"]
}

df = pd.DataFrame(dados)
df
```

---

## Lendo arquivos CSV

Uma das tarefas mais comuns em análise de dados é ler arquivos CSV.

```python
df = pd.read_csv("datasets/vendas.csv")
```

Parâmetros comuns:

* `sep` → separador
* `encoding` → codificação
* `decimal` → separador decimal

```python
df = pd.read_csv("datasets/vendas.csv", sep=",", encoding="utf-8")
```

---

## Visualizando os dados

### Primeiras linhas

```python
df.head()
```

### Últimas linhas

```python
df.tail()
```

### Informações gerais

```python
df.info()
```

### Estatísticas descritivas

```python
df.describe()
```

---

## Selecionando colunas

```python
df["nome"]
```

Selecionando múltiplas colunas:

```python
df[["nome", "idade"]]
```

---

## Selecionando linhas

### Usando índice

```python
df.loc[0]
```

### Usando posição

```python
df.iloc[0]
```

---

## Filtros (condições)

Exemplo: pessoas com idade maior que 25.

```python
df[df["idade"] > 25]
```

Filtros combinados:

```python
df[(df["idade"] > 25) & (df["cidade"] == "SP")]
```

---

## Criando novas colunas

```python
df["idade_ano_seguinte"] = df["idade"] + 1
```

---

## Renomeando colunas

```python
df.rename(columns={"nome": "nome_cliente"}, inplace=True)
```

---

## Ordenando dados

```python
df.sort_values("idade")
```

Ordem decrescente:

```python
df.sort_values("idade", ascending=False)
```

---

## Lidando com valores nulos

### Verificando valores nulos

```python
df.isnull().sum()
```

### Removendo valores nulos

```python
df.dropna()
```

### Preenchendo valores nulos

```python
df.fillna(0)
```

---

## Salvando dados

```python
df.to_csv("datasets/arquivo_tratado.csv", index=False)
```

---

## Boas práticas com Pandas

* Explore os dados antes de analisá-los
* Use nomes de colunas padronizados
* Evite modificar dados sem entender o impacto
* Trabalhe com cópias quando necessário

---

## Conclusão

Neste post você aprendeu:

* O que é Pandas
* Series e DataFrame
* Leitura de arquivos CSV
* Operações básicas de manipulação de dados
