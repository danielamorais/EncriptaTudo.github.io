# Coletivo Encripta Tudo

O Coletivo Encripta Tudo busca trazer principalmente para a UNICAMP discussões sobre segurança na internet, privacidade, criptografia e software livre.

## Requisitos

* git

* jekyll

* ruby e gem

## Como rodar o projeto

Instale o Ruby e Gem:

```
$ sudo aptitude install ruby-dev gem 

$ sudo gem install jekyll
```

*Obs.: Em distribuições .rpm, utilize ruby-devel.*

Faça download do projeto em sua máquina e execute localmente:
```
$ git clone https://github.com/EncriptaTudo/EncriptaTudo.github.io.git
$ cd EncriptaTudo.github.io
$ jekyll serve -w 
```

Agora acesse localhost:4000 em seu navegador.

## Como criar um novo post

O Jekyll suporta markdown e o "transforma" para uma página estática HTML, para criar um novo post basta criar um arquivo com a extensão .md no diretório *_posts*.
Para o nome do arquivo, utilize o padrão **ano-mes-dia-nomedopost.md**

Note que pode ser necessário executar o Jekyll novamente para o post ser carregado corretamente:
```
$ jekyll serve -w
```
Após finalizar a criação do post, copie apenas o conteúdo que está dentro de *_site* e envie para a branch **gh-pages**. 

A branch **master** contém todos os arquivos de configurações do Jekyll e a **gh-pages** contém somente os arquivos estáticos necessários para exibição do site. 

``` 
$ git branch
* gh-pages
$ git add *
$ git commit -m "Meu novo post" 
$ git push origin gh-pages
```

Lembre-se de encaminhar o seu post *.md* para a branch **master** também. 

Documentação útil para git: http://rogerdudler.github.io/git-guide/

## Erros comuns 

1. Caso obtenha o seguinte erro ao instalar o Jekyll:
```
zlib is missing; necessary for building libxml2
```

Instale o seguinte pacote e tente novamente instalar o Jekyll: 

```
$ sudo aptitude install zlib1g-dev
```

2. Caso o css não esteja carregando corretamente, altere em *index.html* que está do diretrio de *_site* o caminho para encontrar o arquivo CSS:

```
<link rel="stylesheet" type="text/css" href="/css/style.css" >
```

Verificar issue: https://github.com/EncriptaTudo/EncriptaTudo.github.io/issues/2

3. Se ao acessar localhost:4000 obter uma página com layout quebrado e sem os devidos posts, verifique se o comando do jekyll foi executado no local correto.
O comando *jekyll serve -w* deve ser executado dentro do diretório */EncriptaTudo.github.io*
