# My-commands-for-consultation

<center>

# <font color="rgb(61,98,0)" size="7" face="Arial">Comandos Usados</font>

# TASK-MANAGE-SYSTEM. 

É um Projeto que tem como base Treinamento Em Programação Com Python Moderno na construção de Web-apps ou API com uso do Micro-FrameWork FLASK e usando As boas praticas e novidades. 

## 

> **REQUISITOS**:
> * Computador com Python, Pyenv, Poetry, Git, Docker, Docker-Compose devidamente instalados
> * IDE Um editor de código como VSCode, Vim, PyCharm, Sublime. (OBS: Usarei o VSCode)

> **NOTA**: Os comandos apresentados serão executados em um terminal Linux, se estiver no Windows recomendo usar o WSL, uma máquina virtual ou um container Linux, ou por conta própria adaptar os comandos necessários.

```bash
# 1- Cria Pasta ou Diretorio do projeto e entra com VsCode pelo Terminal 
mkdir Task-Manage-System
cd Task-Manage-System     
code .

# 2- Cria um Projeto no Git
git init
touch .gitignore README.md LICENSE
## .gitignore
 **/__pycache__
 .pytest_cache
 .env
 .ruff_cache
 venv
 COMANDS-USED.md

## README.md
# TASK-MANAGE-SYSTEM.

É um Projeto que tem como base Treinamento Em Programação Com Python Moderno na construção de Web-apps ou API com uso do Micro-FrameWork FLASK e usando As boas praticas e novidades do mercado. 


## LICENSE
MIT License

Copyright (c) 2024 VLADEMIR

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

##
git status
git add .gitignore
git add README.md
git add LICENSE
git add .
git commit -m "init: start project git and add .gitignore README.md LICENSE files"

# 3- PYENV Verifica a versão, cria variavel de ambiente local, ativa, atualiza pip 
pyenv --version
pyenv local 3.12.3
pyenv exec python -V
pyenv exec python -m venv venv --prompt <nome-projeto>
source venv/bin/activate OU . venv/bin/activate
pip install -U pip setuptools wheel
pip list

# 3.1- Cria pastas com codigos do Projeto 
mkdir src tests docs

## 3.2- Cria arquivos requiridos
touch Dockerfile docker-compose.yml .env requirements.txt requirementes-dev.txt

## 3.3- Adiciona .env
FLASK_APP=app.py
FLASK_ENV=development
SECRET_KEY="please change me"

##Criar senhas ou usando python >>>
>>> import os
>>> os.urandom(24)
import secrets
print(secrets.token_hex(32))

## 3.4- Adiciona requirementes-dev.txt

-r requirements.txt
pytest 
pytest-cov 
taskipy 
ruff 
httpx 
ipython

## 3.5- Adiciona requirementes.txt
Flask
flask-smorest
Flask-SQLAlchemy
Flask-Migrate
psycopg2-binary
Click

## 3.6- Instala as dependecias
pip install -r requirements-dev.txt
git add .
git commit -m "config: creation of folder and requirements file considering dependencies with virtual environment"
pip freeze > requirements.txt

# 6- Adicione as dependencias
poetry add flask flask-restx #Ex. poetry add fastapi uvicorn httpx 
poetry add --group dev pytest pytest-cov taskipy ruff httpx
# 7- Criar .env, src/__init__.py

# 8- CONFIGURAÇÃO DO .vscode
## 8.1 extensions.json
{
  "recommendations": [
    "ms-python.python",
    "ms-python.vscode-pylance",
    "charliermarsh.ruff",
    "editorconfig.editorconfig"
  ]
}
## 8.2 settings.json
{
  "window.zoomLevel": 0.42,
  "editor.fontSize": 14,
  "screencastMode.fontSize": 36,
  "terminal.integrated.fontSize": 12,
  "files.exclude": {
    ".venv/": false,
    "**/*.pyc": {
      "when": "$(basename).py"
    },
    "**/__pycache__": true,
    "**/*.pytest_cache": true,
    ".mypy_cache/": true,
    ".ruff_cache/": true
  },
  "[python]": {
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
      "source.fixAll": "explicit",
      "source.organizeImports": "explicit"
    },
    "editor.defaultFormatter": "charliermarsh.ruff"
  },
  "[jsonc]": {
    "editor.defaultFormatter": "vscode.json-language-features"
  },
}
$ tree --config .vscode
.
├── .vscode                
│   ├── extensions.json
│   │   ├── {
│   │   │     "recommendations": [
│   │   │     "ms-python.python",
│   │   │     "ms-python.vscode-pylance",
│   │   │     "charliermarsh.ruff",
│   │   │     "editorconfig.editorconfig"
│   │   │     ]
│   │   └── }
│   ├── settings.json
│   │    ├── {
│   │    │     "window.zoomLevel": 0.42,
│   │    │     "editor.fontSize": 14,
│   │    │     "screencastMode.fontSize": 36,
│   │    │     "terminal.integrated.fontSize": 12,
│   │    │     "files.exclude": {
│   │    │       ".venv/": false,
│   │    │       "**/*.pyc": {
│   │    │          "when": "$(basename).py"
│   │    │     },
│   │    │     "**/__pycache__": true,
│   │    │     "**/*.pytest_cache": true,
│   │    │     ".mypy_cache/": true,
|   |    |     ".ruff_cache/": true
│   │    │     },
│   │    │     "[python]": {
│   │    │       "editor.formatOnSave": true,
│   │    │       "editor.codeActionsOnSave": {
│   │    │         "source.fixAll": "explicit",
│   │    │         "source.organizeImports": "explicit"
│   │    │       },
│   │    │       "editor.defaultFormatter": "charliermarsh.ruff"
│   │    │     },
│   │    │     "[jsonc]": {
│   │    │       "editor.defaultFormatter": "vscode.json-language-features"
│   │    │     },
│   │    └── }
│   └──  
└──

# 9- pyproject.toml

[tool.ruff]
line-length = 89
extend-exclude = ['migrations']

[tool.ruff.lint]
preview = true
select = ['I', 'F', 'E', 'W', 'PL', 'PT']

[tool.ruff.format]
preview = true
quote-style = 'single'

[tool.pytest.ini_options]
pythonpath = "."
addopts = '-p no:warnings'

[tool.taskipy.tasks]
lint = 'ruff check .; ruff check . --diff'
format = 'ruff check . --fix; ruff format .'
run = 'python main.py'
pre_test = 'task lint'
test = 'pytest -s -x --cov=fast_zero -vv'
post_test = 'coverage html'


# 10- Usando o Docker

## Dockerfile

# Usa uma imagem base do Python
FROM python:3.12-slim

# Define o diretório de trabalho dentro do contêiner
WORKDIR /app

# Copia o arquivo de dependências para o diretório de trabalho
COPY requirements.txt .

# Instala as dependências do Python
RUN pip install -U pip \
    && pip install --no-cache-dir -r requirements.txt

# Copia o código da aplicação para o contêiner
COPY . .

# Expõe a porta da aplicação do contêiner
EXPOSE 5000

#ENV SECRET_KEY=******

# Instrução CMD para rodar o aplicativo
CMD ["flask", "run", "--host=0.0.0.0"]


# .dockerignore
# Ignora arquivos Python compilados
__pycache__/
*.pyc

# Ignora arquivos e pasta com ambiente de desenvolvimento variaveis de ambiente
venv/
.env

# Ignora arquivos de configuração do Docker
Dockerfile
.dockerignore

# Ignora arquivos de controle de versionamento
.git
.gitignore

# Ignora pastas de testes e exemplos
tests/
examples/

# Ignora outros arquivos desnecessarios
*.log

docker build -t <Nome-do-Projeto> .
docker run -d -p 5002:5000 <Nome-ou-ID-Projeto>
docker run -d -p 5002:5000 -w /app -v "${pwd}:/app" <Nome-ou-ID-Projeto>



```

</center>

Author: @VladeSouza 

Github: @VladeTec

Linkedin: https://www.linkedin.com/in/vlademir-souza-ads

