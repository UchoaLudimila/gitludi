# Python 102 – Introdução ao NumPy

## O que é NumPy?

NumPy (Numerical Python) é uma biblioteca fundamental para:
- Computação numérica
- Operações matemáticas eficientes
- Manipulação de arrays multidimensionais

Ela é a base de bibliotecas como:
- Pandas
- SciPy
- Scikit-learn

---

## Importando o NumPy

O padrão é importar o NumPy com o apelido `np`:

```python
import numpy as np
````

---

## Arrays NumPy

O principal objeto do NumPy é o **array** (`ndarray`).

```python
array = np.array([1, 2, 3, 4, 5])
array
```

---

## Diferença entre list e array NumPy

### Lista Python

```python
lista = [1, 2, 3]
lista * 2
```

Resultado:

```python
[1, 2, 3, 1, 2, 3]
```

### Array NumPy

```python
array = np.array([1, 2, 3])
array * 2
```

Resultado:

```python
[2 4 6]
```

---

## Criando arrays comuns

### Array de zeros

```python
np.zeros(5)
```

---

### Array de uns

```python
np.ones(5)
```

---

### Array com intervalo

```python
np.arange(0, 10, 2)
```

---

### Array com valores igualmente espaçados

```python
np.linspace(0, 1, 5)
```

---

## Tipo de dados (dtype)

```python
array = np.array([1, 2, 3], dtype=float)
array
```

Verificando o tipo:

```python
array.dtype
```

---

## Dimensões e forma do array

```python
array = np.array([[1, 2, 3], [4, 5, 6]])

array.ndim    # número de dimensões
array.shape   # linhas e colunas
array.size    # total de elementos
```

---

## Acessando elementos

```python
array = np.array([10, 20, 30, 40])

array[0]
array[-1]
```

---

## Slicing (fatiamento)

```python
array[1:3]
```

---

## Operações matemáticas

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

a + b
a - b
a * b
a / b
```

---

## Funções matemáticas do NumPy

```python
np.sum(a)
np.mean(a)
np.max(a)
np.min(a)
np.std(a)
```

---

## Operações com matrizes

```python
matriz = np.array([[1, 2], [3, 4]])

matriz.T          # transposta
np.dot(matriz, matriz)
```

---

## Boolean indexing (filtro)

```python
valores = np.array([10, 20, 30, 40])

valores[valores > 20]
```

---

## Trabalhando com valores aleatórios

```python
np.random.rand(5)        # valores entre 0 e 1
np.random.randint(1, 10, 5)
```

Definindo semente (reprodutibilidade):

```python
np.random.seed(42)
```

---

## Aplicação em Ciência de Dados

* Normalização de dados
* Cálculos estatísticos
* Simulações
* Base para operações em Pandas

Exemplo simples:

```python
dados = np.array([100, 200, 300])
media = np.mean(dados)
```

---

## Performance: por que usar NumPy?

* Operações vetorizadas
* Código mais rápido que loops Python
* Uso eficiente de memória

Exemplo:

```python
# Evite
resultado = []
for i in range(1000):
    resultado.append(i * 2)

# Prefira
resultado = np.arange(1000) * 2
```

---

## Boas práticas

* Prefira arrays NumPy para cálculos numéricos
* Evite misturar listas e arrays sem necessidade
* Use operações vetorizadas
* Verifique o `dtype` dos arrays

---

## Erros comuns com NumPy

* Confundir shape do array
* Erros de broadcast
* Usar loops em vez de vetorização
* Misturar tipos incompatíveis

---

## Conclusão

Neste post você aprendeu:

* O que é NumPy
* Criação e manipulação de arrays
* Operações matemáticas
* Filtros e operações vetorizadas
