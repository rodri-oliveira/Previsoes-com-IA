# Previsões com IA

Projeto de aprendizado de máquina em Python/Jupyter para análise e previsão de score de crédito.

## Sobre o projeto
- Notebooks em `inicial (1).ipynb` e `gabarito.ipynb`.
- Dados de exemplo: `clientes.csv` e `novos_clientes.csv`.
- Ambiente isolado com `venv` e dependências listadas em `requirements.txt`.

## Pré-requisitos
- Python 3.11+ instalado (recomendado). Verifique com:
  ```powershell
  py --version
  py -0p
  ```
- Git instalado (opcional, para clonar/commitar).
- VS Code com extensões:
  - Python (Microsoft)
  - Jupyter (Microsoft)

## Setup rápido (Windows PowerShell)
Na raiz do projeto:
```powershell
# 1) Criar e ativar o ambiente virtual
py -m venv .venv
.\.venv\Scripts\Activate.ps1

# 2) Atualizar ferramentas básicas
python -m pip install --upgrade pip setuptools wheel

# 3) Instalar dependências
pip install -r requirements.txt
```
Se preferir instalar apenas o necessário para os notebooks:
```powershell
pip install jupyter ipykernel pandas numpy scikit-learn
python -m ipykernel install --user --name ia-curso --display-name "Python (.venv ia-curso)"
```

## Usando no VS Code (Jupyter)
1. Selecione o interpretador: Ctrl+Shift+P → "Python: Select Interpreter" → escolha `./.venv/Scripts/python.exe`.
2. Abra o notebook (`.ipynb`).
3. No topo do notebook, selecione o kernel "Python (.venv ia-curso)". Se não aparecer, use Ctrl+Shift+P → "Jupyter: Select Jupyter Kernel".
4. Teste o kernel com:
   ```python
   import sys; print(sys.executable)
   ```
   Deve apontar para `.../.venv/Scripts/python.exe`.

## Executando
- `inicial (1).ipynb`: pipeline didático com preparação de dados e treino/teste.
- `gabarito.ipynb`: referência/solução do curso.

Para abrir o Jupyter Notebook clássico (opcional):
```powershell
jupyter notebook
```
Ou JupyterLab:
```powershell
jupyter lab
```

## Reprodutibilidade
- Congelar dependências após instalar/atualizar pacotes:
  ```powershell
  pip freeze > requirements.txt
  ```
- Para reinstalar em outra máquina:
  ```powershell
  py -m venv .venv
  .\.venv\Scripts\Activate.ps1
  pip install -r requirements.txt
  ```

## Estrutura do repositório
```
.
├── .gitignore
├── README.md
├── requirements.txt
├── clientes.csv
├── novos_clientes.csv
├── inicial (1).ipynb
└── gabarito.ipynb
```

## Dicas e problemas comuns
- Kernel errado: se `from sklearn.preprocessing import LabelEncoder` falhar, verifique o kernel e/ou instale no próprio notebook:
  ```python
  %pip install scikit-learn pandas numpy
  ```
  Reinicie o kernel após instalar.
- OneDrive e caminhos com acento/espaços podem causar lentidão ou problemas de permissão. Se notar erros estranhos, mova o projeto para um caminho simples, ex.: `C:\projetos\previsoes-ia`.
- Encoding do CSV: se houver erro de decodificação, tente:
  ```python
  pd.read_csv("clientes.csv", encoding="latin-1")
  # ou
  pd.read_csv("clientes.csv", encoding="utf-8-sig")
  ```
- Limpar saídas do notebook antes de commitar ajuda a manter o repo limpo (VS Code: "Clear All Outputs").

## Contribuindo
Pull Requests são bem-vindos. Para alterações maiores, abra uma issue primeiro para discutir o que você gostaria de mudar.

## Licença
Defina a licença desejada (ex.: MIT) adicionando um arquivo `LICENSE`.
