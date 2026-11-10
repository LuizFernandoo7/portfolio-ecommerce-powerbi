# 📊 E-Commerce Dashboard - Análise de Vendas e Retenção (Power BI)

## 📌 Visão Geral do Projeto
Este é o segundo projeto do meu portfólio de transição para a área de Análise de Dados, focado na construção de um dashboard executivo de Business Intelligence utilizando **Power BI**. Os dados consumidos neste painel foram modelados e importados de um banco de dados relacional SQL Server (construído do zero no meu [Projeto 1 - Inserir Link Aqui]). 

O objetivo deste dashboard é fornecer à gestão uma visão clara e limpa da saúde financeira da loja, acompanhando a evolução do faturamento, retenção de clientes e o desempenho de vendas por categoria de produto.

## 🛠️ Ferramentas e Tecnologias Utilizadas
* **Power BI Desktop:** Importação de dados, Modelagem, Linguagem DAX e Visualização de Dados.
* **SQL Server:** Fonte de dados estruturada.

## 🧠 Modelagem de Dados e Estrutura Analítica
Para garantir a integridade dos filtros e a precisão das análises, o modelo de dados foi estruturado aplicando as melhores práticas de mercado:
* **Relacionamentos Inteligentes:** Conexão estruturada entre as tabelas `Clientes`, `Pedidos`, `Produtos` e `Itens_Pedido`.
* **dCalendario (Dimensão Temporal):** Criada integralmente via linguagem DAX para permitir a análise cronológica correta e o agrupamento de métricas por "Ano-Mês".
* **Tabela de Medidas Exclusiva (`_Medidas`):** Centralização de todos os cálculos do projeto para manter a organização e escalabilidade do modelo.

## 📈 Principais Métricas e Fórmulas DAX
As medidas foram desenvolvidas com foco em performance e para corrigir comportamentos padrão de filtro cruzado (*cross-filtering*) entre as tabelas de dimensão e fato.

* **Faturamento Total:** `SUM(Itens_Pedido[preco_unitario])`
* **Total de Clientes (Únicos):** `DISTINCTCOUNT(Pedidos[id_cliente])` *(Garante que clientes com compras recorrentes não inflem o número total).*
* **Total de Itens Vendidos:** `COUNTROWS(Itens_Pedido)` *(Solução analítica aplicada para corrigir a falha de propagação de filtro Lado 1 -> Muitos, garantindo o ranqueamento correto de categorias no eixo).*

## 💡 Visualização e Interatividade
O layout foi planejado para evitar poluição visual ("Lixo Gráfico"), priorizando a tomada de decisão rápida:
* **Cartões de KPI (Top Level):** Leitura instantânea do volume de pedidos (39), clientes únicos (20) e faturamento bruto (R$ 6,75 Mil).
* **Evolução Temporal:** Identificação de picos de venda, com destaque para a forte tração financeira em Março de 2026.
* **Ranking de Categorias:** Visão clara do comportamento do portfólio, revelando um empate técnico na liderança entre as áreas de "Moda" e "Eletrônicos".
* **Interatividade Completa:** Todos os gráficos atuam como filtros simultâneos, permitindo análises isoladas de comportamento com um único clique.

<img width="870" height="504" alt="capa" src="https://github.com/user-attachments/assets/211171c7-de78-462d-9924-44b7eaa15ddd" />
