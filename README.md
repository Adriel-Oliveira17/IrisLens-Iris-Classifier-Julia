# Classificação de Espécies de Íris com MLJ em Julia

![Julia](https://img.shields.io/badge/Julia-1.11.5-9558B2?style=flat-square&logo=julia&logoColor=white)
![MLJ](https://img.shields.io/badge/Framework-MLJ.jl-389826?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

Pipeline completo de Machine Learning desenvolvido em Julia para a classificação automatizada das três espécies do dataset Iris (*setosa*, *versicolor* e *virginica*). O projeto utiliza a biblioteca MLJ.jl e algoritmos de Árvores de Decisão, cobrindo todo o ciclo desde o pré-processamento estratificado até o cálculo de métricas de avaliação e inferência em lote.

---

## Sumário

- [Visão Geral](#visão-geral)
- [Tecnologias e Bibliotecas](#tecnologias-e-bibliotecas)
- [Estrutura do Pipeline](#estrutura-do-pipeline)
- [Desempenho e Métricas](#desempenho-e-métricas)
- [Inferência em Novas Amostras](#inferência-em-novas-amostras)
- [Instalação e Execução](#instalação-e-execução)
- [Estrutura do Repositório](#estrutura-do-repositório)
- [Como Enviar para o GitHub](#como-enviar-para-o-github)
- [Licença](#licença)

---

## Visão Geral

Este repositório serve como referência prática de boas práticas de Data Science e Machine Learning na linguagem Julia. Ele aborda:

- Manipulação de dados estruturados com `DataFrames.jl`.
- Particionamento estatisticamente controlado (divisão treino/teste estratificada).
- Treinamento e ajuste de hiperparâmetros com `DecisionTree.jl` via interface `MLJ.jl`.
- Implementação de métricas customizadas de avaliação por classe (Precisão, Recall e Acurácia Global).

---

## Tecnologias e Bibliotecas

| Tecnologias | Descrição / Função |
| :--- | :--- |
| **Julia 1.11.5** | Linguagem de alto desempenho para computação científica |
| **MLJ.jl** | Framework unificado de Machine Learning em Julia |
| **DataFrames.jl** | Estruturação e manipulação de conjuntos de dados |
| **DecisionTree.jl** | Algoritmo de classificação baseado em Árvore de Decisão |
| **CategoricalArrays.jl** | Tratamento de variáveis categóricas |

---

## Estrutura do Pipeline

```text
[ Dataset Iris ] ---> [ Partitioning (80/20 Stratified) ] ---> [ DecisionTreeClassifier ]
                                                                      |
                                                                      v
[ Inferência em Novas Amostras ] <--- [ Avaliação de Métricas ] <--- [ Predict Mode ]
