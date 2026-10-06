# 04. Testes de Hipóteses: Teste t vs. Teste F

## 1. Teste t (Avaliação Individual)
* **Objetivo:** Avalia se uma variável específica $X_j$ tem relação com a resposta $Y$, mantendo as outras fixas.
* **Hipótese:** $H_0: eta_j = 0$ (não tem efeito).
* **Fórmula:**
  $$t = \frac{\hat{\beta}_j - 0}{\text{SE}(\hat{\beta}_j)}$$
* **Interpretação:** Divide a estimativa pelo seu erro padrão. Se $ert{}tert{}$ for grande e o $p	ext{-valor} < 0{,}05$, rejeita-se $H_0$ (a variável é relevante).

---

## 2. Teste F (Avaliação Conjunta Global)
* **Objetivo:** Avalia se **pelo menos um** dos preditores do modelo é útil.
* **Hipótese:** $H_0: eta_1 = eta_2 = \dots = eta_p = 0$ (nenhuma variável presta).
* **Fórmula:**
  $$F = \frac{(\text{TSS} - \text{RSS}) / p}{\text{RSS} / (n - p - 1)}$$

---

## 3. Por que precisamos do Teste F? (O Problema dos Múltiplos Testes)
Se você rodar um modelo com **100 variáveis inúteis** com nível de significância de $5\%$:
* É esperado que cerca de **5 variáveis pareçam significativas puramente por acaso** ($100 \times 0{,}05 = 5$).
* Se olhar apenas os testes t individuais, você cometerá falsas descobertas.
* O **Teste F** protege contra isso porque avalia o modelo inteiro de uma só vez.
