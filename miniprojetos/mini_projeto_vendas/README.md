# Mini-Projeto: Análise de Vendas

## 📝 Descrição do Projeto

Este projeto tem como objetivo demonstrar o **fluxo completo de análise de dados** utilizando SQL, Python, Pandas, Matplotlib e Seaborn.  
O foco é analisar um **banco de dados de vendas** e extrair insights relevantes, como:

- Total de vendas por produto  
- Média de vendas por dia e por cliente  
- Distribuição de valores de vendas  
- Relação entre quantidade e valor total  

Este mini-projeto serve como **portfólio** para mostrar habilidades de Data Science e análise de dados.

---

## 📁 Estrutura do Projeto

```

mini_projeto_vendas/
│
├── data/
│   └── vendas.db             # Banco SQLite com dados de vendas
│
├── notebooks/
│   └── analise_vendas.ipynb  # Notebook Python com análise exploratória
│
├── scripts/
│   └── consulta_sql.py       # Script Python para consultar dados do SQLite
│
├── README.md                 # Este arquivo
└── requirements.txt          # Bibliotecas necessárias

````

---

## 🛠 Tecnologias Utilizadas

- **SQL (SQLite)**: armazenamento e consulta de dados  
- **Python**: manipulação, cálculo e análise  
- **Pandas**: limpeza e agregação de dados  
- **NumPy**: operações numéricas  
- **Matplotlib**: gráficos básicos  
- **Seaborn**: gráficos estatísticos e avançados  

---

## 🚀 Como Rodar o Projeto

1. Clone o repositório:

```bash
git clone https://github.com/UchoaLudimila/gitludi/miniprojetos/mini_projeto_vendas.git
cd mini_projeto_vendas
````

2. Crie um ambiente virtual (opcional, mas recomendado):

```bash
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
```

3. Instale as dependências:

```bash
pip install -r requirements.txt
```

4. Abra o **notebook** e rode a análise:

```bash
jupyter notebook notebooks/analise_vendas.ipynb
```

---

## 📊 Exemplos de Visualizações

### Total de vendas por produto

![Exemplo gráfico de barras](https://via.placeholder.com/600x300.png?text=Gr%C3%A1fico+de+Barras)

### Vendas por dia

![Exemplo gráfico de linha](https://via.placeholder.com/600x300.png?text=Gr%C3%A1fico+de+Linha)

### Distribuição de valor total por produto

![Exemplo boxplot](https://via.placeholder.com/600x300.png?text=Boxplot)

---

## 💡 Possíveis Insights

* Produtos mais vendidos
* Dias da semana com maior faturamento
* Diferença de compras por gênero de cliente
* Relação entre quantidade vendida e valor total

---

## 🔜 Próximos Passos

* Criar um **dashboard interativo** usando Plotly ou Streamlit
* Análise de tendências e sazonalidade
* Previsão de vendas futuras usando **Machine Learning**
* Integração com **API externa** para vendas em tempo real

---

## 📚 Referências

* [Pandas Documentation](https://pandas.pydata.org/docs/)
* [NumPy Documentation](https://numpy.org/doc/)
* [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)
* [Seaborn Documentation](https://seaborn.pydata.org/)
* [SQLite Tutorial](https://www.sqlite.org/docs.html)
