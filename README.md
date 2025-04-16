# Testar Stacks Formatação e Linting de Código Python

## Contexto

- **Black** – Formatador de código automático
- - Reescreve o código Python conforme uma convenção rígida de estilo. Você não precisa decidir sobre o espaçamento ou a quebra de linhas: o Black decide por você. É conhecido como “o uncompromising code formatter”.

- **isort** – Organizador de imports
- - Ordena automaticamente os imports do seu código Python, separando por tipo (standard library, third-party, e local) e deixando tudo limpo e organizado.

- **Flake8** – Ferramenta de linting
- - Analisa o código em busca de erros, más práticas, estilo fora do PEP8, variáveis não usadas, entre outros. É uma espécie de “revisor” que aponta problemas antes da execução.

## Preparação do Ambiente

1) Instalar `pyenv local 3.11.5`
2) Iniciar Poetry como o comando `poetry init`
3) Execute agora o `poetry env use 3.11.5`
4) A partir da versão 2.0.0 do Poetry, o comando `poetry shell` não vem mais habilitado por padrão, então execute o seguinte comando `poetry self add poetry-plugin-shell` para instalar o plugin e executar como antigamente
4) Na sequencia execute no terminal `poetry shell`
5) Para sair do ambiente virtual, digite: `deactivate`

## Instalar as Bibliotecas

- **Flake8:** 
1) Para instalar: `poetry add flake8`
2) Para executar: `poetry run flake8`