# Comandos GIT

* **git tag:** É possível criar tags com o qualquer nome, para que não fiquemos presos a um determinado padrão de nomenclatura de versões. Isso nos permite inclusive marcarmos o repositório como "v0.1a", "v0.1b" com a finalidade de definirmos versões preliminares, de acordo com a necessidade do projeto atual.

* **git checkout v0.1:** isualizar como o nosso projeto, junto com todos os seus arquivos html, estava na versão v0.1. Para isso, basta dizer ao git que queremos buscar a versão v0.1. 

* **git diff v0.1 v0.2:** Com esse comando podemos visualizar quais foram as mudanças realizadas nos arquivos de um projeto.

# Como descobrir quem realizou as alterações em um arquivo linha a linha ?

* **git blame index.html:** funcionalidade onde podemos consultar quem foi o autor de cada linha de um arquivo.

> Para sair do blame, basta apertar a tecla q

# Inicialização de um repositório

* O Git é uma ferramenta de controle de versão baseada no sistema de arquivos, ou seja, podemos fazer a associação de uma pasta diretamente a um repositório. 

> **mkdir curso-git**
> **cd curso-git**

# como essa é uma pasta como qualquer outra em nosso computador, será que o git já sabe que ela conterá os arquivos do nosso projeto? Como indicar que essa pasta será o nosso futuro repositório ?

> **git init**

>> Será exibida uma mensagem similar a: **Initialized empty Git repository in /diretorio/repositorio/do/git** E pronto. Já temos um repositório.

* **git ls-files:** Verificando quais arquivos pertencem ao nosso projeto.

* **git status:** Verifica o estado dos arquivos do nosso projeto.

* **git add index.html:** Adicionando arquivos na stage para ser commitado.

# Realizando o primeiro commit no repositório

> **git config --global user.name "seunome"** = Inserir usuário da máquina

> **git config --globa user.email "seuemail@gmail.com"** = e-mail configurado no git no momento que geramos a SSH

* **git commit -m "mesagem":** Realiza o commit e passa uma mensagem explicando o commit feito.

# Fazendo commit sem criar um index / stage

* **git commit -a:** Inclui imediatamente no commit todos os arquivos modificados ou alterados! Porém
não adiciona os arquivos novos. Podemos combinar a opção de mensagem com **git commit -a -m "Mensagem Commit"** para não precisar
escrever a mensagem no editor padrão do console.

