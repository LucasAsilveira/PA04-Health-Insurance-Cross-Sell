# PA04-Health-Insurance-Cross-Sell

![Imagem_Insurance_Car](https://user-images.githubusercontent.com/94136773/156264357-a7b4bc53-5c55-48ec-bd20-7ebd681a9b1e.jpg)

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

Será desenvolvido de a cordo com o pedido e necessidade levantadas pelo CEO as seguintes questões:

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
- Biblioteca Pandas ;
- Git e Github;
- Heroku;
- Flask e python API's
- Google Sheets e App Script

### 2.3. Processo 

- Coleta de Dados: Através conexão com banco de dados Postgress hospedado numa clound da AWS.
- Limpeza dos Dados: Organizar e Renomear colunas, descrever os tipos, dimensão, checar dados faltantes e Realizar Descrição estatística, criar hipóteses de negócio criando novas variáveis para exploração destas adiante.
- Exploração dos dados: Fazer análise gráfica das variáveis, validar as hipóteses levantadas.
- Modelagem dos dados: Transformação das variáveis fazendo ajuste de escala e fazendo as transformações necessárias para podermos usar o algoritmos de Machine Learning da melhor forma. Usaremos o Boruta junto com a analise das hipóteses para escolher as variáveis para o modelo final.
- Avaliação do Algoritmo: Será feita ordenação dos dados conforme score de propensão de predito pelo modelo. Avaliando gráfico curva de ganho e lift destes dados ordenados assim como metodo de Precisão e Recall Top k. 
- Modelo em Produção: Colocar o  modelo no Heroku para hospedá-lo e ficar sempre disponível para acesso, onde será elaborada tabela google sheets para realizar ordenação dos clientes. 

## 3. Principais Insights dos Dados

1. Clientes em faxa etárias de idade maior possuem mais interesse pelo seguro.(FALSO)
- Insight Gerado: A faxa etária de maior interesse é de 42 a 52 anos. Sendo que na faixa de 30 a 40 também os clientes demosntraram mais interesse. Caindo bastante o interesse nas faixas mais baixas de idade e um pouco nas faixas mais altas.

2. Clientes com automóveis mais novos e não possuem seguro de automóvel tem mais interesse pelo seguro.(FALSO)
- Insight Gerado: Na verdade clientes com automóveis mais velhos e que não possuem seguros tem mais interesse.

3. Clientes com automóveis que já sofreram danos, possuem mais interesse pelo seguro.(VERDADEIRO)
- Insgith Gerado: Clientes que já tiveram danos, tem muito mais interesse pelo seguro, apesar de parecer óbvio, ao analisarmos os dados vimos que tem uma diferença de interesse bem acentuada. 

4.  Clientes do gênero feminino possuem proporcionalmente, mais interesse pelo seguro.(FALSO)
- Insight Gerado: Na realidade Clientes do gênero Masculino possuem mais interesse.

## 4. Modelo de Machine Learning

 <b> Modelos testados:</b>
  
Para desenvolver o modelo de Machine Learning a ser usado no projeto, inicialmente foi testado o desempenho de alguns algortmos de Machine Learn para podemos selecionar o de melhor desempenho para o nosso problema. Para medir o desempenho cada modelo foi treinado com dados de treino(80%) e teste(20%), foi feito uma ordenação em formato de lista com o resultado de propensão de venda de cada cliente, as métricas usadas para medir este desempenho foram: Precision Top K e Recall Top K. 

- Precision top k: Conta quantas predições foram corretas até k e dividi por todas as predições realizada pelo modelo até k. Onde k  é o número de elementos testatados. <b>Tabela com resultados dos modelos para métrica Precision top k:</b>

![image](https://user-images.githubusercontent.com/94136773/158162036-9f50ac1e-6236-404e-b9b7-b60742934e9c.png)


- Recall Top K: Conta quantas predições foram corretas até k e dividi por todos os exemplos verdadeiros.
<b>Tabela com resultados dos modelos para métrica Recall top k:</b>

![image](https://user-images.githubusercontent.com/94136773/158162300-c6dc3517-1498-42ca-82d3-ff387a22c552.png)

<b> Analisando Resultados:</b> Com base nos resultados, conseguimos ter desempenhos muito semelhantes para os algoritmos Random Forest e o Xgboost Classifier, sendo que o primeiro desempenhou um pouco melhor para números maiores de k, enquanto o segundo obterve melhores resultados para números menores de k. Levando em consideração que o número de telefonemas que será usado na base é de 20000 para 127000 ligações, ou seja em torno de 15% dos dados, foid ecidido seguir com o Xboost Classifier que desempenhou melhor para esta proporção dos dados alem de ser um modelo mais leve que o Random Forest. 

#### Modelos Final(Xboost Classifier): 
 Após ser definido o algoritmo de ML a ser usado, foi feito um ajuste fino dos hyperparâmetros do modelo para melhorar seu desempenho, a técnica usada foi Random Search, técnica de uso rápido e simples, onde definimos alguns valores a ser testados para os principais parâmetros, rodando o algoritmo na base de dados diversas vezes de forma randômica e medindo o seu desempenho para definir os melhores parâmetros a serem usados. 
 <b>Com os parâmetros ajustados tivemos os modelo final definido, a baixo a curvas de ganho e de lift obtidas:</b>
 
 ![image](https://user-images.githubusercontent.com/94136773/158164534-dc97bd54-0191-419a-b1be-d7d3cd1a91c9.png)

 <b>Tabela com resultados do modelo final das métrica Precision e Recall top k:</b>
  
 ![image](https://user-images.githubusercontent.com/94136773/158164937-ac341933-3995-47a6-897d-50e1090bace1.png)

 Obtivemos uma melhora com relação ao modelo não ajustado usando o k de 15% e 30% de 2.1% e 1.27% respectivamente. 
 
## 5. Respondendo Questões de Negócio:

### Questões Levantadas pelo CEO

<b>Q2.</b> Com 20.000 ligações, quantos clientes interessados iram ser alcançados?

- Com 20.000 ligações serão alcançados 7213 clientes interessados. 
- Estas 20.000 ligações representam 15.75% da base de clientes que será usada pelo time de vendas e alcançariam 47,33% dos clientes interessados.

<b>Q3.</b> Com 40.000 ligações, quantos clientes interessados iram ser alcançados?

- Com 40.000 ligações serão alcançados 12320 clientes interessados. 
- Estas 40.000 ligações representam 31,5% da base de clientes que será usada pelo time de vendas e alcançariam 80.84% dos clientes interessados.

<b>Q4.</b> Para alcançar 80% dos interessados quantas ligações teriam que ser feitas?

- Para atingir 80% serão necessário fazer 39192 ligações.
- Estas 39192 ligações, correspondem a 30,86% da base de clientes. 



| Número Ligações |  %Interessados  | Número de Interessados |
| ------------------- | ------------------- | ------------------- |
|  20000 |  47.33 | 7213 |
|  40000 |  80.84 | 12320 |
|  39192 |  80.00 | 12192 |

### Planilha Google Sheets colocada em produção

- Na imagem a baixo, tem um exemplo da tabela feita na plataforma Google Sheets, onde colocando a lista de clientes, conseguimos fazer a predição de score de cada cliente e classificarmos segundo o score predito pelo modelo. <b> Uma tabela teste, com 1000 dados onde foi realizado uma predição para teste pode ser acessada clicando no [LINK](https://docs.google.com/spreadsheets/d/e/2PACX-1vSEdUJ5gYjwt1K9arIASQ5ufINOx0hrEsCnB_r8N4PTsGIoxwvB-n0kd3AQUU7545a3uzArOhbnU4hV/pubhtml?gid=0&single=true)</b>

![Tabela_Predicao_Score](https://user-images.githubusercontent.com/94136773/156259601-7aba2ecf-bee4-4897-bba4-0983d4490751.jpg) 
 
## 6. Resultados financeiros para o negócio

- Para fazermos estimativas financeiras que poderá ser gerado ao implementar o modelo, utilizamos as seguintes premissas:
 
<b>1.</b> Os cálculos foram realizados partindo da premissa que a proporção de pessoas interessadas na lista de clientes utilizada pelo setor de vendas se manterá a mesma da base utilizada para treinar o modelo.

<b>2.</b>  Todos os clientes interessados que forem contatados irão contratar o seguro.

<b>3.</b>  Para comparar com o modelo usamos os resultados de um modelo que escolheria os clientes de forma aleatória para estimarmos o ganho a mais do que um aleatório.


| Número Ligações |  Ganho  Clientes | % Ganho Performance |Ganho Financeiro(R$)|
| ------------------- | ------------------- | ------------------- |-------------------|
|  20000 |  4819 | 301.29 |7.228.500,00|
|  40000 |  5107  | 127.80 |7.660.500,00|

## 7. Conclusão:

O objetivo final foi alcançado, o modelo final conseguiu obter resultados estimados de até 300% para alcançar clientes interessados quando feito para selecionar 20.000 ligações e 127% ao dobrar as ligações para 40.000 ligações.
As estimativas econômicas tiveram uma crescente consideravel também. 
O modelo ficará em produção e poderá ser utilizado para novas listas de clientes para possíveis novas captação clientes pelo time de vendas. 

## 8. Próximos Passos:

- Coletar feedbacks sobre a Usabilidade afim de implementar melhorias. 
- Testar novas features, criando features derivadas e testar melhora de performance a partir destas.  
- Testar novos modelos de Machine Learn e diferente encoders nas features para tentar melhorar a performance. 
 
## 9. Referências:

- Dataset usado do [Kaggle](https://www.kaggle.com/anmolkumar/health-insurance-cross-sell-prediction)
- Este projeto foi realizado durante o curso 'DS em Produção', [Comunidade DS](https://www.comunidadedatascience.com/ds-em-producao/)
- Imagem utilizada é de uso livre no site [pixabay](https://pixabay.com/pt/illustrations)



