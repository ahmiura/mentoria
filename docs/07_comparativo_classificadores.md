# 07. Comparativo de Classificadores & Paradoxo de Simpson

## 1. Famílias de Classificadores (ISLP Cap. 4)
* **Regressão Logística:** Não assume que as features sejam normais; modela diretamente a probabilidade via combinação linear.
* **LDA (Linear Discriminant Analysis):** Assume que as classes vêm de distribuições Gaussianas que compartilham a **mesma matriz de covariância**. Gera fronteiras lineares.
* **QDA (Quadratic Discriminant Analysis):** Permite que cada classe tenha sua **própria covariância**. Gera fronteiras parabólicas/curvas (mais flexível).
* **KNN (K-Nearest Neighbors):** Não paramétrico; classifica por votação dos $K$ vizinhos mais próximos. Sofre com a maldição da dimensionalidade.

---

## 2. O Paradoxo do Estudante (Paradoxo de Simpson)
No dataset `Default`:
1. **Regressão Univariada (apenas `student`):**
   O coeficiente é **positivo** (estudantes no geral atrasam mais faturas que não estudantes).
2. **Regressão Múltipla (`student` + `balance`):**
   O coeficiente de `student` vira **negativo** ($e^\beta < 1$).

### Por que isso acontece?
* Estudantes carregam dívidas maiores de cartão em média.
* Mas ao comparar **um estudante e um não estudante com o mesmo saldo devedor exato** (ex.: ambos devendo $1.500$), o estudante tem **menor risco de calote**.
* Modelos multivariados evitam conclusões enganosas de análises univariadas isoladas.
