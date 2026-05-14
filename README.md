# Projeto de Machine Learning — Medical Cost Personal Dataset

## Sobre o Projeto

Este é  um projeto desenvolvido como uma atividade acadêmica para a disciplina de Computação em Nuvem, o foco foi em conceitos de Machine Learning e pré-processamento de dados.

O dataset escolhido foi o **Medical Cost Personal Dataset**, disponível no Kaggle, o site ao qual foi mencionado pelo professor para escolher o dataset para a atividade. O objetivo principal do projeto escolhido foi analisar e preparar os dados para aplicações de modelos de regressão, utilizando o algoritmo **Random Forest Regressor**, e o que foi ensinado em sala de aula.

---

## Dataset Utilizado

Dataset: **Medical Cost Personal Dataset**
Fonte: Kaggle
Link: https://www.kaggle.com/datasets/mirichoi0218/insurance
Objetivo: Prever os custos médicos (`charges`) com base em características dos pacientes.

### Variáveis do Dataset

| Coluna   | Descrição                      |
| -------- | ------------------------------ |
| age      | Idade do paciente              |
| sex      | Sexo                           |
| bmi      | Índice de massa corporal       |
| children | Quantidade de filhos           |
| smoker   | Indica se o paciente é fumante |
| region   | Região onde o paciente reside  |
| charges  | Custos médicos cobrados        |

---

# Etapas do Projeto

Como foi apresentado em aula, mas especificamente retirei esse sequecia de etapas **ex-04-imb**, que seriam:

    1.Análise dos Dados (EDA)
    2.Limpeza de Dados (coerção de TotalCharges + remoção de irrelevantes + imputação)
    3.Tratamento de Outliers
    4.Transformações Estatísticas (StandardScaler)
    5.Encoding de Variáveis Categóricas (mapeamento binário + One-Hot Encoding)
    6.Separação das Variáveis
    7.Divisão entre Treino e Teste

Embora, como notado, ouveram modificações em que a etapa '6.Seleção de Features' apresentado no dataset que me baseei (**ex-04-imb**), foram serparadas em duas etapas diferentes neste dataset. Além de não apresentar a etapa '7.Split do Dataset e Balanceamento com SMOTE', que não foi aplicada pois nesse projeto se trata de um problema de regressão. Como a variável alvo (**charges**) possui valores contínuos, o foco do pré-processamento foi direcionado ao tratamento de outliers, transformações estatísticas e divisão adequada entre treino e teste.

## 1. Análise Exploratória dos Dados (EDA)

Foi realizada uma análise inicial do dataset utilizando funções como:

```python
df.info()
df.describe()
df.hist()
```

Essa etapa nos permitiu visualizar:

* Tipos das variáveis;
* Distribuição dos dados;
* Presença de valores extremos;
* Estrutura geral do dataset.

---

## 2. Limpeza de Dados

Foi realizada a remoção de registros duplicados utilizando:

```python
df = df.drop_duplicates()
```

Também foi verificado se o dataset não possuía valores nulos.

---

## 3. Tratamento de Outliers

Os outliers foram identificados utilizando o método IQR (Interquartile Range).

```python
Q1 = df['charges'].quantile(0.25)
Q3 = df['charges'].quantile(0.75)
IQR = Q3 - Q1
```

Após a identificação, foi criada uma nova versão do dataset sem os valores considerados extremos.

---

## 4. Transformações Estatísticas

Foi aplicada uma transformação logarítmica na variável `charges` para reduzir a assimetria dos dados.

```python
df['charges_log'] = np.log1p(df['charges'])
```

Também foi utilizada a padronização dos dados com `StandardScaler`.

```python
scaler = StandardScaler()
```

---

## 5. Encoding de Variáveis Categóricas

As variáveis categóricas foram convertidas em variáveis numéricas utilizando One-Hot Encoding.

```python
df = pd.get_dummies(df, columns=['sex', 'smoker', 'region'], drop_first=True)
```

---

## 6. Separação das Variáveis

O dataset foi dividido entre:

* variáveis de entrada (`X`);
* variável alvo (`y`).

```python
X = df.drop(columns=['charges'])
y = df['charges']
```

---

## 7. Divisão entre Treino e Teste

Os dados foram separados em conjuntos de treino e teste.

```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

---

## Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Jupyter Notebook
* Git/GitHub

---

## Objetivo Final

O objetivo do projeto/atividade academica é aplicar técnicas de análise e preparação de dados para treinamento de modelos de Machine Learning capazes de prever custos médicos com base nas características dos pacientes.


