O **aprendizado não supervisionado** busca **encontrar padrões e relações** em dados **não rotulados**. É muito utilizado em **mineração de dados**, pois permite extrair informações sem conhecimento prévio sobre os rótulos.

📌 **Principais Tarefas**:
✅ **Agrupamento (Clustering)** → Separar os dados em grupos semelhantes.  
✅ **Identificação de Padrões Frequentes** → Encontrar padrões comuns em grandes volumes de dados.  
✅ **Identificação de Anomalias** → Detectar **pontos fora do padrão**.  
✅ **Redução de Dimensionalidade** → Simplificar os dados sem perder informações essenciais.  

---

## 1. **Agrupamento de Dados (Clustering)**

O **agrupamento de dados** organiza um conjunto de exemplos em **grupos naturais**, de forma que os itens dentro do mesmo grupo sejam mais **similares** entre si do que com itens de outros grupos.

### 🔹 **Características**
- **Problema não supervisionado** → Não há rótulos indicando a qual grupo cada objeto pertence.
- **Entrada** → Um conjunto de dados **sem rótulos**.
- **Saída** → Uma **atribuição de cada elemento** a um grupo (cluster).

---

## 2. **Como Definir os Grupos?**
Para realizar o agrupamento, é fundamental definir uma **medida de similaridade** entre os dados.

📌 **Exemplo de Medida de Similaridade**:
✅ **Distância Euclidiana**  
A **distância entre dois pontos** no espaço é medida como:

$$
d(A, B) = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}
$$

Essa métrica é usada por **muitos algoritmos de agrupamento** para calcular a proximidade entre exemplos.

---

## 3. **Algoritmo K-Means**

O **K-Means** é um dos algoritmos mais utilizados para **agrupamento**.

📌 **Funcionamento**:
1. **Escolhe aleatoriamente K pontos** como os **centroides iniciais**.
2. **Cada ponto do conjunto de dados é associado ao centroide mais próximo**.
3. **Os centroides são recalculados** como a média dos pontos atribuídos a cada grupo.
4. **Repete até que os grupos não mudem mais**.

📌 **Critérios para definir K**:
✅ Um **K muito pequeno** → Pode agrupar pontos diferentes no mesmo grupo.  
✅ Um **K muito grande** → Pode criar grupos com pouca distinção entre si.  

💡 **Método das Silhuetas** → Mede a qualidade dos clusters e ajuda a definir **o melhor valor de K**.

- **Valor próximo de 1** → O ponto está no **grupo correto**.
- **Valor próximo de 0** → O ponto está **entre dois grupos**.
- **Valor negativo** → O ponto foi colocado no **grupo errado**.

---

## 4. **Avaliação dos Resultados do Agrupamento**

Como não há rótulos nos dados, **avaliar a qualidade do agrupamento é desafiador**. Algumas métricas ajudam a estimar a **qualidade dos clusters**:

📌 **Critérios de Qualidade**:
✅ **Homogeneidade** → Elementos dentro do mesmo grupo devem ser **altamente similares**.  
✅ **Separação** → Elementos de **diferentes grupos** devem ser **muito distintos**.  

💡 **Objetivo**: **Minimizar a distância entre pontos do mesmo grupo e maximizar a distância entre grupos distintos**.

---

## 5. **Identificação de Padrões Frequentes**

📌 **Objetivo**: Encontrar **padrões comuns** em grandes conjuntos de dados.

✅ **Exemplo**:  
No supermercado, um sistema pode identificar que **clientes que compram café geralmente compram leite**.  

📌 **Técnicas usadas**:
✅ **Regras de Associação** (como o Algoritmo **Apriori**)  
✅ **Métricas principais**:
- **Suporte** → Frequência com que um conjunto de itens aparece nos dados.
- **Confiança** → Probabilidade condicional de um item ser comprado junto a outro.
- **Lift** → Mede a correlação entre os itens.

💡 **Aplicação prática** → **Sistemas de Recomendação**, como sugestões de produtos na Amazon ou sugestões de heróis em jogos online.

---

## 6. **Identificação de Anomalias**

A **identificação de anomalias** detecta itens ou eventos que **diferem do padrão** em um conjunto de dados.

📌 **Aplicações**:
✅ **Detecção de Fraudes** → Transações bancárias suspeitas.  
✅ **Segurança de Sistemas** → Identificação de acessos indevidos.  
✅ **Monitoramento Industrial** → Detecção de falhas em máquinas.

💡 **Método comum** → **Algoritmos de agrupamento** para encontrar pontos fora do padrão.

---

## 7. **Redução de Dimensionalidade**

A **redução de dimensionalidade** busca **representar os dados em menos dimensões**, mantendo a **informação essencial**.

📌 **Objetivo**:
✅ Facilitar a **visualização** dos dados.  
✅ Diminuir o **custo computacional**.  
✅ Evitar a **maldição da dimensionalidade** (quando muitos atributos tornam o modelo ineficiente).

📌 **Técnicas utilizadas**:
✅ **PCA (Principal Component Analysis)** → Converte os dados em **novas variáveis independentes**.  
✅ **Autoencoders** → Redes neurais que aprendem uma **representação compacta** dos dados.

💡 **Exemplo Prático**:
Para comparar diferentes **algoritmos de tomada de decisão em jogos**, pesquisadores utilizaram **PCA** para reduzir um **conjunto de 600.000 dados** para **3 componentes principais**, e depois aplicaram **K-Means** para agrupamento.

---

# **Resumo Geral da Aula**

📌 **Aprendizado Não Supervisionado**:
- Objetivo: **Encontrar padrões em dados não rotulados**.
- Aplicações: **Mineração de dados, recomendação de produtos, detecção de fraudes**.

📌 **Principais Técnicas**:
✅ **Agrupamento (Clustering)** → K-Means, Distância Euclidiana.  
✅ **Identificação de Padrões Frequentes** → Regras de Associação.  
✅ **Identificação de Anomalias** → Detecção de fraudes e eventos incomuns.  
✅ **Redução de Dimensionalidade** → PCA, Autoencoders.

🚀 **Impacto na Inteligência Artificial**:
Essas técnicas são essenciais para **análise de dados em grande escala**, sendo usadas em **sistemas de recomendação, segurança e aprendizado profundo**.

---

# **Conclusão**

O **aprendizado não supervisionado** é uma área poderosa da IA que permite a **descoberta de padrões** e insights **sem necessidade de rótulos**. Seus métodos são fundamentais para aplicações como **reconhecimento de padrões, recomendações automáticas e segurança cibernética**.

🔥 **Principais aprendizados**:
✅ O **K-Means** é amplamente utilizado para **agrupamento de dados**.  
✅ A **escolha correta de K** é fundamental para **bons agrupamentos**.  
✅ **Regras de Associação** ajudam na **descoberta de padrões frequentes**.  
✅ **Detecção de Anomalias** é usada em **segurança e monitoramento**.  
✅ **Redução de Dimensionalidade** melhora a eficiência da análise de dados.  