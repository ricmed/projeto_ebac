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
  - Foram identificadas e excluídas colunas com 100% de valores nulos
  - Colunas com poucos valores nulos tiveram suas linhas correspondentes excluídas
  - Demais colunas com valores nulos foram imputadas utilizando o KNNImputer





