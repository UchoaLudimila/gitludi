# Python 004 – Funções

## Introdução

Funções permitem **organizar**, **reutilizar** e **simplificar** o código.
Em Ciência de Dados, funções são muito usadas para:
- Limpeza de dados
- Transformações
- Cálculos repetitivos
- Padronização de análises

---

## O que é uma função?

Uma função é um bloco de código que:
- Executa uma tarefa específica
- Pode receber parâmetros
- Pode retornar um valor

---

## Criando uma função

Usamos a palavra-chave `def` para definir uma função.

```python
def saudacao():
    print("Olá, seja bem-vindo!")
````

Chamando a função:

```python
saudacao()
```

---

## Funções com parâmetros

```python
def saudacao(nome):
    print("Olá,", nome)
```

Chamando a função:

```python
saudacao("Ana")
```

---

## Funções com mais de um parâmetro

```python
def soma(a, b):
    print(a + b)
```

```python
soma(5, 3)
```

---

## Retornando valores (return)

O `return` permite que a função devolva um resultado.

```python
def soma(a, b):
    return a + b
```

```python
resultado = soma(10, 5)
print(resultado)
```

---

## Diferença entre print e return

```python
def exemplo_print():
    print("Isso é um print")

def exemplo_return():
    return "Isso é um return"
```

* `print` → apenas exibe
* `return` → devolve o valor para uso posterior

---

## Parâmetros padrão

```python
def saudacao(nome="Usuário"):
    print("Olá,", nome)
```

```python
saudacao()
saudacao("Carlos")
```

---

## Argumentos nomeados

```python
def cadastro(nome, idade, cidade):
    print(nome, idade, cidade)
```

```python
cadastro(idade=30, nome="Ana", cidade="SP")
```

---

## Funções dentro de funções

```python
def calcular_media(notas):
    return sum(notas) / len(notas)

def situacao_aluno(notas):
    media = calcular_media(notas)
    if media >= 6:
        return "Aprovado"
    else:
        return "Reprovado"
```

---

## Funções e escopo de variáveis

### Escopo local

```python
def exemplo():
    x = 10
    print(x)
```

### Escopo global

```python
x = 5

def exemplo():
    print(x)
```

---

## Funções lambda

Funções anônimas e curtas.

```python
dobro = lambda x: x * 2
dobro(5)
```

Uso comum com listas:

```python
valores = [1, 2, 3, 4]
list(map(lambda x: x * 2, valores))
```

---

## Aplicação em Ciência de Dados

Exemplo: padronizar valores.

```python
def classificar_valor(valor):
    if valor >= 1000:
        return "Alto"
    elif valor >= 500:
        return "Médio"
    else:
        return "Baixo"
```

Essa função pode ser usada depois em Pandas com `apply()`.

---

## Boas práticas ao criar funções

* Funções devem ter uma responsabilidade clara
* Use nomes descritivos
* Evite funções muito longas
* Documente quando necessário

Exemplo com docstring:

```python
def soma(a, b):
    """
    Retorna a soma de dois números.
    """
    return a + b
```

---

## Erros comuns com funções

* Esquecer de chamar a função
* Confundir `print` com `return`
* Usar variáveis fora do escopo
* Criar funções genéricas demais

---

## Conclusão

Neste post você aprendeu:

* Como criar funções
* Parâmetros e retorno
* Funções lambda
* Escopo de variáveis
* Boas práticas
