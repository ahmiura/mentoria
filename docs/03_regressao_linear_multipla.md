# 03. Regressão Linear Múltipla & Multicolinearidade

## 1. Notação Matricial Compacta
$$\mathbf{y} = \mathbf{X}\boldsymbol{\beta} + \boldsymbol{\epsilon}$$

$$\begin{bmatrix} y_1 \\ y_2 \\ \vdots \\ y_n \end{bmatrix} = \begin{bmatrix} 1 & x_{11} & \dots & x_{1p} \\ 1 & x_{21} & \dots & x_{2p} \\ \vdots & \vdots & \ddots & \vdots \\ 1 & x_{n1} & \dots & x_{np} \end{bmatrix} \begin{bmatrix} \beta_0 \\ \beta_1 \\ \vdots \\ \beta_p \end{bmatrix} + \begin{bmatrix} \epsilon_1 \\ \epsilon_2 \\ \vdots \\ \epsilon_n \end{bmatrix}$$

* A primeira coluna de $1$ serve para multiplicar e ativar o intercepto $\beta_0$.
* Cada linha representa um paciente ou cliente.
* Cada coluna representa uma feature clínica ou financeira.

---

## 2. Como o Modelo Resolve a Equação?
1. **Solução Analítica (Equações Normais):**
   $$\hat{\boldsymbol{\beta}} = (\mathbf{X}^T \mathbf{X})^{-1} \mathbf{X}^T \mathbf{y}$$
   Inverter $\mathbf{X}^T \mathbf{X}$ custa $\mathcal{O}(p^3)$ e amplifica erros de arredondamento quando há colinearidade.
2. **Solução Numérica (SVD - Decomposição em Valores Singulares):**
   O scikit-learn usa $\mathbf{X} = \mathbf{U} \boldsymbol{\Sigma} \mathbf{V}^T$, calculando a pseudo-inversa de Moore-Penrose $\mathbf{X}^\dagger$. É muito mais estável numericamente.

---

## 3. O Caso da Multicolinearidade (Exemplo: Dataset Diabetes)
No dataset de Diabetes:
* `s5` (triglicerídeos) e `bmi` apresentam coeficientes positivos fortes ($\approx +695$ e $+531$).
* `s1` (colesterol total) aparece com coeficiente muito negativo ($\approx -918$), enquanto `s2` (LDL) é positivo.
* **Isso não significa que colesterol cura diabetes!** Significa que exames de sangue medem quase a mesma gordura (**multicolinearidade**); os coeficientes disputam peso matematicamente para equilibrar a conta.
