## 📄 Estrutura do conteúdo sobre JOINs

### 🔹 1. Introdução
- O que é JOIN: comando usado para **combinar dados de duas ou mais tabelas**.  
- Por que é importante: permite analisar informações que estão distribuídas em diferentes tabelas.  

---

### 🔹 2. Tipos principais de JOIN

#### **INNER JOIN**
- Retorna apenas registros que têm correspondência em ambas as tabelas.  
```sql
SELECT clientes.nome, pedidos.valor
FROM clientes
INNER JOIN pedidos
ON clientes.id = pedidos.cliente_id;
```
👉 Mostra apenas clientes que possuem pedidos.

---

#### **LEFT JOIN**
- Retorna todos os registros da tabela da esquerda, mesmo sem correspondência na direita.  
```sql
SELECT clientes.nome, pedidos.valor
FROM clientes
LEFT JOIN pedidos
ON clientes.id = pedidos.cliente_id;
```
👉 Lista todos os clientes, incluindo os que não têm pedidos (os valores aparecem como `NULL`).

---

#### **RIGHT JOIN**
- Retorna todos os registros da tabela da direita, mesmo sem correspondência na esquerda.  
```sql
SELECT clientes.nome, pedidos.valor
FROM clientes
RIGHT JOIN pedidos
ON clientes.id = pedidos.cliente_id;
```
👉 Lista todos os pedidos, mesmo que não tenham cliente associado.

---

#### **FULL JOIN**
- Retorna todos os registros quando há correspondência em uma das tabelas.  
```sql
SELECT clientes.nome, pedidos.valor
FROM clientes
FULL JOIN pedidos
ON clientes.id = pedidos.cliente_id;
```
👉 Mostra todos os clientes e todos os pedidos, mesmo sem correspondência.

---

### 🔹 3. Dica final
- Sempre defina bem a **chave de ligação** (`ON tabela1.coluna = tabela2.coluna`) para evitar resultados incorretos.  
- JOINs são a base para análises mais avançadas, como relatórios e dashboards.  

---
