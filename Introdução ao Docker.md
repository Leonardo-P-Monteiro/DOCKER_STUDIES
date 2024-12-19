# CRIANDO UMA IMAGEM DO PROJETO.

- <DOCKER_USERNAME> Troque para o seu username.
- Lembre de estar dentro do diretório do projeto para executar o comando de criação da imagem.

```
docker build -t <DOCKER_USERNAME>/getting-started-todo-appv .
```
_obs.: Certifique-se de incluir o ponto (.) no final do comando docker build. Isso informa ao Docker onde encontrar o Dockerfile._



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
- 8080:80 -> Portas para acessar o continer.

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



# INSERINDO **TAG** EM UMA IMAGEM DOCKER.

- Entenda isso como um meio de gerenciar versões do containers.

f1477ec11d12 -> ID único da imagem. 

_obs.: Ao invés do **ID** você pode colocar o nome do diretório/projeto e ele vai 
entender normal como se fosse o ID._

**minha-imagem:v1.0** -> Aliase que quero colocar na minha imagem.

````
docker tag f1477ec11d12 minha-imagem:v1.0
````

- Para adicionar mais uma tag a uma imagem que já possui uma tag basta fazer o mesmo procedimento - isso não irá sobrescrever as demais tags associadas a imagem.

````
docker tag minha-imagem:v1.0 meu-repositorio/minha-imagem:latest
````

- Também posso usar o próprio nome da pasta do projeto com o meu nome de usuário
do Docker Hub para definir uma tag ao projeto que o docker vai compreender que estamos inserindo
uma tag nele. 

`````
docker tag f1477ec11d12 devpmonteiro/helloworld-demo-node:1.0
`````

# ETIQUETANDO (**TAGS**) PARA ENVIAR PARA O DOCKER HUB

````
docker tag minha-imagem:v1.0 seunomedeusuario/minha-imagem:v1.0
````
- Neste caso, estamos "etiquetando" a imagem com o **seu nome de usuário do Docker Hub (seunomedeusuario)** para que ela possa ser enviada para o repositório. Para subir para o Docker Hub fica faltando 
apenas o "push" na sequência. Por isso posso fazer o controle das minhas imagens e já com meu nome 
de usuário do Docker Hub sem me preocupar que o projeto seja "upado" e exposto, pois somente 
será feito upload quando passado o comando "push" para o docker e eu indicar a tag a ser feito upload.

- Prefira já etiquetar nesse formato para deixar no ponto de executar apenas o 
comando push e fazer upload, pois sempre que queremos upar nossas imagens e containers
de imagens é preciso inserir nosso nome de usuário do Docker Hub antes do nome do projeto
para que ele seja enviado para o repositório. 

# COMANDO PARA CRIAR UM ARQUIVO DOCKER COMPOSE.

`````

`````