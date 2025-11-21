# 💰 Otimização de Preços (Pricing & Elasticidade)

### 1. O Problema de Negócio
Em um marketplace competitivo como a Olist, definir o preço correto é crucial. Um preço muito alto derruba as vendas; um muito baixo corrói a margem. O objetivo deste projeto é calcular a **Elasticidade-Preço da Demanda (PED)** de produtos reais para entender a sensibilidade dos consumidores a variações de preço.

### 2. Os Dados
Utilizou-se o dataset real do E-commerce Brasileiro (Olist) disponível no Kaggle.
* **Foco:** Análise do produto "Best Seller" da categoria **Móveis e Decoração**.
* **Tabelas processadas:** `olist_order_items` (transações) e `olist_products` (metadados).

### 3. Metodologia
* **Engenharia de Dados:** Join entre tabelas transacionais e de cadastro de produtos.
* **Filtragem:** Seleção do SKU com maior volume histórico de vendas para garantir significância estatística.
* **Modelagem Econométrica:** Aplicação de **Regressão Log-Log** (OLS) para estimar a elasticidade ($\beta$). A fórmula utilizada foi:
  $ln(Quantidade) = \alpha + \beta \cdot ln(Preço)$

### 4. Resultados Impressionantes
O modelo identificou uma elasticidade extremamente alta de **-18.09**.

**Insight de Negócio:**
O gráfico abaixo mostra que o produto é **altamente elástico**.
* Ao preço de **R$ 70,00**, o volume de vendas ultrapassa 400 unidades.
* Um pequeno aumento para **R$ 75,00** (apenas ~7% de aumento) faz a demanda despencar para cerca de 120 unidades.

<img width="734" height="477" alt="image" src="https://github.com/user-attachments/assets/8469df54-9f1d-49cd-a207-0232aa667e40" />


**Conclusão:** Para este produto específico, a estratégia de "Preço Baixo / Alto Volume" é a vencedora. Tentativas de aumentar a margem unitária resultam em perda massiva de receita total.

### 5. Ferramentas
* Python (Pandas, Statsmodels)
* Análise de Dados Reais (Data Engineering básico)
