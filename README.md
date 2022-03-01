# PA04-Health-Insurance-Cross-Sell
## STATUS DO PROJETO: EM CONSTRUÇÃO

## Contexto
### Projeto de Classificação quanto a propensão de Vendas de uma Seguradora.

 A Insurance All é uma empresa que fornece seguro de saúde para seus clientes e o time de produtos está analisando a possibilidade de oferecer aos assegurados, um novo produto: Um seguro de automóveis.

Foi feita uma pesquisa com cerca de 380 mil clientes sobre o interesse em aderir a um novo produto de seguro de automóveis, estas respostas ficaram salvas em um banco de dados junto com outros atributos dos clientes.

O Contexto, é fictício. A empresa, o contexto, o CEO, as perguntas de negócio foram elaborados com o objetivo de demonstrar meus conhecimentos e capacidade de solucionar um problema real.

## 1. Questão de Negócio

### 1.1. Problema 

A empresa selecionou 127 mil novos clientes para participar de uma campanha, no qual receberão a oferta do novo produto, esta será feita pelo time de vendas através de ligações telefônicas. 
Contudo, o time de vendas tem uma capacidade de realizar 20 mil ligações dentro do período da campanha.
É necessário um modelo que prediz e classifica os clientes com maior propensão de adquirirem o novo produto. O time de vendas espera que seja priorizado as pessoas com maior interesse de compra afim de otimizar a campanha priorizando estes. 
 
### 1.2. Causas do Problema

Campanha tem limite de 20 mil ligações dentro dos 127 mil clientes selecionados, não possuindo uma forma de classificar estes clientes para poder priorizar os clientes com maior potencial de compra dentro deste banco de dados. 



### 1.3. Solução 

Será desenvolvido de a cordo com o pedido e necessidade do cliente as seguintes questões:

<b>Q1.</b> Elaborar lista com os principais Insights sobre os atributos mais relevantes dos clientes interessados na aquisição do novo produto.

<b>Q2.</b> Por meio de algorítimos de Machine Learning será calculado a porcentagem de clientes com maior propensão de vendas, afim de priorizar os 20 mil clientes a serem contatados pelo time de vendas.

<b>Q3.</b> Projeções caso o número de ligações aumente para 40 mil, qual seria o aumento de  de número de clientes contatados.

<b>Q4.</b> Projeção de número de ligações necessárias para contatar 80% dos interessados no novo produto. 
 
## 2. Planejamento da Solução

### 2.1. O que será entregue

- Uma planilha desenvolvida na plataforma google sheets, que terá acesso via API ao modelo de Machie Learn desenvolvido. Este modelo estará hospedado em nuvem na plataforma Heroku Clound. Na tabela será feito por meio do APP Script, um novo botão onde o usuário poderá carregar uma lista de clientes com as features necessárias para esta tabela e fazer a previsão do score de propensão de venda de cada cliente, podendo classificar a lista na ordem dos clientes mais propensos a adquirirem o produto. 
### 2.2. Ferramentas Usadas

- Python 3.8;
- Jupyter Notebook;
- Panda Enviroment;
- Git e Github;
- Heroku;
- Flask e python API's
- Google Sheets e App Script

### 2.3. Processo 

