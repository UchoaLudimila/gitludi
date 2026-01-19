# Python 104 – Visualização de Dados com Seaborn

## Introdução

O **Seaborn** é uma biblioteca Python baseada em Matplotlib que permite:
- Criar gráficos estatísticos facilmente
- Tornar visualizações mais elegantes
- Trabalhar bem com DataFrames do Pandas

Seaborn é muito usado em Ciência de Dados para análise exploratória (EDA).

---

## Instalando o Seaborn

Se ainda não tiver instalado:

```bash
pip install seaborn
````

Importando a biblioteca:

```python
import seaborn as sns
import matplotlib.pyplot as plt
```

---

## Dataset de exemplo

O Seaborn já possui datasets de teste, como `tips`:

```python
tips = sns.load_dataset("tips")
tips.head()
```

---

## Gráfico de dispersão (scatterplot)

```python
sns.scatterplot(data=tips, x="total_bill", y="tip")
plt.show()
```

Adicionando cor por categoria:

```python
sns.scatterplot(data=tips, x="total_bill", y="tip", hue="sex")
plt.show()
```

---

## Gráfico de linhas (lineplot)

```python
sns.lineplot(data=tips, x="size", y="tip")
plt.show()
```

---

## Gráfico de barras (barplot)

```python
sns.barplot(data=tips, x="day", y="total_bill")
plt.show()
```

---

## Boxplot (diagrama de caixa)

Mostra mediana, quartis e outliers.

```python
sns.boxplot(data=tips, x="day", y="total_bill", hue="sex")
plt.show()
```

---

## Histograma / Distribuição (histplot / displot)

```python
sns.histplot(data=tips, x="total_bill", bins=10, kde=True)
plt.show()
```

* `kde=True` adiciona uma curva de densidade

---

## Gráfico de violino (violinplot)

Combina boxplot com distribuição dos dados:

```python
sns.violinplot(data=tips, x="day", y="total_bill", hue="sex", split=True)
plt.show()
```

---

## Gráfico de correlação (heatmap)

Útil para analisar relação entre variáveis numéricas:

```python
corr = tips.corr()
sns.heatmap(corr, annot=True, cmap="coolwarm")
plt.show()
```

---

## Pairplot (gráfico de pares)

Analisa várias combinações de variáveis numéricas:

```python
sns.pairplot(tips, hue="sex")
plt.show()
```

---

## Estilos e temas

```python
sns.set_style("whitegrid")  # outros: darkgrid, white, ticks
sns.set_palette("Set2")      # paleta de cores
```

---

## Integração com Pandas

Seaborn trabalha diretamente com DataFrames:

```python
import pandas as pd

df = pd.DataFrame({
    "x": [1,2,3,4,5],
    "y": [5,4,3,2,1],
    "categoria": ["A","B","A","B","A"]
})

sns.barplot(data=df, x="x", y="y", hue="categoria")
plt.show()
```

---

## Boas práticas

* Escolha o gráfico certo para cada tipo de dado
* Use cores consistentes
* Adicione títulos e rótulos
* Prefira gráficos claros e simples

---

## Aplicação em Ciência de Dados

Seaborn é muito usado para **EDA (Exploratory Data Analysis)**:

* Comparar categorias
* Visualizar distribuições
* Detectar outliers
* Explorar relações entre variáveis

Exemplo rápido com `tips`:

```python
sns.boxplot(data=tips, x="day", y="total_bill", hue="sex")
plt.title("Distribuição do valor total por dia e sexo")
plt.show()
```

---

## Conclusão

Neste post você aprendeu:

* Como criar gráficos com Seaborn
* Scatterplot, lineplot, barplot, boxplot, violinplot, histplot
* Pairplot e heatmap
* Personalização e integração com Pandas
