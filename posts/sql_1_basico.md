# 🗄️ Introdução ao SQL

O **SQL (Structured Query Language)** é a linguagem padrão para trabalhar com bancos de dados relacionais.  
Com ele, podemos **consultar, inserir, atualizar e deletar dados** de forma simples e organizada.

---

## 🔹 Por que aprender SQL?
- É essencial para quem trabalha com **dados**.  
- Permite acessar informações de forma rápida e precisa.  
- É usado em praticamente todas as empresas que lidam com grandes volumes de dados.  

---

## 📌 Comandos básicos

### 1. Selecionar dados
```sql
SELECT nome, idade 
FROM clientes;
```
👉 Esse comando retorna as colunas `nome` e `idade` da tabela `clientes`.

---

### 2. Filtrar resultados
```sql
SELECT * 
FROM pedidos
WHERE valor > 100;
```
👉 Aqui buscamos todos os pedidos com valor maior que 100.

---

### 3. Ordenar resultados
```sql
SELECT nome, idade 
FROM clientes
ORDER BY idade DESC;
```
👉 Lista os clientes em ordem decrescente de idade.

---

### 4. Inserir novos dados
```sql
INSERT INTO clientes (nome, idade) 
VALUES ('Maria', 28);
```
👉 Adiciona uma nova linha na tabela `clientes`.

---

## 🚀 Próximos passos
- Explorar **JOINs** para combinar tabelas.  
- Aprender funções agregadas como `COUNT`, `SUM`, `AVG`.  
- Criar consultas mais complexas para análise de dados.  

---

✨ *SQL é a chave para transformar dados brutos em informação útil.*


