Olá, este é meu repositório.

name: Continuous Integration

on:
  push:
    branches:
      - main  # Executa o CI no branch 'main' sempre que houver push

jobs:
  build:
    runs-on: ubuntu-latest  # Utiliza o ambiente Ubuntu mais recente para rodar o CI

    steps:
      - name: Checkout repository
        uses: actions/checkout@v2  # Faz o checkout do código do repositório

      - name: Set up Python
        uses: actions/setup-python@v2  # Exemplo de como configurar uma ferramenta (Python aqui)
        with:
          python-version: '3.8'

      - name: Install dependencies
        run: |
          pip install -r requirements.txt  # Se houver dependências para instalar

      - name: Run tests
        run: |
          python -m unittest discover  # Exemplo de execução de testes
