# Projeto de Machine Learning — Medical Cost Personal Dataset

## Informações Aluno
Nome: Thiago Maicky Alves Martins

RA: 4201028

## Sobre o Projeto

Este é  um projeto desenvolvido como uma atividade acadêmica para a disciplina de Computação em Nuvem, o foco foi em conceitos de Machine Learning e pré-processamento de dados.

O dataset escolhido foi o **Medical Cost Personal Dataset**, disponível no Kaggle, o site ao qual foi mencionado pelo professor para escolher o dataset para a atividade. O objetivo principal do projeto escolhido foi analisar e preparar os dados para aplicações de modelos de regressão, utilizando o algoritmo **Random Forest Regressor**, e o que foi ensinado em sala de aula.

---

## Dataset Utilizado

Dataset: **Medical Cost Personal Dataset**

Fonte: Kaggle

Link: https://www.kaggle.com/datasets/mirichoi0218/insurance

Objetivo: Prever os custos médicos (`charges`) com base em características dos pacientes.


## Objetivos do Projeto

Realizar análise exploratória dos dados (EDA)

Aplicar técnicas de limpeza e tratamento de dados

Trabalhar com tratamento de outliers

Aplicar transformações estatísticas

Utilizar pipelines de pré-processamento

Transformar variáveis categóricas em numéricas

Separar os dados entre treino e teste

Preparar os dados para Machine Learning

Visualizar correlações entre as variáveis

O dataset contém informações de pacientes e seus respectivos custos médicos.

## Análise Exploratória (EDA)

Foi realizada uma análise inicial do dataset utilizando:

df.info()

df.describe()

histogramas

boxplots

heatmaps de correlação

Essa etapa ajudou a compreender melhor a distribuição dos dados e possíveis padrões existentes.

## Limpeza de Dados

Durante a limpeza:

Registros duplicados foram removidos;

Os tipos das colunas foram analisados;

Foi feita a verificação de valores nulos.

O dataset apresentou boa qualidade e não possuía valores ausentes.

## Tratamento de Outliers

Os outliers foram identificados utilizando o método:

IQR (Interquartile Range)

Também foram utilizados boxplots para visualizar os valores extremos da variável charges.

## Transformações Estatísticas

Foi aplicado:

Transformação logarítmica em charges;

Normalização com StandardScaler;

Análise gráfica após as transformações.

Essas técnicas ajudam a melhorar a distribuição dos dados e facilitar o treinamento do modelo.

## Pré-processamento com Pipeline

Foi utilizado:

Pipeline

ColumnTransformer

OneHotEncoder

StandardScaler

Essa abordagem automatiza o pré-processamento dos dados e evita problemas como data leakage.

# Split do Dataset

Os dados foram separados em: 80% para treinamento e os 20% restantes para teste

Utilizando:

train_test_split()

## Análise de Correlação

Ao final do pré-processamento, foi gerada uma matriz de correlação para analisar a relação entre as variáveis e o target (charges).

Foi possível perceber que variáveis como:

smoker

age

bmi

possuem impacto relevante nos custos médicos.

## Objetivo Final

O objetivo do projeto é aplicar técnicas de análise e preparação de dados para treinamento de modelos de Machine Learning capazes de prever custos médicos com base nas características dos pacientes.

