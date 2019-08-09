# Stack Sudo Cloud
Docker Compose para ambiente, com postgresql, reddis, nginx e php-fpm

# Pré-requisitos
* Docker em execução na máquina host.
O Docker Compose em execução na máquina host.
* Conhecimento básico do Docker.

# Instalação
+ Para começar, siga os seguintes passos:
+ Clone o repo.
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

# DNS's Internos
- Para testar os servicos por dentro do container utilize o nome do container: app-redis, app-postgres, app-webserver, app-php-fpm

# Código Fonte
- O codigo fonte precisa estar dentro da pasta application.

# Imagens
+ redis: alpine
+ postgres: 9.5-alpine
+ nginx: alpine
+ php71-fpm: latest

# Arquivos Fonte

## No diretório sourcefiles, existem outros diretórios: php-fpm e nginx:

# Solução de problemas
Para problemas com a reutilização dos containers execute os seguintes comandos:
- docker-compose down
- docker container prune
- docker network prune

# SSL
- A URL com ssl que está a funcionar e stack.aplicativo.local , você precisa apontar dentro do hosts da sua maquina windows ou linux stack.aplicativo.local para 127.0.0.1

- Para gerar um certificado SSL personalizado entre no https://www.sslforfree.com/ gere o certificado , troque o mesmo dentro da pasta do projeto /sourcefiles/nginx/ssl/ pelo conteudo dos certificados gerados e troque o nginx.conf o server_name para sua url gerada.
e após isso aponte o dominio no hosts da sua maquina para 127.0.0.1

## Se você precisar reiniciar após modificar o Dockerfile para solução de problemas:
+ Verifique todos os contêineres em execução: `docker ps -a`
+ Pare todos os containers e remova: `docker stop $ (docker ps -a -q)` e `docker rm $ (docker ps -a -q)`
+ Tente começar de novo `docker-compose up -d`
