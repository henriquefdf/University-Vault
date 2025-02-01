A **classificação** é uma tarefa do **aprendizado supervisionado**, onde o objetivo é identificar a qual **classe** um determinado dado pertence, com base em **dados rotulados**.

**Exemplo:** Dado um conjunto de imagens de **gatos e cachorros**, um **modelo de classificação** pode aprender a identificar corretamente novas imagens.

---

## 1. Características do Problema de Classificação

✅ **Entrada**: Um conjunto de exemplos de treinamento com **rótulos conhecidos**.  
✅ **Saída**: Um modelo que classifica **novos exemplos** em uma das categorias aprendidas.  
✅ **Fases do Aprendizado**:
   - **Treinamento**: O modelo aprende a partir dos dados rotulados.
   - **Teste**: O modelo é avaliado em dados **não vistos**.

### 🔹 **Exemplo Prático**
| Nome               | Bilheteria | Avaliação | Gênero      |
|--------------------|-----------|-----------|------------|
| Toy Story         | 10.6       | 9         | Animação   |
| Se eu fosse você  | 30         | 8.7       | Comédia    |
| Cidade de Deus    | 12         | 8.2       | Drama      |
| Juno             | 7          | 7         | Comédia    |
| Divertidamente    | 30         | 9.4       | Animação   |

O modelo pode aprender regras como:  
**SE** avaliação > 8.9 **ENTÃO** gênero = 'Animação'.  

Quando um novo filme surge (ex: **"Se Beber Não Case"** com bilheteria **12** e avaliação **7.6**), o modelo tentará classificá-lo corretamente.

---

## 2. Tipos de Modelos de Classificação

Os **modelos de classificação** podem ser divididos em:

✅ **Modelos compreensíveis ("White Box")**  
   - **Árvores de Decisão** → Criam regras de decisão.  
   - **Regras de Associação** → Descobrem padrões explícitos.  
   - **Redes Bayesianas** → Baseiam-se em probabilidades.

✅ **Modelos "Caixa-Preta" ("Black Box")**  
   - **SVM (Support Vector Machines)** → Separação entre classes por hiperplanos.  
   - **Redes Neurais** → Modelos altamente não lineares.  
   - **KNN (K-Nearest Neighbors)** → Classificação baseada na proximidade dos vizinhos.

---

## 3. Algoritmo **K-Nearest Neighbors (KNN)**

📌 **Características**:
- Algoritmo **preguiçoso** (Lazy Learning) → Apenas armazena os dados e classifica quando necessário.
- Classifica um novo ponto com base na classe dos **K vizinhos mais próximos**.

📌 **Funcionamento**:
1. Calcula a **distância** entre o novo exemplo e os exemplos do conjunto de treinamento.
2. Encontra os **K vizinhos mais próximos**.
3. A classe mais frequente entre os vizinhos define a classificação.

📌 **Escolha do valor de K**:
- **K muito pequeno** → Pode levar a **overfitting** (ajuste excessivo aos dados).  
- **K muito grande** → Pode levar a **underfitting** (generalização ruim).  

💡 **Dica:** Em conjuntos desbalanceados, pode ser necessário usar **votação ponderada**, onde vizinhos mais próximos têm maior peso na decisão.

---

## 4. Avaliação de Modelos de Classificação

A **avaliação** de classificadores é essencial para medir sua **eficácia**.

✅ **Matriz de Confusão**  
A matriz de confusão mostra a relação entre **previsões corretas e incorretas**.

| Classe Real  | Predição Positiva | Predição Negativa |
|-------------|------------------|------------------|
| **Positiva** (C1) | **VP** (Verdadeiros Positivos) | **FN** (Falsos Negativos) |
| **Negativa** (C2) | **FP** (Falsos Positivos) | **VN** (Verdadeiros Negativos) |

📌 **Métricas principais**:
- **Acurácia**: Proporção de exemplos classificados corretamente.  
  $$
  Acurácia = \frac{VP + VN}{VP + FP + VN + FN}
  $$

- **Precisão**: % de previsões positivas que realmente pertencem à classe positiva.  
  $$
  Precisão = \frac{VP}{VP + FP}
  $$

- **Revocação (Recall)**: % dos exemplos positivos que foram corretamente classificados.  
  $$
  Revocação = \frac{VP}{VP + FN}
  $$

- **F1-Score**: Média harmônica entre **precisão** e **revocação**.  
  $$
  F1 = 2 \times \frac{\text{Precisão} \times \text{Revocação}}{\text{Precisão} + \text{Revocação}}
  $$

---

## 5. Problema das Classes Desbalanceadas

💡 **Exemplo:**  
- Suponha um classificador para **câncer** onde:  
  - **4 pacientes** têm câncer.  
  - **500 pacientes** não têm câncer.  
  - O modelo acerta **454 negativos**, mas erra **todos os positivos**.

Apesar da **acurácia de 90%**, o modelo é **péssimo** para identificar casos de câncer.

✅ **Solução:** Usar **precisão, recall e F1-score** para avaliar melhor o desempenho.

---

## 6. Resumo Geral

📌 **Classificação**:
- O **problema** de atribuir rótulos a objetos com base em **dados conhecidos**.
- **Fases**: Treinamento (modelo aprende) e Teste (modelo é avaliado).

📌 **Modelos mais comuns**:
- **Árvores de Decisão**, **KNN**, **SVM**, **Redes Neurais**.

📌 **Avaliação de Modelos**:
- **Acurácia** → Classificações corretas / total.  
- **Precisão** → Quantos positivos previstos realmente são positivos.  
- **Recall** → Quantos exemplos positivos foram corretamente previstos.  
- **F1-Score** → Combinação de precisão e recall.  
