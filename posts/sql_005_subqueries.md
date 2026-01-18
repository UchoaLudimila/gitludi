## 📄 Conteúdo incrementado sobre Subqueries

### 🔹 1. Introdução
- Uma **subquery** é uma consulta dentro de outra consulta.  
- Pode aparecer em diferentes partes: `WHERE`, `FROM`, `SELECT`.  
- Existem dois tipos principais:  
  - **Independentes** → não dependem da consulta externa.  
  - **Correlacionadas** → dependem da consulta externa para cada linha.

---

### 🔹 2. Subquery no WHERE (independente)
```sql
SELECT nome, idade
FROM clientes
WHERE id IN (
    SELECT cliente_id
    FROM pedidos
    WHERE valor > 500
);
```
👉 Retorna os clientes que têm pedidos acima de 500.

---

### 🔹 3. Subquery no FROM (como tabela temporária)
```sql
SELECT cliente_id, AVG(valor) AS media_por_cliente
FROM (
    SELECT cliente_id, valor
    FROM pedidos
) AS sub
GROUP BY cliente_id;
```
👉 Usa uma subquery como tabela temporária para calcular a média de pedidos por cliente.

---

### 🔹 4. Subquery no SELECT (correlacionada)
```sql
SELECT nome,
       (SELECT COUNT(*) 
        FROM pedidos 
        WHERE pedidos.cliente_id = clientes.id) AS total_pedidos
FROM clientes;
```
👉 Para cada cliente, calcula o total de pedidos usando uma subquery.

---

### 🔹 5. Subquery com EXISTS
```sql
SELECT nome
FROM clientes c
WHERE EXISTS (
    SELECT 1
    FROM pedidos p
    WHERE p.cliente_id = c.id
);
```
👉 Retorna apenas clientes que possuem pelo menos um pedido.

---

### 🔹 6. Subquery com NOT EXISTS
```sql
SELECT nome
FROM clientes c
WHERE NOT EXISTS (
    SELECT 1
    FROM pedidos p
    WHERE p.cliente_id = c.id
);
```
👉 Retorna clientes que **não possuem pedidos**.

---

### 🔹 7. Subquery com funções agregadas
```sql
SELECT nome, idade
FROM clientes
WHERE idade > (
    SELECT AVG(idade)
    FROM clientes
);
```
👉 Retorna clientes com idade acima da média.

---

### 🔹 8. Dicas finais
- Sempre use **alias** (`AS sub`) para nomear subqueries no `FROM`.  
- Prefira **JOINs** quando possível, pois podem ser mais eficientes.  
- Use **EXISTS** e **NOT EXISTS** para verificar presença ou ausência de registros.  
- Subqueries são poderosas para relatórios complexos e análises avançadas.  

---

✨ *Subqueries são como consultas dentro de consultas: permitem resolver problemas complexos sem criar tabelas extras.*  

---
