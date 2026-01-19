# Python 003 – Estruturas de Controle

## Introdução

As estruturas de controle permitem que o programa:
- Tome decisões
- Execute blocos de código repetidamente
- Controle o fluxo de execução

Elas são fundamentais para qualquer linguagem de programação
e muito utilizadas em Ciência de Dados.

---

## Estruturas condicionais

### if / elif / else

Permite executar diferentes blocos de código dependendo de uma condição.

```python
idade = 18

if idade >= 18:
    print("Maior de idade")
else:
    print("Menor de idade")
````

---

### Usando elif

```python
nota = 7

if nota >= 9:
    print("Excelente")
elif nota >= 6:
    print("Aprovado")
else:
    print("Reprovado")
```

---

## Operadores de comparação

| Operador | Significado    |
| -------- | -------------- |
| `==`     | igual          |
| `!=`     | diferente      |
| `>`      | maior          |
| `<`      | menor          |
| `>=`     | maior ou igual |
| `<=`     | menor ou igual |

Exemplo:

```python
idade >= 18
```

---

## Operadores lógicos

| Operador | Significado |
| -------- | ----------- |
| `and`    | e           |
| `or`     | ou          |
| `not`    | não         |

Exemplo:

```python
idade >= 18 and idade <= 65
```

---

## Estruturas de repetição

### for

Usado para percorrer sequências (listas, strings, intervalos).

```python
nomes = ["Ana", "Bruno", "Carlos"]

for nome in nomes:
    print(nome)
```

---

### for com range()

```python
for i in range(5):
    print(i)
```

Resultado:

```
0
1
2
3
4
```

---

### while

Executa o código enquanto a condição for verdadeira.

```python
contador = 0

while contador < 5:
    print(contador)
    contador += 1
```

---

## Controle de loops

### break

Interrompe o loop.

```python
for numero in range(10):
    if numero == 5:
        break
    print(numero)
```

---

### continue

Pula a iteração atual.

```python
for numero in range(5):
    if numero == 2:
        continue
    print(numero)
```

---

## Estruturas aninhadas

É possível usar estruturas dentro de outras.

```python
for i in range(3):
    if i % 2 == 0:
        print(i, "é par")
    else:
        print(i, "é ímpar")
```

---

## Uso comum em Ciência de Dados

### Exemplo: classificação simples

```python
valores = [100, 250, 500, 1000]

for valor in valores:
    if valor >= 500:
        print(valor, "→ valor alto")
    else:
        print(valor, "→ valor baixo")
```

---

## Cuidados com loops

* Evite loops desnecessários
* Prefira operações vetorizadas (quando usar Pandas)
* Cuidado com loops infinitos no `while`

Exemplo de loop infinito (erro comum):

```python
while True:
    print("Executando...")
```

---

## Boas práticas

* Use indentação correta (Python depende disso)
* Mantenha condições simples
* Evite aninhar muitos `if`s
* Use nomes de variáveis claros

---

## Conclusão

Neste post você aprendeu:

* Estruturas condicionais (`if`, `elif`, `else`)
* Operadores de comparação e lógicos
* Estruturas de repetição (`for`, `while`)
* Controle de loops (`break`, `continue`)
