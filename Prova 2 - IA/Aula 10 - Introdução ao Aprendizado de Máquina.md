O **Aprendizado de Máquina (Machine Learning - ML)** é uma subárea da **Inteligência Artificial (IA)** que permite que computadores aprendam **a partir de dados**, sem serem explicitamente programados. Esse conceito foi introduzido por **Arthur Samuel (IBM) em 1959**.

---

## 1. Tipos de Aprendizado

Existem três principais paradigmas de aprendizado:

1. **Aprendizado Supervisionado** → Aprende a partir de **dados rotulados**.  
2. **Aprendizado Não Supervisionado** → Aprende a partir de **dados não rotulados**.  
3. **Aprendizado por Reforço** → Aprende **pela interação com o ambiente**, recebendo **recompensas**.

---

# 2. Aprendizado Supervisionado

No **aprendizado supervisionado**, o modelo é treinado com **dados rotulados**, ou seja, para cada entrada há uma **saída esperada**. Ele aprende a **mapear entradas (X) para saídas (Y)**.

**Objetivo**: Estimar uma função que relacione **entradas e saídas**, permitindo fazer previsões em novos exemplos.

## 🔹 Exemplo:
Previsão do **preço de um apartamento** com base em:
- **X1**: Localização
- **X2**: Tamanho em m²
- **X3**: Número de vagas

O modelo aprende a prever o **preço do imóvel (Y)** com base nesses atributos.

### 📌 Principais Tarefas:
✅ **Regressão** → Quando a saída **Y** é contínua (ex: prever preços).  
✅ **Classificação** → Quando a saída **Y** é categórica (ex: prever se um e-mail é spam ou não).

### 🔹 Modelos comuns:
- **Regressão Linear** (para regressão).
- **Árvores de Decisão** (para classificação e regressão).
- **Redes Neurais** (usadas em diversas aplicações).

---

# 3. Aprendizado Não Supervisionado

No **aprendizado não supervisionado**, os dados **não possuem rótulos**. O objetivo é **descobrir padrões nos dados**.

**Objetivo**: Identificar **estruturas ocultas** nos dados sem informações explícitas sobre a saída.

## 🔹 Exemplo:
Agrupar apartamentos com base em:
- **X1**: Localização
- **X2**: Tamanho em m²
- **X3**: Número de vagas

O modelo pode agrupar imóveis **similares** sem saber seus preços.

### 📌 Principais Tarefas:
✅ **Agrupamento (Clustering)** → Segmentação de clientes, organização de documentos.  
✅ **Detecção de Anomalias** → Identificação de fraudes bancárias.  
✅ **Regras de Associação** → Descoberta de padrões (ex: produtos comprados juntos no supermercado).

### 🔹 Algoritmos comuns:
- **K-Means** (para agrupamento).
- **DBSCAN** (para detecção de anomalias).
- **Apriori** (para regras de associação).

---

# 4. Comparação: Supervisionado vs Não Supervisionado

|         ==**Supervisionado**==          |       ==**Não Supervisionado**==       |
| :-------------------------------------: | :------------------------------------: |
|         Dados possuem rótulos.          |     Dados **não** possuem rótulos.     |
| Aprende a prever uma saída específica.  |     Aprende a identificar padrões.     |
| Exemplos: **Regressão, Classificação**. | Exemplos: **Agrupamento, Associação**. |

---

# 5. Aprendizado por Reforço

No **Aprendizado por Reforço (Reinforcement Learning - RL)**, o agente aprende **pela interação com o ambiente** e recebe **recompensas** conforme suas ações.

**Origem**: Formalizado por **Sutton & Barto na década de 1980**.

## 🔹 Características:
- Normalmente, o ambiente é modelado como um **Processo de Decisão de Markov (MDP)**.
- **O agente não conhece a função de transição e as recompensas a priori**.
- O aprendizado ocorre **por tentativa e erro**, ajustando as estratégias com base nas recompensas.

## 🔹 Exemplo:
Um **carro autônomo** aprende a **evitar colisões** ao dirigir em um ambiente simulado. Ele:
- Recebe **+1 ponto** por completar o trajeto sem bater.
- Recebe **-1 ponto** ao colidir.

### 📌 Elementos principais:
✅ **Estado (S)** → Representação do ambiente.  
✅ **Ação (A)** → Escolha do agente em cada estado.  
✅ **Recompensa (R)** → Feedback positivo ou negativo.  

---

# 6. Algoritmo Q-Learning (Aprendizado por Reforço)

O **Q-Learning** é um dos principais algoritmos de Aprendizado por Reforço.

**Objetivo**: Estimar a **função Q(s, a)**, que representa o valor de executar uma ação **a** em um estado **s**.

A atualização dos valores **Q(s, a)** segue a equação de Bellman:

$$
Q(s, a) \leftarrow Q(s, a) + \alpha \left[ R + \gamma \max_{a'} Q(s', a') - Q(s, a) \right]
$$

Onde:
- **α (taxa de aprendizado)**: Controle da atualização dos valores.
- **γ (fator de desconto)**: Quanto mais **γ** → mais valoriza **recompensas futuras**.
- **R** → Recompensa imediata recebida após tomar a ação.

---

# 7. Aplicações do Aprendizado de Máquina

✅ **Diagnóstico Médico** (classificação de doenças).  
✅ **Detecção de Fraudes** (análise de anomalias).  
✅ **Previsão Financeira** (regressão para prever preços de ações).  
✅ **Robótica** (aprendizado por reforço para movimentação autônoma).  
✅ **Processamento de Linguagem Natural (NLP)** (tradução automática, chatbots).  

---

# 8. Conclusão

O **Aprendizado de Máquina** é um dos pilares da Inteligência Artificial, permitindo a construção de **modelos preditivos** e **agentes autônomos**.

✅ **Aprendizado Supervisionado** → Usa **dados rotulados** para **classificação** e **regressão**.  
✅ **Aprendizado Não Supervisionado** → Descobre **padrões ocultos** sem rótulos.  
✅ **Aprendizado por Reforço** → Aprende com **recompensas e penalidades**.  