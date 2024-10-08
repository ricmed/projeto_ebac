# Projeto: Modelo de Previsão de Óbitos por Leptospirose

Dados provenientes do SINAN Estadual

Painel do SINAN: https://ricmed-painelsinan.streamlit.app/

Análise feita: https://github.com/ricmed/projeto_ebac/blob/main/trata_dados.ipynb

A doença apresenta elevada incidência em determinadas áreas além do risco de letalidade, que pode chegar a 40% nos casos mais graves. Sua ocorrência está relacionada às condições precárias de infraestrutura sanitária e alta infestação de roedores infectados. 
Por isso se faz necessária políticas públicas de controle desta doença, além de ferramentas que possam ajudar a identificar pessoas com mais riscos de vir a óbito.

## 1. Coleta de Dados
- Dados anonimizados provenientes do DATASUS, referentes ao Estado de Pará.
- Arquivo .dbf chamado NINDINET foi convertido para .csv

## 2. Modelagem
- Foram filtrados somente os registros de leptospirose
- Valores nulos foram identificados e tratados.
  - Foram identificadas e excluídas colunas com 100% de valores nulos.
  - Colunas com poucos valores nulos tiveram suas linhas correspondentes excluídas.
  - Demais colunas categóricas com valores nulos, foi criada uma classe Sem Informação para esses casos.
- Foi criada uma coluna de quantidade de dias a partir das colunas referentes a data de ínicio dos sintomas e a data de registro da notificação, data que pode ser considerada como a data em que o paciente foi a unidade de saúde.
- Foram eliminadas colunas que não poderiam contribuir com a análise.
- Foi utilizada a técnica de one-hot encoder para criar variávéis dummies a partir de vaviáveis categóricas.
- Foi utilizada a técnica de label encoder para codificar a variável FAIXA_ETARIA.
- Foram testados os seguintes algorítmos: Regressão Logistica, Random Forest AdaBoost e XGBoost, com as classes desbalanceadas, com aplicação Oversampling e com aplicação de Undersampling

## 3. Conclusões
- Nenhum dos modelos criados conseguiu prever a classe minoritária de forma satisfatória
- Somente over ou under sampling não foi suficiente para os modelos performarem de forma apropriada
- Os dados são de díficil análise e classificação
- Sugestão de aplicar ténicas mais refinadas para tratamento de classes desbalanceadas




