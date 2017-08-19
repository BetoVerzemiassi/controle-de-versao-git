# Comandos GIT

* **git tag:** É possível criar tags com o qualquer nome, para que não fiquemos presos a um determinado padrão de nomenclatura de versões. Isso nos permite inclusive marcarmos o repositório como "v0.1a", "v0.1b" com a finalidade de definirmos versões preliminares, de acordo com a necessidade do projeto atual.

* **git checkout v0.1:** isualizar como o nosso projeto, junto com todos os seus arquivos html, estava na versão v0.1. Para isso, basta dizer ao git que queremos buscar a versão v0.1. 

* **git diff v0.1 v0.2:** Com esse comando podemos visualizar quais foram as mudanças realizadas nos arquivos de um projeto.

# Como descobrir quem realizou as alterações em um arquivo linha a linha ?

* **git blame index.html:** funcionalidade onde podemos consultar quem foi o autor de cada linha de um arquivo.

> Para sair do blame, basta apertar a tecla q