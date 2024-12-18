# CRIANDO UMA IMAGEM DO PROJETO.

- <DOCKER_USERNAME> Troque para o seu username.
- Lembre de estar dentro do diretório do projeto para executar o comando de criação da imagem.

```
docker build -t <DOCKER_USERNAME>/getting-started-todo-app
```



# VERIFICANDO AS IMAGENS PRESENTES NA MÁQUINA.

```
docker image ls
```
Esse listará todas as imagens de docker presentes na máquina.



# FAZENDO UPLOAD DA IMAGEM PARA O **DOCKER HUB**.

- <DOCKER_USERNAME> Lembre de trocar para seu username.

````
docker push <DOCKER_USERNAME>/getting-started-todo-app
````



# RODANDO UM CONTAINER (E JÁ BAIXANDO ELE DO DOCKER HUB) PELO CÓDIGO (CLI).

````
docker run -d -p 8080:80 docker/welcome-to-docker
````
- docker -> Troque pelo nome do usuário do qual você quer buscar o container.
- welcome-to-docker -> É o nome do container que queremos baixar daquele usuário.
- Portas para acessar o continer.

Ex.: 
````
docker run -d -p 8080:80 nome_meu_amigo/nome_container
````



# VER QUAIS CONTAINERS ESTÃO RODANDO NA MINHA MÁQUINA.

````
docker ps
````
Esse comando acima vai mostrar quais containers estão RODANDO na minha máquina. Mas se eu quiser ver todos que eu possuo na máquina, mesmo os que não estão rodando, é só incluir a tag ````-a````. 
````
docker ps -a
````

# PARANDO A EXECUÇÃO DE UM CONTAINER

`````
docker stop <the-container-id>
`````
Você não precisa fornecer todo o código do ID para finalizar a execução de um container, bastar fornecer ao menos uns 4 dígitos do container que o CLI já vai conseguir identificar. 



