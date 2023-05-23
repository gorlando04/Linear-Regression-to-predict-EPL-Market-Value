# Linear-Regression-to-predict-EPL-Market-Value


## English Premier League Market Value Prediction

Este projeto tem como objetivo realizar uma regressão linear em um conjunto de dados. O conjunt que será utilizado será o epldata_final.csv, que é referente a informações sobre jogadores e seus valores de mercado. Os jogadores do conjunto pertencem a premier-league na temporada 17-18.

O interessante desta análise e que poderemos compreender como estavam dispostos os valores naquela época e entender como isto mudou atualmente.

Todos os dados e informações reais, que serão adicionadas à este projeto serão retirados do transfermaket, um site que possui diversas informações sobre futebol

![Screenshot from 2023-05-22 18-05-47](https://github.com/gorlando04/Linear-Regression-to-predict-EPL-Market-Value/assets/91696970/4e8bfc15-75c6-4601-bb2d-f0d612757e01)


## Conjunto de dados

Para obter o conjunto de dados foi utilizado a plataforma KAggle que disponibiliza diversos conjuntos de dados. O conjunto de dados está disponível neste repositório para facilitar as coisas.

O conjunto de dados possui diversos atributos, alguns relevantes outros nem tanto. Assim foi necessário realizar uma vistoria nestes atributos para entendê-los.

![Screenshot from 2023-05-22 18-07-28](https://github.com/gorlando04/Linear-Regression-to-predict-EPL-Market-Value/assets/91696970/5c8ddce0-25a6-4c94-86e4-b9d8cd238197)


Estes eram os atributos, e eles possuiam diversos tipos de dados diferentes, ou seja, strings, inteiros, reais, etc… Logo seria necessário lidar com essa diferença, já que na regrssão os dados precisavam ser numéricos.

No conjunto de dados os jogadores dos seguintes times estavam disponíveis

![Screenshot from 2023-05-22 18-08-34](https://github.com/gorlando04/Linear-Regression-to-predict-EPL-Market-Value/assets/91696970/bb84d299-9102-461a-b103-0a26ec55cd6f)


## Atributos

Como exisitiam diversos no conjunto de dados, nesta página inicial, será mostrado apenas o atributo alvo, que erá o valor de mercado, e como ele estava disposto.

![Screenshot from 2023-05-22 18-09-48](https://github.com/gorlando04/Linear-Regression-to-predict-EPL-Market-Value/assets/91696970/ec844702-dab8-4d54-a2a9-366272e05623)


Pode-se perceber que a maioria dos valores estava entre 0 e 20 milhões, oque é esperado visto que jogadores mas valiosos são algo mais raro de acontecer, entretanto, como podemos ver, eles existem.

## Pré-processamento

Após a verificação dos atributos, foi necessário realizar o pré-processamento dos dados. Tratamos valores nulos, verificamos outliers, transformamos tipos de dados, normalização, etc…

Tudo isto foi feito para garantir que o conjunto de dados possuise integridade dos dados e evitasse que o modelo recebesse como entrada dados insignificantes e que possuísem incoerências.

Além disso, foi realizado o cálculo da correlação para verificar atributos redundantes que poderiam ser retirados. FOi estabelecido um limite para a retirada com base na correlação. Na tabela abaixo podemos entender o que os valores de correalação podem representar.

![Screenshot from 2023-05-22 18-12-51](https://github.com/gorlando04/Linear-Regression-to-predict-EPL-Market-Value/assets/91696970/b501c388-f230-4b1b-bec8-f6778bf0a6ca)


## Regressão Linear

Finalmente, iniciou-se a regressão linear do conjunto de dados. Inicialmente foi utilizado apenas um modelo com diferentes estratégias do conjunto de dados, ou seja, com diferentes atributos, para que fosse possível entender como os atributos estavam influenciando a regressão.

A estratégia que melhor se comportou foi a utilização do conjunto de dados por inteiro mesmo, obtendo um R2-SCORE de 0.72 que foi um bom valor.

![Screenshot from 2023-05-22 18-15-06](https://github.com/gorlando04/Linear-Regression-to-predict-EPL-Market-Value/assets/91696970/7c5c5635-05d2-4903-98f0-21ff3ce738b7)


Além disso foi explicado como funciona o R2-SCORE. Essa medidade mede a disposição de todos os pontos ao redor da reta de regressão ajustada. Esta medida também é chamada de coeficiente de determinação. Para um conjunto de dados, valores maiores de R2 representam menores diferenças observadas entre os dados observados com a reta ajustada. É interessante notar que os possíveis valores para R2 vão de 0 à 1.

Assim, um R2-SCORE de 0 representa que um modelo não é capaz de explicar nenhum variação dos dados nas variáveis do conjunto de dados. Já, um R2-SCORE DE 1 demostra um modelo que representa todas as variações relacionadas a variação das médias, o que também não é tão interessante já que pode indicar overfitting.

## Combinação de modelos

Após a interpretação dos resultados, foi entendido que o modelo talvez pudesse melhorar. Para isso foi utilizado a combinação de modelos que é uma estratégia muito interessante que permite unir modelos de forma que o resultado seja melhorado. Para isso algumas restrições existem, mas felizmente o nosso problema contemplava todas essas restrições.

Ao realizar a combinação, encontrou-se que a melhor estratégia de dataset era a que um atiributo (fpl_points) era retirado. Então desta maneira inicou-se a verificação de como o número de iterações de combinação influenciavam no resultado.

![Screenshot from 2023-05-22 18-18-29](https://github.com/gorlando04/Linear-Regression-to-predict-EPL-Market-Value/assets/91696970/de2b2e93-747f-4471-8d86-36db69dc5052)


No final, pode-se construir o gráfico abaixo, e verificar que o R2-SCORE não foi tão afetado pelo nro de iteração mas o erro quadrático foi.

![Screenshot from 2023-05-22 18-18-43](https://github.com/gorlando04/Linear-Regression-to-predict-EPL-Market-Value/assets/91696970/2de522b8-1671-407d-bc4f-d5b2ec0b88ad)


## Adicional

Além da regressão foi realizada a construção de um gráfico que continha informações do mundo real em comparação com este conjunto de dados. O gráfico continha o preço dos 10 jogadores mais valiosos da PL 17/18 até o presente momento, 2023. Com isso foi interessante perceber a curva de valor dos jogadores e entender como foi o seu valor de mercado ao longo do tempo.

![Screenshot from 2023-05-22 18-20-32](https://github.com/gorlando04/Linear-Regression-to-predict-EPL-Market-Value/assets/91696970/69f8d7c4-5f8f-4a20-ae00-63d7b73be014)



## Conclusão

Este projeto apresenta inicialmente um análise dos atributos visando identificar as características deles e entender como estão dispostos no conjunto de dados, para conseguir torná-los aceitáveis para serem utilizados em modelos estatísticos. Para se realizar esta tarefa, foi realizado cálculos de correlação, vistoria de valores nulos, análise de distribuição estatísitcias em outros métodos.

Após isso, inicou-se a fase de verificar a relação dos atributos com a variável alvo, para entender se alguma variável era muito explicativa, podendo ser utilizada como única. Infelizmente isso não foi possível, já que individualmente as variavéis não agregavam muitas informações para prever o preço de um jogador.

Em seguida, foi realizada uma rápida normalização utilizando MinMaxScaler, para deixar todos os atributos padronizados para evitar qualquer problema em relação a desbalanceamento nos valores dos atributos.

Em seguida iniciou-se a primeira regressão linear, em que se foi testada algumas hipóteses em relação ao conjunto de dados, e como as mudanças iriam afetar no resultado da regressão. COnsequentemente, os resultados foram analisados, focando no valor do R2-SCORE e como poderiámos interpretá-lo.

EM seguida, houve a tentativa de se combinar modelos de regressão para melhorar a qualidade da predição.

Desta maneira, entende-se que mesmo que a combinação seja uma ferramenta muito poderosa para alavancar modelos, em relação ao R2 não houve tanta mudança, mas o erro quadrático, que era o objetivo à ser minimizado na combinação melhorou em relação a primeira regressão realizada. LOgo foi possível compreender um pouco como os jogadores da primeira divisão da inglaterra estavam dispostos.

FInalmente, foi realizado um adicional no trabalho, analisando os valores de mercado dos jogadores ao longos dos anos. Isto foi realizado apenas para o top-10 jogadores da liga. COm isto foi interessante verificar quais jogadores se mantiveram no topo e quais acabaram perdendo muito valor.
