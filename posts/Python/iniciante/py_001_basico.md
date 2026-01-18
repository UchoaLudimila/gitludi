# Python 001 – Introdução e Conceitos Básicos

## O que é Python?

Python é uma linguagem de programação:
- Simples e fácil de aprender
- Muito utilizada em Ciência de Dados, Análise de Dados e Machine Learning
- Possui uma grande comunidade e diversas bibliotecas

Em Ciência de Dados, Python é usado principalmente para:
- Manipulação de dados
- Análise exploratória
- Visualização
- Modelagem estatística e Machine Learning

---

## Instalando e executando Python

Existem várias formas de usar Python:

- Instalação local (Python + VS Code)
- Anaconda
- Google Colab
- Jupyter Notebook

Para iniciantes em Ciência de Dados, **Jupyter Notebook** e **Google Colab** são ótimas opções.

---

## Primeiro código em Python

O clássico "Olá, mundo":

```python
print("Olá, mundo!")
````

A função `print()` é usada para exibir informações na tela.

---

## Comentários em Python

Comentários servem para explicar o código e não são executados.

```python
# Este é um comentário de uma linha

print("Aprendendo Python")  # Comentário ao lado do código
```

---

## Variáveis

Variáveis são usadas para armazenar valores.

```python
idade = 25
nome = "Ana"
altura = 1.68
```

Em Python:

* Não é necessário declarar o tipo da variável
* O tipo é definido automaticamente

---

## Tipos básicos de dados

### Inteiro (int)

```python
quantidade = 10
```

### Decimal (float)

```python
preco = 19.99
```

### Texto (string)

```python
cidade = "São Paulo"
```

### Booleano (bool)

```python
ativo = True
```

---

## Verificando o tipo de uma variável

```python
type(quantidade)
type(preco)
type(cidade)
type(ativo)
```

---

## Operações básicas

### Operações matemáticas

```python
a = 10
b = 3

print(a + b)  # soma
print(a - b)  # subtração
print(a * b)  # multiplicação
print(a / b)  # divisão
```

---

## Entrada de dados do usuário

```python
nome = input("Digite seu nome: ")
print("Olá,", nome)
```

> Obs: A função `input()` sempre retorna uma string.

---

## Conversão de tipos

```python
idade = int(input("Digite sua idade: "))
altura = float(input("Digite sua altura: "))
```

---

## Boas práticas iniciais

* Use nomes de variáveis claros
* Evite nomes genéricos como `x` e `y`
* Use comentários quando necessário
* Mantenha o código simples e legível

---

## Conclusão

Neste post vimos:

* O que é Python
* Como executar código básico
* Variáveis e tipos de dados
* Operações simples
