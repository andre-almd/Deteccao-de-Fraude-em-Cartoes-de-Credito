# Detecção-de-Fraude-em-Cartões-de-Crédito

Neste projeto, iremos abordar o problema das fraudes em cartões de crédito, uma das principais preocupações das instituições financeiras como bancos e fintechs.

**Este é um projeto proposto no curso Data Science Na Prática 3.0 do [Sigmoidal](https://sigmoidal.ai/).**

---

![](img/img.jpg)

Apenas no Brasil, de janeiro a julho de 2022, foram [mais de 5 milhões de tentativas de crimes](https://extra.globo.com/economia-e-financas/brasil-registra-mais-de-mil-tentativas-de-fraudes-financeiras-digitais-por-hora-aponta-pesquisa-25554716.html), contra 2,5 milhões registradas no ano de 2021 — um aumento de 97%. Traduzindo em valores, os [golpes financeiros](https://www.estadao.com.br/economia/golpes-bancarios-geram-prejuizos-no-pais/) devem alcançar a marca de R$2,5 bilhões em 2022.

Dentra essas fraudes, aquelas envolvendo cartões de crédito são de grande relevância uma vez que a sua não-detecção acaretará em prejuízos consideráveis, tanto para o consumidor quanto para a instituição financeira.

Existe uma grande variedade de cenários que podem levar um fraudador a realizar com sucesso pagamentos fraudulentos com cartão de crédito. Atualmente, não há uma taxonomia definida sobre os tipos de fraude de cartão de crédito, embora se saiba que certos padrões ocorrem com mais frequência do que outros.

**É um jogo de gato e rato, onde os padrões fraudulentos mudam ao longo do tempo.**

Um outro fator a ser considerado é a quantidade de falsos positivos, ou seja, aquelas vezes em que você tentou fazer uma compra e teve seu cartão bloqueado preventivamente - o que provavelmente gerou estresse e constrangimento.

Por todos esses motivos, o investimento na área de detecção de fraudes por meio de Inteligência Artificial vem crescendo a cada ano, representando uma grande oportunidade em *Data Science*. 

Dispondo de grandes volumes de dados como base histórica, um algoritmo de machine learning apenas um pouco melhor que os anteriores já representa uma economia de milhões de Reais. E esse é o desafio, aprimorar cada vez mais o uso de algoritmos visando inibir ou evitar transações fraudulentas.

## **Sobre os dados**

Os dados usados neste projeto foram disponibilizados por algumas empresas européias de cartão de crédito. O [*dataset*](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) representa as operações financeiras que aconteceram no período de dois dias, onde foram classificadas 492 fraudes em meio a quase 290 mil transações.

Este é um conjunto de dados extremamente desbalanceado, onde as fraudes representam apenas 0,17% do total.

Outro detalhe interessante é que as *features* são todas numéricas, e foram descaracterizadas (por problemas ligados à privacidade e segurança). Assim, os nomes das colunas são representados por $[V1, V2, V3 \dots, V28]$

[Na página original dos dados](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud), também é informado que as variáveis passaram por uma transformação conhecida como Análise de Componentes Principais (*Principal Component Analysis* - PCA).

A PCA permite a redução da dimensionalidade enquanto mantém o maior número possível de informações. Para conseguir isso, o algoritmo encontra um conjunto novo de recursos - os chamados **componentes**.

Esses componentes são em número menor or igual às variáveis originais. No caso deste projeto, os componentes achados pela transformação da PCA são as próprias colunas $[V1, V2, V3 \dots, V28]$.

**Dicionário dos dados**

|Coluna|Descrição|
|------|---------|
|Time|Número de segundos decorridos entre a transação do registro atual e a primeira transação no conjunto de dados|
|V1 - V28|Pode ser resultado de uma redução de dimensionalidade do PCA para proteger identidades de usuários e recursos confidenciais|
|Amount|Valor da transação|
|Class|1 para transações fraudulentas, 0 caso contrário|