# 05. Regressão Logística, Função Sigmoide e o Número de Euler

## 1. A Sigmoide e a Constante de Euler
A Regressão Logística comprime a reta $z = \beta_0 + \beta_1 X_1 + \dots + \beta_p X_p$ em uma probabilidade contínua entre $0$ e $1$:

$$p(X) = \frac{1}{1 + e^{-z}} = \frac{e^z}{1 + e^z}$$

### A constante de Euler:
* Letra **$e$** é uma constante matemática fixa:
  $$\mathbf{e \approx 2{,}71828}$$
* $e^0 = 1$
* $e^1 \approx 2{,}71828$
* $e^{-5} = \frac{1}{e^5} \approx 0{,}0067$

---

## 2. Exemplo Numérico Passo a Passo (Cálculo na Mão)
Considere um modelo de crédito com:
* $\beta_0 = -10{,}5$
* $\beta_1 = 0{,}0055$ (peso por dólar de saldo devedor)

### Cliente A: Saldo devedor de $1.000$ dólares ($X = 1000$)
1. **Reta $z$:**
   $$z = -10{,}5 + (0{,}0055 \times 1000) = -10{,}5 + 5{,}5 = \mathbf{-5{,}0}$$
2. **Exponencial $e^z$:**
   $$e^{-5{,}0} = 2{,}71828^{-5} \approx 0{,}006737$$
3. **Sigmoide:**
   $$p = \frac{0{,}006737}{1 + 0{,}006737} \approx \mathbf{0{,}0067} \quad (\mathbf{0{,}67\%} \text{ de risco})$$

### Cliente B: Saldo devedor de $2.000$ dólares ($X = 2000$)
1. **Reta $z$:**
   $$z = -10{,}5 + (0{,}0055 \times 2000) = -10{,}5 + 11{,}0 = \mathbf{+0{,}5}$$
2. **Exponencial $e^z$:**
   $$e^{+0{,}5} = \sqrt{2{,}71828} \approx 1{,}6487$$
3. **Sigmoide:**
   $$p = \frac{1{,}6487}{1 + 1{,}6487} = \frac{1{,}6487}{2{,}6487} \approx \mathbf{0{,}622} \quad (\mathbf{62{,}2\%} \text{ de risco})$$

---

## 3. Máxima Verossimilhança (MLE) com Números
A regressão logística acha os betas maximizando a probabilidade conjunta dos acertos:
$$L(\boldsymbol{\beta}) = \prod_{\text{caloteiros}} p(x_i) \times \prod_{\text{adimplentes}} (1 - p(x_i))$$

Se tivermos 1 caloteiro real ($Y=1$) e 1 bom pagador ($Y=0$):
* Um modelo que prevê $p_1 = 0{,}90$ e $p_2 = 0{,}10$ tem $L = 0{,}90 \times (1 - 0{,}10) = \mathbf{0{,}81}$ (Acertou!).
* Um modelo que prevê $p_1 = 0{,}20$ e $p_2 = 0{,}80$ tem $L = 0{,}20 \times (1 - 0{,}80) = \mathbf{0{,}04}$ (Errou feio!).
