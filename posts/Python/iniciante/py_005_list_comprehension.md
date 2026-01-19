# Python 005 – List Comprehension

## Introdução

List Comprehension é uma forma **mais curta, legível e Pythonic**
de criar listas a partir de outras sequências.

É muito utilizada em Ciência de Dados para:
- Transformar dados
- Filtrar valores
- Aplicar regras simples
- Substituir loops `for` tradicionais

---

## Estrutura básica

A estrutura geral é:

```python
[expressao for item in iteravel]
````

Exemplo usando `for` tradicional:

```python
numeros = [1, 2, 3, 4]
quadrados = []

for n in numeros:
    quadrados.append(n ** 2)
```

Usando List Comprehension:

```python
quadrados = [n ** 2 for n in numeros]
```

---

## List Comprehension com condição

Estrutura:

```python
[expressao for item in iteravel if condicao]
```

Exemplo: números pares.

```python
numeros = [1, 2, 3, 4, 5, 6]
pares = [n for n in numeros if n % 2 == 0]
```

---

## Condição com if e else

```python
resultado = ["par" if n % 2 == 0 else "ímpar" for n in numeros]
```

---

## Trabalhando com strings

Exemplo: converter nomes para maiúsculo.

```python
nomes = ["ana", "bruno", "carlos"]
nomes_maiusculo = [nome.upper() for nome in nomes]
```

---

## List Comprehension com funções

```python
def dobro(x):
    return x * 2

valores = [1, 2, 3, 4]
dobrados = [dobro(v) for v in valores]
```

---

## List Comprehension aninhada

```python
matriz = [[1, 2], [3, 4], [5, 6]]
valores = [n for linha in matriz for n in linha]
```

Resultado:

```python
[1, 2, 3, 4, 5, 6]
```

---

## Comparação: List Comprehension vs for tradicional

### for tradicional

```python
resultado = []
for n in range(10):
    if n > 5:
        resultado.append(n)
```

### List Comprehension

```python
resultado = [n for n in range(10) if n > 5]
```

---

## Quando usar List Comprehension

Use quando:

* A lógica é simples
* A expressão cabe em uma linha
* O código fica mais legível

Evite quando:

* A lógica é muito complexa
* Há muitos `if` aninhados
* A legibilidade é prejudicada

---

## Aplicação em Ciência de Dados

Exemplo: classificação de valores.

```python
valores = [100, 250, 500, 1000]

classificacao = [
    "Alto" if v >= 500 else "Baixo"
    for v in valores
]
```

Exemplo: limpeza simples de dados.

```python
dados = ["  Ana", "Bruno ", " Carlos "]
dados_limpos = [d.strip() for d in dados]
```

---

## Diferença entre list comprehension, map e filter

### map

```python
list(map(lambda x: x * 2, valores))
```

### filter

```python
list(filter(lambda x: x >= 500, valores))
```

List Comprehension geralmente é:

* Mais legível
* Mais usada na comunidade Python

---

## Performance

List Comprehension costuma ser:

* Mais rápida que loops tradicionais
* Mais eficiente em memória (em muitos casos)

---

## Boas práticas

* Priorize legibilidade
* Não abuse de aninhamentos
* Use nomes claros
* Quebre em funções se necessário

---

## Conclusão

Neste post você aprendeu:

* Estrutura da List Comprehension
* Uso com condições
* Uso com strings e funções
* Aplicações práticas em Ciência de Dados
