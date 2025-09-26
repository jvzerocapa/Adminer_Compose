# Adminer via Docker Compose

Este projeto utiliza o **Adminer**, uma ferramenta web leve para gerenciar bancos de dados, similar ao **phpMyAdmin**, mas com suporte a múltiplos bancos, incluindo:

- MySQL / MariaDB
- PostgreSQL
- SQLite
- MS SQL Server
- Oracle
- Outros via ODBC

O setup é feito via **Docker Compose** para facilitar a instalação e execução.

## Docker Compose

O arquivo `docker-compose.yml` incluído define um serviço para o Adminer:

```yaml
version: '3.8'

services:
  adminer:
    image: adminer
    container_name: adminer
    ports:
      - "8080:8080"
    restart: always
Explicação dos parâmetros
image: adminer – Usa a imagem oficial do Adminer do Docker Hub.

container_name: adminer – Nome do container.

ports: "8080:8080" – Porta 8080 do host mapeada para porta 8080 do container.

restart: always – Reinicia automaticamente o container em caso de falha ou reboot do host.

Como iniciar o Adminer
Navegue até a pasta do projeto no terminal.

Execute:


docker compose up -d
Verifique se o container está rodando:
docker ps

Acessando a interface
Abra o navegador e acesse:

http://localhost:8080

Você verá a tela de login do Adminer. Para conectar a um banco:

Sistema: escolha o tipo do banco (ex.: MS SQL Server).

Servidor: IP ou hostname do banco.

Usuário: nome do usuário.

Senha: senha correspondente.

Base de dados: (opcional) nome do banco.

Links úteis
Documentação oficial do Adminer -> https://www.adminer.org/en/
Imagem oficial no Docker Hub -> https://hub.docker.com/_/adminer
