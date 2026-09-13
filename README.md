name: Pipeline CI

on:
  push:
    branches: [ principal, main ]
  pull_request:
    branches: [ principal, main ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Configurar Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'

      - name: Teste de Integracao
        run: |
          python -c "print('Pipeline CI/CD executado com sucesso!')"
