# 🗺️ Índice Geral de Estudos e Revisão — Machine Learning (ISLP)

Este índice conecta a teoria matemática, os exemplos numéricos e os códigos implementados nos notebooks.

---

## 📚 Módulos Teóricos e Práticos

### 1. Fundamentos e Avaliação
* [01. Dilema Viés-Variância (Bias-Variance Trade-Off)](docs/01_bias_variance_tradeoff.md)
  * O que é Viés e Variância
  * Erro Irredutível ($\sigma^2$)
  * Decomposição matemática do erro de teste

### 2. Regressão Linear
* [02. Regressão Linear Simples e OLS](docs/02_regressao_linear_simples_ols.md)
  * Minimização do RSS passo a passo
  * Por que a derivada é igualada a zero (curva convexa)
  * O que significa $\mathbb{E}[\cdot]$ e o estimador não-viesado
* [03. Regressão Linear Múltipla & Multicolinearidade](docs/03_regressao_linear_multipla.md)
  * Notação matricial: $\mathbf{y} = \mathbf{X}\boldsymbol{\beta} + \boldsymbol{\epsilon}$
  * Solução analítica (Equações Normais) vs. Numérica (SVD)
  * Multicolinearidade prática (dataset Diabetes)
* [04. Testes de Hipóteses: Teste t vs. Teste F](docs/04_testes_t_e_f.md)
  * Teste t para significância individual
  * Teste F para significância global
  * O risco dos múltiplos testes e o valor-$p$

### 3. Classificação
* [05. Regressão Logística, Sigmoide e o Número de Euler](docs/05_regressao_logistica_e_sigmoide.md)
  * Por que a regressão linear falha para probabilidade
  * O que é a constante de Euler ($e \approx 2{,}71828$)
  * Cálculo na mão da Sigmoide, Odds e Log-Odds
  * Máxima Verossimilhança (MLE) explicada com números
* [06. Matriz de Confusão, Limiar de Decisão e Curva ROC-AUC](docs/06_matriz_confusao_e_roc_auc.md)
  * Métricas calculadas passo a passo (Acurácia, Recall, Precisão)
  * O efeito de ajustar o limiar (0.50 vs 0.20)
  * O que a Curva ROC e a AUC realmente medem
* [07. Comparativo de Classificadores & Paradoxo de Simpson](docs/07_comparativo_classificadores.md)
  * Regressão Logística vs. LDA vs. QDA vs. KNN
  * O Paradoxo do Estudante (dataset Default)

---

## ⚡ Consulta Rápida
* [01_cheatsheet.md](01_cheatsheet.md): Resumo de fórmulas, siglas e termos-chave em uma página.
