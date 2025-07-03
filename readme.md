# Imersão DevOps - Alura Google Cloud (Com Adaptações)

Este projeto é uma API desenvolvida com FastAPI para gerenciar alunos, cursos e matrículas em uma instituição de ensino. Ele foi originalmente desenvolvido durante a **Imersão DevOps da Alura**, e esta versão inclui **modificações e incrementos pessoais**, com o objetivo de aprofundar o aprendizado e torná-lo parte do meu portfólio.

##  Sobre este repositório

A base do projeto (arquivos principais da aplicação e banco de dados) foi mantida conforme fornecida pela Alura:

- `app.py`
- `database.py`
- `models.py`
- `schemas.py`
- `requirements.txt`
- Banco de dados SQLite (`escola.db`)

As seguintes modificações e melhorias foram adicionadas por mim:

- Criação de um **`Dockerfile`** para containerização da aplicação.
- Inclusão de um **`docker-compose.yml`** para facilitar a orquestração do ambiente.
- Ajustes no `README.md` para refletir as alterações e facilitar a execução com Docker.

## Pré-requisitos

- [Python 3.10 ou superior instalado](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)
- [Docker](https://www.docker.com/get-started/)

##  Executando com Docker (opcional e recomendado)

docker-compose up --build
Acesse: http://localhost:8000/docs


1. **Clone este repositório:**

sh
Copy
Edit
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio

2. **Crie e ative o ambiente virtual:**
sh
Copy
Edit
python3 -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate     # Windows

3. **Instale as dependências:**
sh
Copy
Edit
pip install -r requirements.txt

4. **Execute a aplicação:**
sh
Copy
Edit
uvicorn app:app --reload
5. **Acesse a documentação interativa:**
http://127.0.0.1:8000/docs


---
### Autenticação e envio no Google Cloud
```sh
gcloud auth login
gcloud config det project PROJECT_ID
gcloud run deploy --port=8000
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass  # se seu Visual code for restrito
gcloud config set project indigo-syntax-464622-b1
 gcloud run deploy --port=8000  # a porta que você defiiniu no yml
 Do you want enable these APIs to continue (this will take a few minutes)? (Y/n)?  Y # diga sim para continuar
 Please specify a region: # use a mais perto, no nosso caso para barata é a de SP [32] southamerica-east1
 De Y para tudo
 Allow unauthenticated invocations to [api] (y/N)?  y  #sim porque vai ser aberto, se fosse intranet até seria bom criar login.
 Minha pagina: https://api-829073535968.southamerica-east1.run.app
```
---
## Estrutura do Projeto
## Mantido como o da **Alura**
- `app.py`: Arquivo principal da aplicação FastAPI.
- `models.py`: Modelos do banco de dados (SQLAlchemy).
- `schemas.py`: Schemas de validação (Pydantic).
- `database.py`: Configuração do banco de dados SQLite.
- `routers/`: Diretório com os arquivos de rotas (alunos, cursos, matrículas).
- `requirements.txt`: Lista de dependências do projeto.


---
- O banco de dados SQLite será criado automaticamente como `escola.db` na primeira execução.
- Para reiniciar o banco, basta apagar o arquivo `escola.db` (isso apagará todos os dados).

---
