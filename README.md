# Projeto de Classificação do Tipo de Clima

O objetivo deste projeto de ciência de dados é **classificar o tipo de clima** com base em dados meteorológicos sintéticos utilizando **Aprendizagem de Máquina Supervisionada** e a metodologia **CRISP-DM**. O modelo busca prever se o clima será: **Chuvoso**, **Ensolarado**, **Nublado** ou **Nevando**.

-----

## 1\. Compreensão do Negócio

  - **Nome do Dataset**: Classificação do tipo de clima

  - **Estrutura**: O conjunto de dados é composto por 11 colunas, incluindo:

      - `Temperature`: Temperatura em graus Celsius
      - `Humidity`: Umidade relativa do ar (%)
      - `Wind Speed`: Velocidade do vento
      - `Precipitation (%)`: Probabilidade de precipitação
      - `Cloud Cover`: Nível de cobertura de nuvens
      - `Atmospheric Pressure`: Pressão atmosférica
      - `UV Index`: Índice de radiação ultravioleta
      - `Season`: Estação do ano
      - `Visibility (km)`: Visibilidade em quilômetros
      - `Location`: Local de coleta dos dados
      - `Weather Type`: Variável alvo (Chuva, Sol, Nublado, Nevando)

  - **Objetivo**: Classificar o clima em quatro categorias: **Chuvoso**, **Ensolarado**, **Nublado** ou **Nevando**.

  - **Metodologia**: Utilização de modelo de aprendizagem supervisionada para classificação.

  - **Público-alvo**: Estudantes, serviços de previsão do tempo, indústria agrícola e o público em geral.

  - **Critério de sucesso**: Acurácia de no mínimo 90%.

  - **Limitação**: Por se tratar de dados sintéticos, o estudo pode apresentar viés.

  - **Link do dataset**: [Weather Type Classification](https://www.kaggle.com/datasets/nikhil7280/weather-type-classification)

-----

## 2\. Preparação dos Dados

Nesta etapa, os dados foram limpos e processados para garantir a qualidade do modelo.

  - **Tratamento de Outliers**: Valores de umidade acima de 100 foram removidos. Outliers em outras colunas (`Wind Speed`, `Precipitation (%)`, `Visibility (km)`) foram tratados usando a técnica de **Intervalo Interquartil (IQR)**.
  - **Limpeza**: Dados duplicados e nulos foram removidos.
  - **Engenharia de Features**: Colunas categóricas (`Cloud Cover`, `Season`, `Location`, `Weather Type`) foram convertidas para valores numéricos usando `LabelEncoder`.

O conjunto de dados, que originalmente tinha 13.200 linhas, foi reduzido para **12.088 linhas** após a limpeza e o tratamento de outliers.

-----

## 3\. Modelagem e Treinamento

Foram testados cinco algoritmos de classificação supervisionada para encontrar o melhor desempenho. O conjunto de dados foi dividido em **70% para treinamento** e **30% para teste**.

  - **Algoritmos testados**:
      - `RandomForestClassifier`
      - `DecisionTreeClassifier`
      - `GaussianNB`
      - `GradientBoostingClassifier`
      - `SVM (Support Vector Machine)`

-----

## 4\. Avaliação e Resultados

O desempenho dos modelos foi medido pela métrica de **acurácia** e os resultados foram os seguintes:

  - **Modelo Vencedor**: O `RandomForestClassifier` apresentou a melhor performance.
  - **Resultado**: O modelo alcançou uma acurácia de **94%**, superando o critério de sucesso do projeto de 90%.
  - **Matriz de Confusão**:
    ```
    [[875  22   7  15]
     [ 36 818   7  20]
     [ 26  15 832  22]
     [ 31  10  13 878]]
    ```

-----

## 5\. Conclusão

O `RandomForestClassifier` se mostrou um modelo robusto e eficaz para a classificação do clima. Com uma acurácia de 94%, ele atende e supera as expectativas do projeto, demonstrando seu potencial para aplicações práticas em previsão do tempo.
