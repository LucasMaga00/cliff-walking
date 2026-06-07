# Cliff Walking

Um projeto Python para implementar e testar o problema de aprendizado por reforço Cliff Walking.

## Requisitos

- Python 3.11 ou superior
- [uv](https://docs.astral.sh/uv/) - Um gerenciador de pacotes Python extremamente rápido

## Instalação

### Instalar uv

Se você não tem `uv` instalado, siga o [guia de instalação oficial](https://docs.astral.sh/uv/getting-started/installation/):

```bash
# macOS / Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows (PowerShell)
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### Configurar o projeto

Uma vez que você tem `uv` instalado, configure o ambiente do projeto:

```bash
# Instalar dependências e criar ambiente virtual
uv sync

# Este comando irá:
# - Criar um diretório .venv com o ambiente Python
# - Instalar todas as dependências do projeto
# - Bloquear as dependências em uv.lock para reprodutibilidade
```

## Uso

Ative o ambiente virtual:

```bash
# Em macOS/Linux
source .venv/bin/activate

# Em Windows
.venv\Scripts\activate
```

Execute seus scripts Python normalmente:

```bash
python seu_script.py
```

Ou use `uv run` para executar sem ativar o ambiente:

```bash
uv run python seu_script.py
```

## Desenvolvimento

### Gerenciar dependências

Adicionar uma nova dependência:

```bash
uv add nome_do_pacote
```

Adicionar uma dependência apenas para desenvolvimento:

```bash
uv add --dev nome_do_pacote
```

Remover uma dependência:

```bash
uv remove nome_do_pacote
```

Atualizar dependências:

```bash
# Atualizar todas as dependências
uv lock --upgrade

# Atualizar pacote específico
uv lock --upgrade-package nome_do_pacote
```

### Ambiente virtual

O ambiente virtual é automaticamente gerenciado em `.venv/`. Para usá-lo em sua IDE, aponte para `.venv/bin/python` (ou `.venv\Scripts\python.exe` no Windows).

## Estrutura do projeto

```
.
├── notebook.ipynb    # Notebook Jupyter com implementação e testes
├── pyproject.toml    # Configuração do projeto e dependências
├── uv.lock          # Versões das dependências bloqueadas
├── conteudo.md      # Conteúdo do projeto
├── avaliacao.md     # Critérios de avaliação
└── README.md        # Este arquivo
```

## Mais informações

- [Documentação do uv](https://docs.astral.sh/uv/)
- [Guia de Empacotamento Python](https://packaging.python.org/)
