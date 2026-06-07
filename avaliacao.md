O Cliff Walking (S&B, Exemplo 6.6) é um gridworld no qual o agente deve aprender a navegar de um ponto inicial até um objetivo evitando um precipício. Cada passo no precipício gera recompensa −100 e reinicia o episódio; cada passo fora do precipício gera recompensa −1. O agente dispõe de quatro ações (cima, baixo, esquerda, direita). O ambiente deve ser implementado do zero, sem bibliotecas de RL prontas. A aproximação de função linear Q(s,a,w) = w⊤φ(s,a) substitui a tabela Q — o aluno deve definir o vetor de features φ(s,a) e implementar explicitamente o loop de atualização semi-gradiente TD. A comparação entre o agente tabular (Q-Learning) e o agente com aproximação de função é o núcleo analítico da atividade.


(1) Implementação do ambiente Cliff Walking. (Peso = 1,0)


(a) Dinâmica do ambiente com estados, ações, recompensas e condições de término corretamente definidas


(b) Lógica do precipício (recompensa −100 e reinício do episódio) implementada e verificada


(c) Visualização do gridworld implementada para inspeção do comportamento do agente


(2) Implementação do agente tabular Q-Learning. (Peso = 2,0)


(a) Inicialização da tabela Q(s,a) e loop de atualização off-policy com max_a Q(S'_,a)


(b) Política ε-greedy com decaimento de ε documentado


(c) Hiperparâmetros justificados e métricas de treinamento registradas (curva de aprendizado, recompensa por episódio)


(3) Implementação do agente com aproximação de função e semi-gradiente TD. (Peso = 4,0)


(a) Representação Q(s,a,w) = w⊤φ(s,a) com vetor de features φ(s,a) definido e justificado


(b) Loop de atualização semi-gradiente TD implementado explicitamente: w ← w + α [r + γ max_a Q(s'_,a,w) − Q(s,a,w)] ∇Q(s,a,w)


(c) Política ε-greedy com decaimento, hiperparâmetros justificados e métricas de treinamento registradas


(4) Análise comparativa. (Peso = 2,0)


(a) Comparação entre Q-Learning tabular e agente com aproximação de função: curvas de aprendizado, política aprendida e convergência


(b) Discussão conceitual sobre o que muda ao substituir a tabela Q por uma função parametrizada — generalização, estabilidade e limitações


(c) Identificação de ao menos um caso em que a generalização da aproximação de função é prejudicial neste ambiente e interpretação do fenômeno


(5) Vídeo explicativo (2 a 5 minutos). (Peso = 1,0)


(a) Explicação do ambiente Cliff Walking: estados, ações, recompensas e lógica do precipício


(b) Demonstração dos dois agentes: como o loop de atualização funciona em cada caso e qual é a diferença entre a tabela Q e a função parametrizada


(c) Apresentação da análise comparativa com curvas de aprendizado e discussão dos resultados observados


(d) Duração entre 2 e 5 minutos, com explicação completa e objetiva dentro do tempo