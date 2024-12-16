English description below:

Modelo de Classificação e Regressão com Árvores de Decisão e Random Forest

Eu criei este projeto para explorar e entender o funcionamento de modelos de classificação e regressão, utilizando técnicas de pré-processamento, 
otimização de hiperparâmetros e ensamble de modelos. Também realizei uma comparação entre duas abordagens para a criação de um ensemble: 

a abordagem manual utilizando o ShuffleSplit e a função built-in RandomForestRegressor do Scikit-learn.


Etapas do Processo

1. Criação de Pipelines
   
Eu utilizei o Pipeline do Scikit-learn para encadear várias etapas de processamento e modelagem:

Pré-processamento: 

Normalização com StandardScaler e redução de dimensionalidade com PCA.

Modelagem: 

Árvore de Decisão (DecisionTreeClassifier e DecisionTreeRegressor) e Random Forest (RandomForestRegressor), dependendo do tipo de problema (classificação ou regressão).
Usei pipelines, o que permite que as etapas sejam aplicadas de maneira consistente, sem risco de vazamento de dados (leakage).

2. Otimização de Hiperparâmetros
   
A otimização dos hiperparâmetros foi feita utilizando as técnicas de RandomizedSearchCV e GridSearchCV.

Essas técnicas ajudam a encontrar a melhor combinação de parâmetros para os modelos, garantindo uma maior performance.
Eu também ajustei a quantidade de componentes principais do PCA, a profundidade das árvores e outras variáveis importantes para o treinamento dos modelos.

3. Validação Cruzada e ShuffleSplit
   
Para treinar os modelos de maneira robusta, utilizei o ShuffleSplit, que realiza a validação cruzada embaralhando os dados e dividindo-os em subconjuntos de treino e teste. 
Durante esse processo, treinei o modelo em múltiplas iterações e combinei as predições de cada iteração para criar um ensemble de modelos. 
Isso foi feito utilizando a técnica de votação por moda.

4. Comparação com RandomForestRegressor
   
Em seguida, fiz uma comparação entre a técnica de ensemble manual (com o uso do ShuffleSplit) e a abordagem built-in do Scikit-learn, utilizando o RandomForestRegressor. 
Embora o processo de ShuffleSplit me dê maior controle sobre a combinação dos modelos, o RandomForestRegressor oferece uma solução mais prática e otimizada, 
já que a criação do ensemble é feita automaticamente.

5. Resultados e Desempenho
   
Por fim, calculei o erro médio quadrático (MSE) para avaliar a performance dos modelos.
Com a técnica de ShuffleSplit, obtive um MSE consideravelmente alto em comparação com o RandomForestRegressor,
mas o processo manual de ensemble me deu uma visão mais clara sobre como essas técnicas podem ser combinadas para melhorar a previsão.



Classification and Regression Model with Decision Trees and Random Forest

I created this project to explore and understand the functioning of classification and regression models, using preprocessing techniques,
hyperparameter optimization, and model ensembling. I also performed a comparison between two approaches for creating an ensemble: 

the manual approach using ShuffleSplit and the built-in RandomForestRegressor function from Scikit-learn.

Process Steps

1. Pipeline Creation
   
I used Scikit-learn’s Pipeline to chain multiple processing and modeling steps:

Preprocessing:

Normalization with StandardScaler and dimensionality reduction with PCA.

Modeling:

Decision Tree (DecisionTreeClassifier and DecisionTreeRegressor) and Random Forest (RandomForestRegressor), depending on the problem type (classification or regression).
I used pipelines, which allow the steps to be applied consistently, without the risk of data leakage.

2. Hyperparameter Optimization
   
Hyperparameter optimization was performed using RandomizedSearchCV and GridSearchCV techniques.

These techniques help find the best parameter combination for the models, ensuring better performance.
I also adjusted the number of principal components in PCA, the depth of the trees, and other important variables for model training.

3. Cross-validation and ShuffleSplit
   
To train the models robustly, I used ShuffleSplit, which performs cross-validation by shuffling the data and splitting it into training and test subsets.
During this process, I trained the model in multiple iterations and combined the predictions from each iteration to create an ensemble of models.
This was done using the voting-by-mode technique.

4. Comparison with RandomForestRegressor
   
Next, I compared the manual ensemble technique (using ShuffleSplit) with the built-in Scikit-learn approach using RandomForestRegressor.
While the ShuffleSplit process gives me more control over the model combination, RandomForestRegressor offers a more practical and optimized solution, 
as the ensemble creation is done automatically.

5. Results and Performance
   
Finally, I calculated the Mean Squared Error (MSE) to evaluate the performance of the models.
With the ShuffleSplit technique, I obtained a considerably higher MSE compared to RandomForestRegressor,
but the manual ensemble process gave me a clearer understanding of how these techniques can be combined to improve predictions.
