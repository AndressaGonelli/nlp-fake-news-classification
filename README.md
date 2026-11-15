# Classificação de Fake News com NLP

Atividade prática da disciplina de **Natural Language Processing (NLP)** do curso de **Ciência de Dados da UNINTER**.

Este projeto implementa um classificador supervisionado de notícias em português, utilizando o corpus [Fake.br](https://github.com/roneysco/Fake.br-Corpus) para distinguir notícias **REAL** (verdadeiras) e **FAKE** (falsas).

## Objetivo

Preparar as notícias, treinar e avaliar um modelo de classificação e gerar duas nuvens de palavras ponderadas por TF-IDF, uma para cada classe.

## Metodologia

1. Download do corpus Fake.br: **7.200 notícias**, organizadas em **3.600 pares** REAL/FAKE.
2. Associação de arquivos pelo identificador de cada par.
3. Normalização do comprimento dos textos dentro de cada par, para reduzir o efeito do tamanho sobre a classificação.
4. Pré-processamento com **NLTK**: conversão para minúsculas, tokenização e remoção de stopwords, pontuação, números e tokens de um caractere.
5. Separação de **75% para treinamento** e **25% para teste**, mantendo os pares no mesmo conjunto.
6. Extração de características com **TF-IDF** e **unigramas, bigramas e trigramas**.
7. Treinamento do classificador supervisionado **LinearSVC** e avaliação no conjunto de teste.
8. Geração de nuvens de palavras para cada classe a partir dos pesos TF-IDF.

## Resultados da execução registrada

| Métrica | Resultado |
| --- | ---: |
| Notícias no corpus | 7.200 |
| Notícias de treinamento | 5.400 |
| Notícias de teste | 1.800 |
| Acurácia no teste | **92,94%** |
| Unigramas distintos em REAL | 19.008 |
| Bigramas distintos em REAL | 35.338 |
| Trigramas distintos em REAL | 14.434 |
| Unigramas distintos em FAKE | 19.668 |
| Bigramas distintos em FAKE | 37.054 |
| Trigramas distintos em FAKE | 14.055 |

As contagens de n-gramas consideram os termos distintos presentes nos textos de treinamento de cada classe e representados no vocabulário TF-IDF. Um mesmo termo pode aparecer nas duas classes.

A acurácia é referente à divisão de treino/teste registrada no notebook, não a uma avaliação em notícias externas ao corpus.

## Como executar

Abra o notebook [NLP_FakeBr_Atividade_Pratica_4880041.ipynb](./NLP_FakeBr_Atividade_Pratica_4880041.ipynb) no **Google Colab** e execute as células em sequência, de cima para baixo. O notebook instala as dependências Python e obtém o corpus por meio do repositório original.

As bibliotecas utilizadas incluem **Python, NLTK, scikit-learn, pandas, NumPy, Matplotlib** e **WordCloud**.

## Fonte dos dados

- [Fake.br-Corpus — repositório de origem](https://github.com/roneysco/Fake.br-Corpus)

O corpus é baixado durante a execução e **não é redistribuído neste repositório**.

## Autoria

**Andressa Gonelli Ribeiro** — RU 4880041
