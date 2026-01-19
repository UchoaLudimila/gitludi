# Python 103 – Visualização de Dados com Matplotlib

## Introdução

Visualizar dados é uma das etapas mais importantes da análise de dados.
Gráficos ajudam a:
- Identificar padrões
- Encontrar outliers
- Comparar valores
- Comunicar resultados

O **Matplotlib** é a biblioteca base de visualização em Python
e serve como fundação para outras bibliotecas como Seaborn.

---

## Importando o Matplotlib

O módulo mais usado é o `pyplot`, geralmente importado como `plt`:

```python
import matplotlib.pyplot as plt
````

---

## Gráfico de linha (Line Plot)

Usado para mostrar evolução ou tendência ao longo do tempo.

```python
x = [1, 2, 3, 4, 5]
y = [10, 15, 20, 25, 30]

plt.plot(x, y)
plt.show()
```

---

## Personalizando o gráfico

```python
plt.plot(x, y, color="blue", linestyle="--", marker="o")
plt.title("Gráfico de Linha")
plt.xlabel("Eixo X")
plt.ylabel("Eixo Y")
plt.show()
```

---

## Gráfico de barras (Bar Plot)

Muito usado para comparar categorias.

```python
categorias = ["A", "B", "C"]
valores = [10, 20, 15]

plt.bar(categorias, valores)
plt.show()
```

---

## Gráfico de barras horizontal

```python
plt.barh(categorias, valores)
plt.show()
```

---

## Gráfico de dispersão (Scatter Plot)

Usado para analisar relação entre duas variáveis.

```python
x = [1, 2, 3, 4, 5]
y = [5, 7, 8, 10, 12]

plt.scatter(x, y)
plt.show()
```

---

## Histograma

Usado para analisar a distribuição dos dados.

```python
dados = [10, 12, 15, 18, 20, 22, 25]

plt.hist(dados, bins=5)
plt.show()
```

---

## Subplots (múltiplos gráficos)

```python
fig, ax = plt.subplots(1, 2, figsize=(10, 4))

ax[0].plot(x, y)
ax[0].set_title("Linha")

ax[1].bar(categorias, valores)
ax[1].set_title("Barras")

plt.show()
```

---

## Trabalhando com NumPy

```python
import numpy as np

x = np.arange(0, 10)
y = x ** 2

plt.plot(x, y)
plt.show()
```

---

## Estilos de gráficos

Visualizando estilos disponíveis:

```python
plt.style.available
```

Usando um estilo:

```python
plt.style.use("ggplot")
```

---

## Salvando gráficos

```python
plt.plot(x, y)
plt.savefig("grafico.png")
plt.show()
```

---

## Boas práticas de visualização

* Sempre coloque título
* Nomeie os eixos
* Evite gráficos poluídos
* Use cores com cuidado
* Escolha o gráfico adequado ao dado

---

## Aplicação em Ciência de Dados

Exemplo simples de análise exploratória:

```python
import pandas as pd

df = pd.read_csv("datasets/vendas.csv")

plt.hist(df["valor_total"], bins=10)
plt.title("Distribuição do Valor Total")
plt.xlabel("Valor")
plt.ylabel("Frequência")
plt.show()
```

---

## Erros comuns com Matplotlib

* Esquecer o `plt.show()`
* Criar gráficos sem rótulos
* Usar cores excessivas
* Não ajustar o tamanho da figura

---

## Conclusão

Neste post você aprendeu:

* Conceitos básicos de visualização
* Gráficos de linha, barra, dispersão e histograma
* Personalização de gráficos
* Boas práticas
