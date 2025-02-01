Os **Processos de Decisão de Markov (MDPs)** são usados para modelar agentes que tomam **decisões sequenciais** em ambientes incertos, onde cada ação influencia estados futuros. Eles são amplamente utilizados em **Aprendizado por Reforço (Reinforcement Learning)**.

---

## 1. Tomada de Decisão

### 🔹 Problema
- Um agente está em um **estado** e pode escolher entre várias **ações**.
- Seu objetivo é escolher a **ação que maximiza a recompensa acumulada**.

Existem dois tipos principais de tomada de decisão:
1. **Decisão única ("single-shot")**: Problema dos **Multi-Armed Bandits**.
2. **Decisão sequencial**: Modelada por **Processos de Decisão de Markov (MDPs)**.

---

## 2. Multi-Armed Bandits

Um **Multi-Armed Bandit** é uma metáfora para um agente que precisa decidir entre várias opções desconhecidas.

### 🔹 Características
- Cada **alavanca** de uma máquina caça-níquel dá um **recompensa aleatória** com **média e variância diferentes**.
- O agente deve decidir **quando explorar novas opções** e **quando explorar a melhor opção conhecida** (**dilema exploração x exploração**).

### 🔹 Estratégias
1. **ε-greedy**:  
   - Com probabilidade **ε**, escolhe uma ação aleatória (exploração).  
   - Com probabilidade **1 - ε**, escolhe a ação de maior recompensa (exploração).

2. **Upper Confidence Bound (UCB)**:  
   - Escolhe a ação com maior **média + variância**, equilibrando exploração e exploração.

---

## 3. Processos de Decisão de Markov (MDPs)

Os **MDPs** são modelos matemáticos usados para representar decisões sequenciais sob incerteza.

### 🔹 **Propriedade de Markov**
A **transição de estado** depende apenas do **estado atual** e da **ação tomada**, **não dos estados passados**.

$$
P(s' | s, a) = T(s, a, s')
$$

### 🔹 **Definição Formal**
Um **MDP** é definido como um **tupla** ⟨S, A, T, R⟩:
- **S**: Conjunto de **estados**.
- **A**: Conjunto de **ações**.
- **T**: **Função de transição** → Probabilidade de chegar ao estado **s'** ao tomar a ação **a** no estado **s**:
  
  $$
  T(s,a,s') = P(s' | s,a)
  $$

- **R**: **Função de recompensa** → Recompensa recebida ao estar no estado **s**:

  $$
  R(s)
  $$

### 🔹 **Exemplo: Mundo 4x3**
- **Estados (S)**: { (1,1), (1,2), ..., (4,3) }.
- **Ações (A)**: { Cima, Baixo, Esquerda, Direita }.
- **Recompensas (R)**:
  - +1 no estado (4,3).
  - -1 no estado (4,2).
  - -0.04 nos demais estados.

---

## 4. Recompensas Acumuladas e Descontadas

Ao longo do tempo, um agente **acumula recompensas** à medida que interage com o ambiente.

### 🔹 **Recompensa Cumulativa**
Para um horizonte **finito** (T passos), a recompensa acumulada é:

$$
G_t = R_{t+1} + R_{t+2} + ... + R_T
$$

### 🔹 **Recompensa Descontada**
Para um horizonte **infinito**, recompensas futuras são **penalizadas** por um **fator de desconto γ**:

$$
G_t = R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + ...
$$

- **γ (fator de desconto)**:  
  - **γ → 0** → O agente **só valoriza recompensas imediatas**.  
  - **γ → 1** → O agente **valoriza também recompensas futuras**.

---

## 5. Políticas de Decisão

Uma **política** π define o comportamento do agente.

- **Definição**: Mapeia estados para ações.
  $$
  a = \pi(s)
  $$
- **Objetivo**: Encontrar a **política ótima** π* que maximiza a recompensa ao longo do tempo.

### 🔹 **Exemplo de Política**
- Se o agente segue a política:
  - **π(s) = direita** no estado (1,1).
  - **π(s) = cima** no estado (2,1).
  - ...
  
  Isso define uma estratégia para navegar no ambiente.

---

## 6. Função de Valor

A **função de valor** mede a **qualidade de um estado** a longo prazo.

- **Definição**: O valor de um estado **s** é a soma esperada das recompensas descontadas ao seguir a política π:

  $$
  V^\pi(s) = \mathbb{E} \left[ \sum_{t=0}^{\infty} \gamma^t R(s_t) \mid s_0 = s \right]
  $$

### 🔹 **Equação de Bellman**
A função de valor pode ser definida **recursivamente**:

$$
V^\pi(s) = R(s) + \gamma \sum_{s'} P(s' | s, \pi(s)) V^\pi(s')
$$

Isso permite calcular valores de estados **de maneira iterativa**.

---

## 7. Políticas e Funções de Valor Ótimas

A **política ótima** é aquela que **maximiza a função de valor**:

$$
V^*(s) = \max_a \sum_{s'} P(s' | s, a) [ R(s) + \gamma V^*(s') ]
$$

- A política ótima **π*** é obtida escolhendo **sempre a melhor ação**.
- Essa equação é conhecida como a **Equação da Otimalidade de Bellman**.

---

## 8. Programação Dinâmica para Resolver MDPs

Se conhecemos a função de transição **T(s, a, s')** e a função de recompensa **R(s)**, podemos encontrar a política ótima com **Programação Dinâmica**.

### 🔹 Métodos de Programação Dinâmica
1. **Iteração de Valor (Value Iteration)**  
   - Inicia com valores aleatórios e atualiza iterativamente usando a **Equação de Bellman**.
   - Converge para **V*** e **π***.

2. **Iteração de Política (Policy Iteration)**  
   - Alterna entre **avaliação da política** e **melhoria da política**.
   - Garante convergência para a política ótima.

---

## 9. Iteração de Valor

O algoritmo de **Value Iteration** funciona da seguinte forma:

1. Inicializa **V(s)** aleatoriamente para todos os estados.
2. Para cada estado **s**, aplica a **Equação da Otimalidade de Bellman**:
   
   $$
   V(s) \leftarrow \max_a \sum_{s'} P(s' | s, a) [ R(s) + \gamma V(s') ]
   $$

3. Repete até que **as mudanças sejam pequenas** (abaixo de um limite).

---

# Conclusão

Os **Processos de Decisão de Markov (MDPs)** são fundamentais para a modelagem de **decisões sequenciais**. Eles fornecem um arcabouço matemático para **agentes que aprendem a agir em ambientes incertos**.

✅ **Modelam problemas de decisão sob incerteza**  
✅ **Usam recompensas descontadas para avaliar estratégias**  
✅ **Podem ser resolvidos via Programação Dinâmica**  