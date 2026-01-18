# Python 201 – Pandas Avançado

## Introdução

Após dominar os conceitos básicos do Pandas, é fundamental aprender operações mais avançadas,
muito utilizadas em análises reais de dados e em projetos de Ciência de Dados.

Neste post, abordaremos:
- Manipulação avançada de DataFrames
- Agrupamentos e agregações
- Merge e concatenação
- Aplicação de funções
- Trabalhando com datas

---

## Revisão rápida: carregando os dados

```python
import pandas as pd

df = pd.read_csv("datasets/vendas.csv")
df.head()
````

---

## Operações com múltiplas colunas

Criando colunas a partir de operações:

```python
df["valor_total"] = df["quantidade"] * df["valor_unitario"]
```

Aplicando múltiplas condições:

```python
df.loc[
    (df["quantidade"] > 5) & (df["categoria"] == "Eletrônicos"),
    ["produto", "valor_total"]
]
```

---

## GroupBy e agregações

Uma das operações mais importantes em Pandas.

```python
df.groupby("categoria")["valor_total"].sum()
```

Múltiplas agregações:

```python
df.groupby("categoria").agg(
    total_vendas=("valor_total", "sum"),
    media_vendas=("valor_total", "mean"),
    quantidade_total=("quantidade", "sum")
)
```

---

## Merge (JOINs no Pandas)

Similar aos JOINs do SQL.

### Exemplo de DataFrames

```python
clientes = pd.read_csv("datasets/clientes.csv")
vendas = pd.read_csv("datasets/vendas.csv")
```

### Inner Join

```python
df_merge = pd.merge(
    vendas,
    clientes,
    on="cliente_id",
    how="inner"
)
```

### Left Join

```python
df_merge = pd.merge(
    vendas,
    clientes,
    on="cliente_id",
    how="left"
)
```

---

## Concatenação de DataFrames

```python
df_2023 = pd.read_csv("datasets/vendas_2023.csv")
df_2024 = pd.read_csv("datasets/vendas_2024.csv")

df_total = pd.concat([df_2023, df_2024])
```

---

## Apply e funções lambda

Aplicando funções customizadas:

```python
df["categoria_tamanho"] = df["categoria"].apply(
    lambda x: "Curta" if len(x) <= 10 else "Longa"
)
```

Usando funções próprias:

```python
def classificar_valor(valor):
    if valor >= 1000:
        return "Alto"
    elif valor >= 500:
        return "Médio"
    else:
        return "Baixo"

df["nivel_venda"] = df["valor_total"].apply(classificar_valor)
```

---

## Trabalhando com datas

Convertendo colunas para datetime:

```python
df["data"] = pd.to_datetime(df["data"])
```

Extraindo informações:

```python
df["ano"] = df["data"].dt.year
df["mes"] = df["data"].dt.month
df["dia"] = df["data"].dt.day
```

Filtrando por período:

```python
df[df["data"] >= "2024-01-01"]
```

---

## Ordenação avançada

```python
df.sort_values(
    by=["ano", "valor_total"],
    ascending=[True, False]
)
```

---

## Resetando e manipulando índices

```python
df.reset_index(drop=True, inplace=True)
```

Definindo índice:

```python
df.set_index("data", inplace=True)
```

---

## Performance e boas práticas

* Prefira operações vetorizadas
* Evite loops (`for`) em DataFrames grandes
* Use `.copy()` quando necessário
* Entenda o impacto de `inplace=True`

---

## Erros comuns em Pandas

* `SettingWithCopyWarning`
* Tipos incorretos (`object` vs `int`)
* Merge com chaves duplicadas
* Alterar dados sem validar

---

## Conclusão

Neste post você aprendeu:

* GroupBy e agregações avançadas
* Merge e concatenação
* Uso de apply e funções lambda
* Manipulação de datas
* Boas práticas de performance

Esses conceitos são amplamente utilizados em projetos reais de Ciência de Dados.
