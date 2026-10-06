# 06. Matriz de Confusão, Limiar de Decisão e Curva ROC-AUC

## 1. As 4 Células da Matriz de Confusão
| | Previu: Não Inadimplente (0) | Previu: Inadimplente (1) |
| :--- | :---: | :---: |
| **Real: Não Inadimplente (0)** | **Verdadeiro Negativo (VN)** | **Falso Positivo (FP)** (Alarme Falso) |
| **Real: Inadimplente (1)** | **Falso Negativo (FN)** (Prejuízo!) | **Verdadeiro Positivo (VP)** (Detecção Correta) |

---

## 2. Fórmulas com Exemplo Numérico
Considere: $VN = 2400$, $FP = 15$, $FN = 55$, $VP = 30$ (Total = 2500):

1. **Acurácia:**
   $$\text{Acurácia} = \frac{VN + VP}{\text{Total}} = \frac{2400 + 30}{2500} = \mathbf{97{,}2\%}$$
   > *Enganosa:* Deixamos escapar 55 dos 85 caloteiros reais!
2. **Recall / Sensibilidade (Quantos caloteiros reais pegamos?):**
   $$\text{Recall} = \frac{VP}{VP + FN} = \frac{30}{30 + 55} = \frac{30}{85} = \mathbf{35{,}3\%}$$
3. **Precisão (Quando tocamos o alarme, ele estava certo?):**
   $$\text{Precisão} = \frac{VP}{VP + FP} = \frac{30}{30 + 15} = \frac{30}{45} = \mathbf{66{,}7\%}$$

---

## 3. O Efeito do Limiar de Corte (Threshold)
* **Limiar padrão (0.50):** Só acusa risco se a probabilidade passar de 50%. Deixa passar muitos caloteiros ($Recall \approx 35\%$).
* **Limiar conservador (0.20):** Se tiver mais de 20% de risco, já acusa. O **Recall sobe para > 70%**, capturando a maioria dos devedores ao custo de alguns alarmes falsos.

---

## 4. Curva ROC e Métrica AUC
* A curva ROC testa **todos os limiares de corte possíveis de 0 a 1** plotando Recall (Y) vs. Falso Positivo (X).
* **AUC = 0.50:** Chute aleatório (jogar moeda).
* **AUC = 1.00:** Ranqueamento perfeito.
