O estudo do **raciocínio probabilístico** na Inteligência Artificial (IA) trata da forma como agentes lidam com a **incerteza** em suas percepções e decisões. Essa incerteza ocorre devido a **informações parciais, dinâmicas ou imperfeitas** do ambiente. O uso da **teoria das probabilidades** permite modelar essa incerteza e construir sistemas inteligentes mais eficientes.

---

## 1. Quantificando a Incerteza

Agentes inteligentes operam sob **graus de crença**, atualizados conforme novas evidências.

### 🔹 Teoria das Probabilidades
- Atribui um **valor numérico (0 a 1)** ao grau de crença do agente sobre determinado evento.
- **Probabilidade a priori (Prior)**: estimativa inicial antes de qualquer observação.
- **Probabilidade a posteriori (Posterior)**: crença revisada após novas evidências.

### 🔹 Exemplo
- Antes de observar nuvens: **P(Chuva) = 0.3**
- Após ver nuvens escuras: **P(Chuva | Nuvens) = 0.7**

---

## 2. Decisão Racional

Um agente racional deve tomar decisões baseadas em:
1. **Função de utilidade** – representa as preferências do agente.
2. **Probabilidades** – mede a chance de um evento ocorrer.

### 🔹 Utilidade Esperada
$$
EU(a) = \sum P(resultado | ação) \times U(resultado)
$$

### 🔹 Exemplo
- P(Chuva | Nuvens) = **0.7**
- Levar um guarda-chuva tem um pequeno custo (-1), mas não levar pode causar grande prejuízo (-10).
- **A melhor decisão é levar o guarda-chuva.**

---

## 3. Revisão de Conceitos de Probabilidades

- **Espaço amostral (Ω)**: conjunto de todos os resultados possíveis.
- Exemplo:
  - **Moeda:** Ω = {cara, coroa}, P(cara) = 0.5.
  - **Dois dados:** Ω = {11, 12, ..., 66}, P(dupla de números iguais) = 6/36.

### 🔹 Variáveis Aleatórias
- **Booleanas:** Gripe = {true, false}.
- **Discretas:** Tempo = {ensolarado, nublado, chuvoso}.
- **Contínuas:** Sensor = [0,1].

---

## 4. Probabilidade Condicional e Regra de Bayes

A **probabilidade condicional** mede a chance de um evento ocorrer **dado que outro evento já aconteceu**:

$$
P(A | B) = \frac{P(A \cap B)}{P(B)}
$$

A **Regra de Bayes** permite inferir a **causa mais provável**:

$$
P(H | E) = \frac{P(E | H) P(H)}{P(E)}
$$

### 🔹 Exemplo: Diagnóstico Médico
- **P(Meningite) = 1/50.000**
- **P(Pescoço duro | Meningite) = 0.5**
- **P(Pescoço duro) = 1/20**
- Aplicando Bayes, **P(Meningite | Pescoço duro) ≈ 0.002 (0.2%)**.

---

## 5. Independência e Independência Condicional

- **Eventos independentes:** quando um evento não afeta a probabilidade do outro.

$$
P(A \cap B) = P(A) P(B)
$$

- **Independência condicional:** dois eventos podem ser independentes **se uma terceira variável for conhecida**.

### 🔹 Exemplo
- Febre e tosse são **condicionalmente independentes** dado que a pessoa tem gripe.

---

## 6. Processos de Inferência Temporal

Quando um ambiente **muda ao longo do tempo**, o agente deve atualizar suas crenças constantemente.

- **Variáveis de estado (Xₜ)** representam o ambiente.
- **Variáveis de evidência (Eₜ)** representam observações.

### 🔹 Exemplo
- Um guarda subterrâneo observa **se o diretor carrega um guarda-chuva** para inferir **se está chovendo**.

---

## 7. Cadeias de Markov

- **Princípio de Markov**: o estado atual **depende apenas do estado anterior**.
- **Cadeias de Markov** são utilizadas para modelar transições entre estados ao longo do tempo.

---

## 8. Técnicas de Inferência em Modelos Temporais

1. **Filtragem**: estimar o estado atual **com base em todas as observações passadas**.
2. **Predição**: prever estados futuros **com base em evidências passadas**.
3. **Suavização**: inferir estados passados **considerando evidências futuras**.
4. **Explicação mais provável**: encontrar a **sequência de estados mais provável**.

---

## 9. Modelos Específicos para Inferência Temporal

- **Modelos Ocultos de Markov (HMM)**: usados quando há estados ocultos.
- **Filtros de Kalman**: aplicáveis a variáveis contínuas.
- **Filtros de Partículas**: métodos de estimativa por amostragem.

---

## 10. Filtragem Bayesiana

A **Filtragem Bayesiana** permite atualizar crenças ao longo do tempo:

$$
P(X_t | e_{1:t}) = \alpha P(e_t | X_t) \sum P(X_t | X_{t-1}) P(X_{t-1} | e_{1:t-1})
$$

Onde:
- **P(X_t | e_{1:t})**: crença sobre o estado atual.
- **P(e_t | X_t)**: modelo de observação.
- **P(X_t | X_{t-1})**: modelo de transição.

---

# Conclusão

Os métodos probabilísticos são **fundamentais** para a Inteligência Artificial, pois permitem:
✅ Modelar a incerteza.  
✅ Tomar decisões informadas com base em evidências.  
✅ Fazer previsões e inferências em ambientes dinâmicos.  

Os principais modelos estudados incluem:
- **Redes Bayesianas** (para inferência probabilística).
- **Cadeias de Markov** (para processos dinâmicos).
- **Filtros de Kalman e Partículas** (para inferências em tempo real).