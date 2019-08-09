# docker-laravel-postgres-nginx
Docker Compose para ambiente, com postgresql, reddis, nginx e php-fpm
# Pré-requisitos
* Docker em execução na máquina host.
O Docker Compose em execução na máquina host.
* Conhecimento básico do Docker.
 

# Instalação
+ Para começar, siga os seguintes passos:
+ Clone o repo.
+ `cd laravel-docker-postgres` para o diretório do projeto.
+ `cd` web e execute o comando para criar um novo projeto no diretório ** application **.
+ `cd ..` para retornar o diretório do projeto.
+ `cp .env.example .env` para usar o arquivo de config env
+ Execute o `docker-compose up -d` para iniciar os containers.
+ Visite http://stack.aplicativo.local para ver seu aplicativo Laravel.
+ Tente conectar 127.0.0.1:5432 para acessar o Postgres
+ Após o início, observe que um diretório e um arquivo serão criados com o nome * postgres * e o arquivo * data *, esses arquivos são arquivos de banco de dados

# uso:
+ `docker-compose up -d` para iniciar todos os containers
+ `docker-compose down` para parar todos os containers
+ Se você precisar reiniciar após modificar o * docker-compose.yml * restart com o `docker-compose down` e` docker-compose up -d`

# Imagens
+ redis: alpine
+ postgres: 9.5-alpine
+ nginx: alpine
+ php71-fpm: latest

# Arquivos Fonte

## No diretório ** sourcefiles **, existem outros diretórios: ** php-fpm ** e ** nginx **:

# Solução de problemas
- Para testar os servicos podentro do container utilize o nome do container: app-redis, app-postgres, app-webserver, app-php-fpm

# SSL

## Se você precisar reiniciar após modificar o * Dockerfile * e ter a solução de problemas:
+ Verifique todos os contêineres em execução: `docker ps -a`
+ Pare todos os containers e remova: `docker stop $ (docker ps -a -q)` e `docker rm $ (docker ps -a -q)`
+ Tente começar de novo `docker-compose up -d`