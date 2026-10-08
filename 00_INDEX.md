# 🗺️ Índice Geral de Estudos e Revisão — Machine Learning (ISLP)

Este índice conecta a teoria matemática, os exemplos numéricos e os códigos implementados nos notebooks.

---

## 📚 Módulos Teóricos e Práticos

### 1. Fundamentos e Avaliação
* [01. Dilema Viés-Variância (Bias-Variance Trade-Off)](docs/01_bias_variance_tradeoff.md)
  * O que é Viés e Variância
  * Erro Irredutível ($\sigma^2$)
  * Decomposição matemática do erro de teste
* [Complexidade_O.ipynb](Complexidade_O.ipynb): Notação Big-O e custo computacional de treino vs. inferência em ML.
* [cap1_ISLP.ipynb](cap1_ISLP.ipynb) e [cap2_ISLP.ipynb](cap2_ISLP.ipynb): Fundamentos estatísticos do ISLP.

### 2. Regressão Linear & Diagnóstico
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
* **Notebooks:**
  * [notebooks/01_regressao_linear.ipynb](notebooks/01_regressao_linear.ipynb): Implementação de regressão simples e múltipla no dataset Diabetes.
  * [cap3_ISLP.ipynb](cap3_ISLP.ipynb): Resumo didático e prático do Capítulo 3.

### 3. Seleção de Modelos & Regularização (ISLP Cap. 6)
* **Notebook:** [notebooks/exercicio_regressao_linear_regularizacao.ipynb](notebooks/exercicio_regressao_linear_regularizacao.ipynb)
  * Seleção de subconjuntos: Sequential Feature Selector (Backward SFS).
  * Encolhimento de coeficientes (*Shrinkage*): Ridge ($L_2$) e Lasso ($L_1$).
  * Sintonia de $\alpha$ por Validação Cruzada (`RidgeCV` e `LassoCV`).
  * Visualização de **Caminhos de Regularização (*Regularization Paths*)**.
  * Combate à multicolinearidade (`s1` vs `s2`) e avaliação 5-Fold K-Fold.

### 4. Classificação & Decisão Operacional (ISLP Cap. 4)
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
* **Notebook:** [notebooks/02_regressao_logistica.ipynb](notebooks/02_regressao_logistica.ipynb): Estudo completo em Python com dados reais de crédito.

### 5. Modelos Baseados em Árvores & Ensembles (ISLP Cap. 8)
* **Notebook:** [notebooks/03_arvores_e_ensembles.ipynb](notebooks/03_arvores_e_ensembles.ipynb)
  * Árvore de Decisão Individual: partição recursiva e diagnóstico de variância.
  * Bagging ($m = p$): agregação por bootstrap para redução de variância.
  * Random Forest ($m < p$): descorrelação de preditores a cada nó ($m \approx \sqrt{p}$).
  * Gradient Boosting: aprendizado sequencial (*slow learning*), sintonia de taxa de aprendizado e curva de erro.
  * Importância das Variáveis (*Feature Importance*) no dataset California Housing.

---

## ⚡ Consulta Rápida
* [01_cheatsheet.md](01_cheatsheet.md): Resumo de fórmulas, siglas e termos-chave em uma página.
