# ⚡ Cheatsheet: Fórmulas e Termos-Chave

| Conceito / Termo | Notação / Fórmula | Em Português Claro | O que checar na prática |
| :--- | :--- | :--- | :--- |
| **Esperança Matemática** | $\mathbb{E}[X]$ | Média teórica a longo prazo caso o experimento se repetisse infinitas vezes. | Se $\mathbb{E}[\epsilon] = 0$, o modelo não tem vício sistemático para cima nem para baixo. |
| **Resíduo (Erro)** | $e_i = y_i - \hat{y}_i$ | A diferença entre o valor real observado e a previsão da reta. | A distribuição dos resíduos deve ser simétrica e centrada no zero. |
| **Soma Residual Quadrática (RSS)** | $\sum (y_i - \hat{\beta}_0 - \hat{\beta}_1 x_i)^2$ | Soma de todos os erros ao quadrado. | O OLS minimiza essa soma derivando e igualando a zero (fundo da bacia). |
| **Número de Euler** | $e \approx 2{,}71828$ | Base dos logaritmos naturais; constante matemática fixa. | Usado no expoente da sigmoide ($e^z$ ou `np.exp(z)`). |
| **Sigmoide (Logística)** | $p(X) = \frac{1}{1 + e^{-z}}$ | Esmagador matemático que converte valores reais $(-\infty, +\infty)$ em $(0, 1)$. | Transforma o score da reta em uma probabilidade real válida entre 0% e 100%. |
| **Odds (Chances)** | $\frac{p}{1 - p}$ | Razão entre a probabilidade de ocorrer e a de não ocorrer. | $p = 0{,}8 \implies \text{Odds} = 4$ (4 chances a favor contra 1 contra). |
| **Odds Ratio** | $e^{\beta_j}$ | Fator que multiplica as chances quando a variável $X_j$ sobe 1 unidade. | Se $e^{\beta} > 1$, aumenta o risco/chance; se $< 1$, reduz. |
| **Teste t** | $t = \frac{\hat{\beta}_j}{\text{SE}(\hat{\beta}_j)}$ | Teste de significância de **uma variável isolada**. | Se $p\text{-valor} < 0{,}05$, a variável é estatisticamente relevante. |
| **Teste F** | $F = \frac{(\text{TSS} - \text{RSS})/p}{\text{RSS}/(n - p - 1)}$ | Teste de significância de **todo o conjunto de variáveis**. | Se $F \gg 1$ e $p\text{-valor} < 0{,}05$, pelo menos uma variável tem impacto real. |
| **Recall (Sensibilidade)** | $\frac{\text{VP}}{\text{VP} + \text{FN}}$ | De todos os casos positivos reais, quantos o modelo conseguiu capturar? | Crítico em risco/doença/fraude; maximiza-se baixando o limiar de corte. |
| **Precisão** | $\frac{\text{VP}}{\text{VP} + \text{FP}}$ | Quando o modelo tocou o alarme, quantas vezes ele estava certo? | Mede o custo operacional do alarme falso. |
| **ROC-AUC** | Área sob a curva ROC | Capacidade do modelo de ranquear clientes de maior risco acima dos de menor risco. | Varia de $0{,}50$ (chute) a $1{,}00$ (perfeito); acima de $0{,}90$ é excelente. |
