# Detecção de Fraudes em Cartões de Crédito com Machine Learning

Projeto desenvolvido em Python para identificar transações fraudulentas em cartões de crédito utilizando algoritmos de Machine Learning.

O objetivo é analisar padrões de transações financeiras, comparar diferentes modelos de classificação e avaliar estratégias para melhorar a identificação de fraudes em conjuntos de dados altamente desbalanceados.

## Objetivos

- Analisar e compreender os dados de transações financeiras.
- Identificar o desequilíbrio entre transações legítimas e fraudulentas.
- Desenvolver modelos de classificação utilizando Machine Learning.
- Comparar o desempenho de diferentes algoritmos.
- Aplicar técnicas de otimização de hiperparâmetros.
- Interpretar as previsões utilizando Feature Importance e SHAP.
- Avaliar diferentes limiares de classificação para melhorar a detecção de fraudes.

## Tecnologias e bibliotecas utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- SHAP
- Google Colab

## Base de dados

Foi utilizado o conjunto de dados Credit Card Fraud Detection, disponibilizado publicamente.

**Fonte:** [Credit Card Fraud Detection Dataset](https://storage.googleapis.com/download.tensorflow.org/data/creditcard.csv)

O conjunto possui 284.807 transações, distribuídas em duas classes:

- Classe 0: transações legítimas.
- Classe 1: transações fraudulentas.

A base apresenta forte desequilíbrio entre as classes, com aproximadamente 99,83% de transações legítimas e 0,17% de fraudulentas.

As variáveis V1 a V28 correspondem a componentes resultantes de uma transformação PCA, enquanto Time e Amount representam informações relacionadas ao tempo e ao valor das transações.

## Modelos desenvolvidos

Foram implementados e comparados quatro cenários:

1. Regressão Logística.
2. Random Forest.
3. Random Forest com otimização de hiperparâmetros utilizando GridSearchCV.
4. XGBoost.

Também foram utilizadas técnicas de balanceamento por pesos de classe e ajuste do limiar de classificação.

## Análise e interpretabilidade

O projeto contempla:

- Análise exploratória dos dados.
- Verificação de valores ausentes.
- Análise da distribuição das classes.
- Transformação logarítmica da variável Amount.
- Padronização das variáveis na Regressão Logística.
- Comparação de métricas de classificação.
- Matrizes de confusão.
- Curvas ROC e Precision-Recall.
- Análise de importância das variáveis.
- Interpretabilidade com SHAP.
- Otimização e validação do limiar de classificação.

## Resultados obtidos

O Random Forest original apresentou os melhores resultados em Precision, F1-Score e PR-AUC entre os modelos comparados utilizando os limiares padrão.

Após a análise dos diferentes limiares, foi selecionado o valor de 0,30 para a avaliação final.

### Desempenho final do Random Forest

| Métrica | Resultado |
|---|---:|
| Precision | 93,18% |
| Recall | 83,67% |
| F1-Score | 88,17% |

### Matriz de confusão

| Resultado | Quantidade |
|---|---:|
| Verdadeiros positivos | 82 |
| Verdadeiros negativos | 56.858 |
| Falsos positivos | 6 |
| Falsos negativos | 16 |

O modelo identificou corretamente 82 das 98 transações fraudulentas presentes no conjunto de teste.

**Observação metodológica:** o conjunto de teste foi utilizado em análises exploratórias anteriores à avaliação final. Portanto, os resultados devem ser interpretados com essa limitação em mente, não constituindo uma avaliação completamente independente.

## Estrutura do projeto

```text
deteccao-de-fraudes/
│
├── deteccao_de_fraudes_cartao_credito.ipynb
│
└── README.md
```

## Como executar

1. Clone este repositório:

```bash
git clone https://github.com/pprg1101/deteccao-de-fraudes.git
```

2. Acesse o diretório:

```bash
cd deteccao-de-fraudes
```

3. Instale as bibliotecas necessárias:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost shap
```

4. Abra o notebook no Google Colab ou em um ambiente Jupyter.

5. Execute as células na ordem apresentada.

A base de dados é carregada diretamente de sua fonte pública durante a execução do notebook.

## Considerações finais

Este projeto demonstra a aplicação de técnicas de Machine Learning na identificação de transações financeiras potencialmente fraudulentas.

O desenvolvimento permitiu explorar diferentes algoritmos, compreender os desafios de conjuntos de dados desbalanceados e aplicar técnicas de avaliação e interpretabilidade.

Os resultados evidenciam a importância de selecionar métricas e limiares adequados ao problema, especialmente quando falsos positivos e falsos negativos possuem impactos distintos.

---

**Desenvolvido como projeto de estudo em Python e Machine Learning.**
