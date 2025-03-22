# Fake Shop


## Variável de Ambiente
DB_HOST	=> Host do banco de dados PostgreSQL.

DB_USER => Nome do usuário do banco de dados PostgreSQL.

DB_PASSWORD	=> Senha do usuário do banco de dados PostgreSQL.

DB_NAME	=>	Nome do banco de dados PostgreSQL.

DB_PORT	=>	Porta de conexão com o banco de dados PostgreSQL.


Código utilizado no evento "Desafio DevOps & Cloud".

#### Este código fonte possui um processo de automação CI-CD simplificado. 


### Passos para configuração do deploy automatizado / execução do CI-CD por GitHub Actions:

1. Obter dados que serão utilziados na secrets:
     - Obter o arquivo de configurações do kubernetes do seu projeto no Digital Ocean;
     - Obter seu usuário de acesso ao DockerHub;
     - Obter sua senha de acesso ao DockerHub;
1. Definir / configurar suas secrets que serão utilziadas no GitHub Actions:
     - Entrando na configuração deste repositorio, vamos em "Settings" -> "Secrets and Variables" -> "Repository secrets" e clicar no botão "New repository secret" e preencher os dados para cada secret conforme descrito abaixo;
     - Preencha em "Name" o nome da secret e em "Secret" o conteúdo protegido.
     -   Teremos 3 secrets inicialmente:


| **Name** | Secret       |
|------------------|---------------|
| DOCKERHUB_USERNAME | Usuáiro para login no DockerHub. |
| DOCKERHUB_TOKEN**  | Senha para login no DockerHub. |
| K8S_KUBECONFIG**   | Arquivo de configuração do kubernetes. |


3. Ao fazer um commit de um arquivo na branch main, teremos um processo de CI-CD sendo iniciado.
