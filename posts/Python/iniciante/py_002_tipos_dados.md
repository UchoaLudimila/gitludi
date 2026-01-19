# Python 002 – Tipos de Dados

## Introdução

Em Python, os tipos de dados definem **que tipo de valor** uma variável pode armazenar
e **quais operações** podem ser realizadas com ela.

Entender bem os tipos de dados é fundamental para escrever códigos corretos
e evitar erros comuns, especialmente em Ciência de Dados.

---

## Tipos de dados básicos

### Inteiro (`int`)

Usado para números inteiros.

```python
idade = 30
quantidade = -5
````

---

### Ponto flutuante (`float`)

Usado para números decimais.

```python
preco = 19.99
altura = 1.75
```

---

### Texto (`str`)

Usado para armazenar texto.

```python
nome = "Maria"
cidade = 'São Paulo'
```

Strings podem usar aspas simples ou duplas.

---

### Booleano (`bool`)

Usado para valores lógicos.

```python
ativo = True
aprovado = False
```

Muito utilizado em condições (`if`).

---

## Verificando o tipo de um objeto

```python
type(idade)
type(preco)
type(nome)
type(ativo)
```

---

## Conversão de tipos (Type Casting)

### Convertendo para inteiro

```python
idade_texto = "25"
idade = int(idade_texto)
```

---

### Convertendo para float

```python
preco_texto = "19.99"
preco = float(preco_texto)
```

---

### Convertendo para string

```python
idade = 30
idade_str = str(idade)
```

---

## Tipos de dados compostos

### Lista (`list`)

Coleção ordenada e mutável.

```python
numeros = [1, 2, 3, 4]
nomes = ["Ana", "Bruno", "Carlos"]
```

Acessando elementos:

```python
numeros[0]
nomes[1]
```

---

### Tupla (`tuple`)

Semelhante à lista, porém imutável.

```python
coordenadas = (10, 20)
```

---

### Dicionário (`dict`)

Estrutura de chave e valor.

```python
pessoa = {
    "nome": "Ana",
    "idade": 25,
    "cidade": "SP"
}
```

Acessando valores:

```python
pessoa["nome"]
pessoa["idade"]
```

---

### Conjunto (`set`)

Coleção não ordenada e sem valores duplicados.

```python
numeros_unicos = {1, 2, 3, 3, 4}
```

Resultado:

```python
{1, 2, 3, 4}
```

---

## Operações comuns com tipos de dados

### Strings

```python
nome = "Ana"

nome.upper()
nome.lower()
len(nome)
```

---

### Listas

```python
numeros = [1, 2, 3]

numeros.append(4)
numeros.remove(2)
```

---

### Dicionários

```python
pessoa["idade"] = 26
pessoa.keys()
pessoa.values()
```

---

## Tipos mutáveis vs imutáveis

### Mutáveis

* list
* dict
* set

### Imutáveis

* int
* float
* str
* tuple

Exemplo:

```python
lista = [1, 2, 3]
lista[0] = 10  # funciona

texto = "abc"
# texto[0] = "x"  # erro
```

---

## Erros comuns com tipos de dados

* Tentar somar `int` com `str`
* Converter textos inválidos para número
* Confundir lista com tupla
* Acessar índices inexistentes

Exemplo de erro:

```python
"10" + 5  # TypeError
```

---

## Aplicação em Ciência de Dados

* Strings → nomes, categorias
* Inteiros → quantidades
* Floats → preços, medidas
* Listas e dicionários → estruturas temporárias
* DataFrames (Pandas) → dados tabulares

---

## Conclusão

Neste post você aprendeu:

* Tipos básicos de dados em Python
* Conversão de tipos
* Estruturas compostas
* Diferença entre tipos mutáveis e imutáveis
