# nodejs-in-container
Um exemplo simples de Node.js executando em container usando Docker

## Construindo a imagem

Uma **imagem** é uma espécie de pacote que contém tudo que você precisa para executar sua aplicação. O Dockerfile é um arquivo que contém todas as instruções para criar uma imagem com o que você precisa.

```shell
docker build -t my-node-app .
```

Onde:
* `docker build` é o comando para construir uma imagem a partir de um Dockerfile
* `-t my-node-app` é o nome que você quer dar para a imagem
* `.` é o local onde está o Dockerfile

## Criar um container

Um **container** é uma instância de uma imagem em execução. Um container nasce para isolar a execução de um processo. Logo, quando o processo morre, o container deixar de existir.

```shell
docker run -p 49160:8080 -d my-node-app
```

Onde:
* `docker run` é o comando usado para criar o container
* `-p 49160:8080` mapeia a porta 8080 do container para a 49160 do host
* `-d` diz para executar o container em background (libera o terminal)
* `my-node-app` é a imagem que será usada para criar o container

## Comandos úteis

* `docker logs <nome do container>` para ver os logs expostos pelo processo que executa no container
* `docker ps -a` para listar todos os containers (parados ou não)
* `docker stop <nome do container>` para parar um container
* `docker start <nome do container>` para iniciar/reiniciar um container
* `docker rm <nome do container>` para remover um container
* `docker -i -t <nome do container> /bin/bash` para acessar o shell do container
