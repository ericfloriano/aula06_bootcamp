# 🧪 Testar Stacks: Formatação e Linting de Código Python

## 🎯 Objetivo

Explorar e aplicar ferramentas modernas para garantir a qualidade, consistência e padronização de código Python, utilizando `black`, `isort`, `flake8` e automações com `taskipy`.

---

## ⚙️ Ferramentas Utilizadas

### `black` – Formatador de Código Automático
Reescreve o código Python conforme uma convenção rígida de estilo. Você não precisa decidir sobre espaçamento ou quebras de linha — o `black` decide por você. É conhecido como “**the uncompromising code formatter**”.

### `isort` – Organizador de Imports
Ordena automaticamente os `imports` do seu código, separando-os por origem (biblioteca padrão, terceiros, locais).

### `flake8` – Linting
Analisa o código em busca de erros, más práticas, violações de PEP8 e variáveis não utilizadas. Um revisor automático de qualidade de código.

---

## 🚧 Preparação do Ambiente

```bash
# 1. Defina a versão Python com pyenv
pyenv local 3.11.5

# 2. Inicie o projeto com poetry
poetry init

# 3. Configure o ambiente virtual
poetry env use 3.11.5

# 4. Ative o suporte ao comando shell do poetry
poetry self add poetry-plugin-shell

# 5. Acesse o ambiente virtual
poetry shell

# Para sair:
deactivate
```
# 📦 Instalação das Bibliotecas

```bash
# Black
poetry add black
poetry run black main.py

# isort
poetry add isort
poetry run isort main.py

# Flake8
poetry add flake8
poetry run flake8 main.py
```
# 🧩 Taskipy – Automatizando Tarefas

O `taskipy` permite definir comandos personalizados para facilitar o dia a dia no desenvolvimento.
Adicione as tarefas no seu `pyproject.toml`:

```toml
[tool.taskipy.tasks]
format = "black main.py && isort main.py"
lint = "flake8 main.py"
run = "python main.py"
```
Execute com:
```bash
poetry run task format
poetry run task lint
```
# 🧼 Pré-commit

Este projeto utiliza `pre-commit` para rodar automaticamente o formatador antes dos commits.

1) Instalar o `pre-commit`:

```bash
poetry add pre-commit --dev
```

2) Criar o arquivo `.pre-commit-config.yaml`:

```yaml
repos:
  - repo: local
    hooks:
      - id: poetry-task-format
        name: Format with Taskipy (black + isort)
        entry: poetry run task format
        language: system
        types: [python]

      - id: poetry-flake8
        name: Lint with Flake8
        entry: poetry run flake8
        language: system
        types: [python]
```

3) Para ativar os hooks:

```bash
pre-commit install
```

4) (Opcional) Testar manualmente os `hooks`:

```bash
pre-commit run --all-files
```

# ✅ Conclusão

Este setup oferece uma forma robusta e automatizada de garantir que o código esteja sempre limpo, organizado e dentro das boas práticas do Python. Com **poetry, taskipy, black, isort, flake8 e pre-commit**, você reduz retrabalho, melhora a legibilidade e eleva o padrão do seu projeto desde o primeiro commit 🚀