## 📄 Estrutura do conteúdo sobre GROUP BY e HAVING

### 🔹 1. Introdução
- O comando **GROUP BY** é usado para **agrupar registros** que possuem valores iguais em determinadas colunas.  
- Ele é essencial para aplicar funções agregadas em grupos de dados.  
- O **HAVING** funciona como um filtro, parecido com o `WHERE`, mas aplicado **após o agrupamento**.

---

### 🔹 2. GROUP BY básico
```sql
SELECT cliente_id, SUM(valor) AS total_por_cliente
FROM pedidos
GROUP BY cliente_id;
```
👉 Agrupa os pedidos por cliente e calcula o total de vendas de cada um.

---

### 🔹 3. GROUP BY com múltiplas colunas
```sql
SELECT cliente_id, produto_id, SUM(valor) AS total_por_produto
FROM pedidos
GROUP BY cliente_id, produto_id;
```
👉 Agrupa por cliente **e** produto, mostrando quanto cada cliente gastou em cada produto.

---

### 🔹 4. HAVING para filtrar grupos
```sql
SELECT cliente_id, SUM(valor) AS total_por_cliente
FROM pedidos
GROUP BY cliente_id
HAVING SUM(valor) > 500;
```
👉 Mostra apenas os clientes cujo total de compras foi maior que 500.

---

### 🔹 5. Diferença entre WHERE e HAVING
- **WHERE** → filtra registros **antes** do agrupamento.  
- **HAVING** → filtra grupos **depois** do agrupamento.  

Exemplo:  
```sql
-- WHERE filtra pedidos antes do agrupamento
SELECT cliente_id, SUM(valor)
FROM pedidos
WHERE valor > 100
GROUP BY cliente_id;

-- HAVING filtra clientes depois do agrupamento
SELECT cliente_id, SUM(valor)
FROM pedidos
GROUP BY cliente_id
HAVING SUM(valor) > 500;
```

---

### 🔹 6. Dica final
- Sempre combine **GROUP BY** com funções agregadas (`SUM`, `COUNT`, `AVG`, etc.).  
- Use **HAVING** quando precisar aplicar condições sobre os resultados agregados.  

---
