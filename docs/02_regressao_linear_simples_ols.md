# 02. Regressão Linear Simples: OLS, Derivadas e Intuição

## 1. O Modelo e o Resíduo
$$Y = \beta_0 + \beta_1 X + \epsilon$$
A previsão da reta é:
$$\hat{y}_i = \hat{\beta}_0 + \hat{\beta}_1 x_i$$

O resíduo (distância entre dado real e reta) é:
$$e_i = y_i - \hat{y}_i = y_i - (\beta_0 + \beta_1 x_i) = y_i - \beta_0 - \beta_1 x_i$$

---

## 2. Minimizando o RSS (Por que derivar e igualar a zero?)
O erro total acumulado ao quadrado é:
$$RSS = \sum_{i=1}^{n} (y_i - \beta_0 - \beta_1 x_i)^2$$

Essa função forma uma **parábola/bacia voltada para cima (curva convexa)**.
* No ponto mínimo (o fundo da bacia), a inclinação da reta tangente é plana: **inclinação zero**.
* Como a derivada mede a inclinação, encontramos o menor erro possível **igualando a derivada a zero**.

### A Derivada de $-\beta_0$ vira $-1$:
Na expressão interna $(y_i - \beta_0 - \beta_1 x_i)$:
* $y_i$ é constante $\to 0$.
* $-\beta_1 x_i$ é constante em relação a $\beta_0 \to 0$.
* $-\beta_0$ é o mesmo que $-1 \cdot \beta_0$, logo sua derivada é **$-1$**.

Pela regra da cadeia:
$$\frac{\partial RSS}{\partial \beta_0} = -2 \sum_{i=1}^{n} (y_i - \beta_0 - \beta_1 x_i) = 0$$

Dividindo por $-2n$:
$$\bar{y} - \beta_0 - \beta_1 \bar{x} = 0 \implies \mathbf{\hat{\beta}_0 = \bar{y} - \hat{\beta}_1 \bar{x}}$$

> A reta ajustada pelo OLS **sempre passa exatamente pelo ponto médio dos dados** $(\bar{x}, \bar{y})$.

---

## 3. Exemplo Prático com Números
Imagine 3 observações:
* $(x_1, y_1) = (1, 2)$
* $(x_2, y_2) = (2, 4)$
* $(x_3, y_3) = (3, 6)$

1. **Médias:**
   * $\bar{x} = (1 + 2 + 3) / 3 = 2$
   * $\bar{y} = (2 + 4 + 6) / 3 = 4$

2. **Cálculo de $\hat{\beta}_1$:**
   $$\hat{\beta}_1 = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sum (x_i - \bar{x})^2}$$

   | $i$ | $(x_i - \bar{x})$ | $(y_i - \bar{y})$ | Produto | $(x_i - \bar{x})^2$ |
   | :-: | :-: | :-: | :-: | :-: |
   | 1 | $1 - 2 = -1$ | $2 - 4 = -2$ | $(-1)(-2) = 2$ | $1$ |
   | 2 | $2 - 2 = 0$ | $4 - 4 = 0$ | $0$ | $0$ |
   | 3 | $3 - 2 = 1$ | $6 - 4 = 2$ | $1 \times 2 = 2$ | $1$ |
   | **Soma** | | | **4 (Numerador)** | **2 (Denominador)** |

   $$\hat{\beta}_1 = \frac{4}{2} = \mathbf{2}$$

3. **Cálculo de $\hat{\beta}_0$:**
   $$\hat{\beta}_0 = 4 - (2 \times 2) = \mathbf{0}$$

Equação final ajustada: $\mathbf{\hat{y} = 2x}$.
