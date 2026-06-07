Objetivo
Implementar uma solução para o problema Cliff Walking utilizando aproximação de função com semi-gradiente TD — substituindo a tabela Q(s,a) por uma função parametrizada Q(s,a,w) atualizada por gradiente descendente. A atividade consolida a transição dos métodos tabulares da Sprint 3 para a aproximação de função da Sprint 4 e deve ser acompanhada de um vídeo explicativo demonstrando as escolhas de modelagem e os resultados obtidos.


Descrição do Problema
O Cliff Walking (S&B, Exemplo 6.6) é um gridworld clássico no qual o agente deve aprender a navegar de um ponto inicial até um objetivo evitando um precipício. Cada passo no precipício gera recompensa −100 e reinicia o episódio; cada passo fora do precipício gera recompensa −1. O agente dispõe de quatro ações (cima, baixo, esquerda, direita) e deve aprender a política que maximiza o retorno acumulado ao longo dos episódios.


O ambiente deve ser implementado do zero, sem o uso de Gym, Gymnasium ou equivalentes. A aproximação de função substitui a tabela Q — o aluno deve definir o vetor de features φ(s,a) e implementar a atualização semi-gradiente TD explicitamente, sem bibliotecas de RL prontas.


Requisitos
1. Implementação do ambiente Cliff Walking: reproduzir o ambiente conforme descrito no S&B, definindo corretamente estados, ações, recompensas e dinâmica de transição, incluindo a lógica do precipício (recompensa −100 e reinício). O ambiente deve ser testável de forma isolada e incluir visualização do gridworld.


2. Aproximação de função com semi-gradiente TD: implementar Q(s,a,w) = w⊤φ(s,a), onde φ(s,a) é um vetor de features definido e justificado pelo aluno. O loop de atualização deve implementar explicitamente a regra w ← w + α [r + γ max_a Q(s'_,a,w) − Q(s,a,w)] ∇Q(s,a,w), com estratégia ε-greedy e decaimento de ε documentado.


3. Definição e avaliação de políticas: propor ao menos duas políticas distintas (por exemplo, ε-greedy com diferentes valores de ε ou diferentes representações de features) e comparar a função de valor V(s) estimada para cada uma ao longo do treinamento.


4. Comparação com agente tabular: comparar o agente com aproximação de função com um agente Q-Learning tabular da Sprint 3 em termos de curvas de aprendizado, política aprendida e convergência. Discutir quando a generalização da aproximação de função ajuda e quando pode prejudicar.


5. Documentação do código: todo o código deve ser comentado e documentado, com explicações sobre as decisões de implementação, a construção do vetor de features, o cálculo da função de valor e a estratégia de exploração adotada.


6. Vídeo explicativo (entre 2 e 5 minutos): o aluno deve produzir um vídeo onde apresente a modelagem do problema, explique como o semi-gradiente TD foi utilizado para estimar a função de valor, demonstre o funcionamento do agente e discuta os principais resultados e aprendizados. Não basta mostrar o sistema funcionando — é necessário explicar as escolhas técnicas e justificá-las. O vídeo deve indicar também onde uma rede neural poderia ser utilizada para aprimorar a solução.