# Cliff Walking

Este projeto implementa uma solução para o problema **Cliff Walking**, um gridworld clássico de aprendizado por reforço apresentado por Sutton & Barto. A atividade explora a transição entre métodos tabulares e aproximação de função, comparando um agente **Q-Learning tabular** com um agente **Q-Learning com aproximação linear e semi-gradiente**.

O artefato principal é o notebook [`notebook.ipynb`](notebook.ipynb), que contém a implementação, os testes, as visualizações e a análise comparativa em português.

## O que foi implementado

- Ambiente Cliff Walking implementado do zero, sem Gym/Gymnasium.
- Dinâmica completa do gridworld:
  - grid `4 x 12`;
  - estado inicial `(3, 0)`;
  - objetivo `(3, 11)`;
  - precipício entre `(3, 1)` e `(3, 10)`;
  - recompensa `-1` por passo;
  - recompensa `-100` ao cair no precipício, com retorno ao início.
- Visualização do grid, das políticas aprendidas e das funções de valor.
- Agente Q-Learning tabular com:
  - tabela `Q(s,a)`;
  - política epsilon-greedy;
  - decaimento de epsilon;
  - métricas de recompensa, passos e quedas no precipício.
- Agente com aproximação linear e semi-gradiente com:
  - representação `Q(s,a,w) = w^T phi(s,a)`;
  - vetor de features por blocos de ação;
  - atualização semi-gradiente explícita;
  - estabilização dos pesos durante o treinamento.
- Comparação final entre os dois agentes:
  - curvas de aprendizado;
  - políticas aprendidas;
  - rollouts gulosos;
  - funções de valor estimadas;
  - discussão sobre generalização, estabilidade e limitações.

## Resultados principais

Na execução validada do notebook:

- O agente tabular alcançou o objetivo em `13` passos no rollout guloso.
- O agente linear alcançou o objetivo em `17` passos no rollout guloso.
- O agente linear obteve melhor recompensa média final durante o treinamento.
- O agente tabular produziu o caminho guloso mais curto e teve menos quedas acumuladas no precipício.

Esses resultados mostram o trade-off central da atividade: a aproximação linear permite generalização entre estados, mas pode ser menos precisa em um ambiente pequeno e discreto, especialmente perto do precipício.

## Requisitos

- Python 3.11 ou superior
- [uv](https://docs.astral.sh/uv/) para gerenciamento do ambiente

As dependências principais são:

- `numpy`
- `matplotlib`

## Como executar

Instale as dependências e crie o ambiente virtual:

```bash
uv sync
```

Abra o notebook:

```bash
uv run jupyter notebook notebook.ipynb
```

Se preferir usar JupyterLab:

```bash
uv run jupyter lab notebook.ipynb
```

## Estrutura do projeto

```text
.
├── notebook.ipynb    # Implementação, testes, gráficos e análise
├── pyproject.toml    # Configuração do projeto e dependências
├── uv.lock           # Versões bloqueadas das dependências
├── conteudo.md       # Enunciado da atividade
├── avaliacao.md      # Critérios de avaliação
└── README.md         # Introdução do projeto
```

## Observação sobre o vídeo

A atividade também exige um vídeo explicativo de 2 a 5 minutos. Este repositório foca na implementação e documentação técnica no notebook; o roteiro e a gravação do vídeo ficam como etapa separada.
