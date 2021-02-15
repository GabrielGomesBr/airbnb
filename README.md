# airbnb

# Como foi a definição da estratégia de modelagem?
O problema pode ser tratado tanto como um problema de regressão quanto como um problema de classificação. Devido a fins de simplicidade, tratei o problema como um de regressão, principalmente por não conhecer as regras de negócio (aplicação final do modelo) que me auxiliariam a transformar o problema em um de classificação. Após isso, realizei algumas limpezas e alterações nos dados e realizei algumas conversões de features, transformando algumas textuais para categóricas com one hot encoding. A partir disso, defini um modelo simples para ser utilizado como baseline. Escolhi a regressão linear (no algoritmo rigde regressor que penaliza coeficientes grandes) porque ela não sofre com o problema de alta dimensionalidade, fazendo com que o meu feature extraction e o meu feature selection não precisasse ser muito complexo. Então, selecionei um modelo mais complexo e otimizei seus parâmetros. Para finalizar, fiz um feature importance que me permitiria melhorar ainda mais os modelos no futuro.

# Como foi definida a função de custo a ser utilizada?
Como o problema foi tratado como um de regressão, utilizei a métrica $$R^2$$, que explica em termos percentuais a variância (informação) explicada pelo modelo. Todavia, poderiam ter sido utilizadas funções de custo que pudessem fazer mais sentido ao negócio, como erro médio percentual. 

# Qual foi o critério utilizado na seleção do modelo final?
Como o tempo que eu possuia para fazer o teste era limitado (pela duração do teste e pelo tempo que eu possuia para realizá-lo), escolhi um modelo baseado em ensemble que pudesse ter um desempenho razoável sem grandes complexidades de parametrização e pudesse ser otimizado utilizando o sklearn optmizer. Todavia, modelos diferentes poderiam ter sido testados como SVM e redes neurais. Porém, acredito que a grande chave deste problema, como da maioria dos problemas de dados, se encontra no feature selections e extraction.

# Qual foi o critério utilizado para validação do modelo? Por que escolheu utilizar este método?
Para validação do modelo foi utilizada validação cruzada com 5 folds, sendo 4 para treinamento e um para validação, ou seja 80 % treinamento e 20 % validação. Escolhi esse método por ser robusto e prover resultados razoáveis sem grandes parametrizações, sendo um bom método para criar um modelo inicial e um baseline.

# Quais evidências você possui de que seu modelo é suficientemente bom?
O modelo capturou apenas 40 % da variância dos dados, o que indica que ele não é suficientemente bom. Todavia, ele foi capaz de aprender, mostrando que ele é promissor para realizar a tarefa. Porém, por mais que a pergunta seja focada no modelo, acredito que a grande sacada para este problema esteja na extração de características. Diversas outras informações poderiam ter sido utilizadas, como:

* Informações textuais, como análise de sentimentos;
* Utilizar dados temporais;
* Detalhar melhor e utilizar as informações contidas em amenities.

