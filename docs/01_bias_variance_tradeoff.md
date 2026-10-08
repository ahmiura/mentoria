# 01. Dilema Viés-Variância (Bias-Variance Trade-Off)

## 1. A Decomposição do Erro de Teste
O Erro Quadrático Médio esperado em dados novos (teste) se divide em 3 parcelas:
$$\mathbb{E}(y_0 - \hat{f}(x_0))^2 = \text{Var}(\hat{f}(x_0)) + [\text{Bias}(\hat{f}(x_0))]^2 + \text{Var}(\epsilon)$$

* **Viés (Bias):** Erro de simplificar uma realidade complexa por um modelo rígido demais (ex.: passar uma reta onde o padrão é uma curva). Gera **Underfitting**.
* **Variância (Variance):** Sensibilidade do modelo às oscilações do treino. Se mudar um dado e o modelo mudar completamente de forma, a variância é alta. Gera **Overfitting**.
* **Erro Irredutível ($\text{Var}(\epsilon) = \sigma^2$):** Ruído inerente ao fenômeno que nenhuma feature consegue prever.

---

## 2. A Gangorra da Flexibilidade
* Modelos rígidos (ex.: Regressão Linear simples): **Alto Viés**, **Baixa Variância**.
* Modelos hiperflexíveis (ex.: KNN com $K=1$, Splines com muitos nós): **Baixo Viés**, **Alta Variância**.
* **Objetivo:** Achar o vale da curva em "U" do erro de teste onde a soma de Viés² e Variância é mínima.
