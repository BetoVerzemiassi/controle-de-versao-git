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

* **git log:** Histórico de commit's realizados no projeto.

* **git whatchanged:** Visualiza a mensagem passada no commit e também quais arquivos foram alterados.

* **git whatchanged -p:** Mostra detalhadamente oque foi alterado nos arquivos em um determinado commit.

# Configuração do repositório remoto

* Para conseguirmos compartilhar nosso projeto HTML, precisamos indicar que o diretório do nosso projeto apontará para um repositório remoto, no caso, o que acabamos de criar no Github. Para realizarmos esse processo, o Git possui o comando **git remote add**, com o qual podemos indicar a localização do repositório remoto e o nome que queremos dar para ele (um apelido ou alias).

> A sintaxe completa do comando é:

>> git remote add [alias_do_repositorio] [uri_do_repositorio]

>> git remote add origin https://github.com/BetoVerzemiassi/controle-de-versao-git.git

# Envio dos commits locais para o repositório   

* **git push origin master:** Enviando nossas alterações para o repositório remoto na branch master criada por padrão no momento
que criamos o repositório no GitHub.

> **origin:** Repositório remoto que criamos, no meu caso com nome controle-de-versao-git

> **master:** Branch criada por padrão ao criar repositórios no GitHub

# Contribuição com o projeto: clone de repositórios

* **git clone:** Com essa comando conseguimos baixar para nossa máquina o repositorio que está no Git para realizar alterações.
Basta apena informar a URL do repositório que queremos realizar o clone. Da seguinte forma abaixo:

> git clone https://github.com/BetoVerzemiassi/controle-de-versao-git.git

# Sincronização com as novas alterações do repositório

* Para que a sincronização seja realizada e o desenvolvedor tenha em seu computador as novas versões dos arquivos, basta que ele execute o comando **git pull origin master**

* Outra alternativa é utilizar, no primeiro push, a opção **-u** ou **--set-upstream**. Ela atrela a branch remota à local, fazendo com que não seja mais necessário passar como parâmetros a origem e a branch no comando push, que fica então assim: **git push**.

# Organização do trabalho com branches

* **git branch design:** Cria uma nova branch com nome design, apenas cria.

* **git checkout -b design:** Cria a nova branch e já nos coloca no caminho certo da nova branch.

* **git branch:** Verifica em qual branch estamos atualmente, será visualizado todos as branch criada,
a que estiver com "*" indica que essa é a branch que estamos.

* **git checkout design:** Modificamos de branch com esse comando.

* **git push origin design:** Envia suas atualizações para o repositório na nova branch criada.

* **git pull origin master:** Atualiza nosso projeto local com os arquivos da branch master.

* **git pull origin design:** Atualiza nossos arquivos locais com as atualizações feitas na branch design.

* **git branch -r:** Visualiza as branches já existentes em um repositório remoto.

* **git push -u origin design:** Atualiza o repositório local e remoto, faz o caminho track da branch remota para
nossa branch local.

# Resolução de conflitos

* Muitos desenvolvedores preferem utilizar uma ferramenta gráfica para facilitar o processo de merge manual, pois as diferenças entre cada versão do arquivo são mais facilmente visíveis, muitas vezes tendo alinhamento linha a linha.

* **git mergetool --tool-help:** Mostra no console uma lista de programas possíveis de ser utilizados. Dessa lista, pode-se escolher um, instalar no seu computador e utilizar através do comando **git mergetool -t nome_do_programa**

# Envio dos commits das branches locais para o master remoto

* Para realizar essa tarefa, o primeiro passo, é verificar se a branch master não possui nenhuma nova atualização, ou seja, temos que fazer um checkout da master com git checkout master e, em seguida, realizarmos o git pull para buscar as novas alterações feitas por outras pessoas naquele repositório.

* **git rebase:** Se simplesmente jogássemos o conteúdo da branch "desenvolvimento" para a master, poderíamos ter que tratar conflitos de vários commits ao mesmo tempo além do log dos commits ficarem confusos. Justamente para evitar essa situação, o Git possui o comando git rebase, onde podemos indicar qual é a nova base de commits que deve ser utilizada e resolver os conflitos commit por commit. No nosso caso, queremos que a branch "desenvolvimento" utilize como base de commits a "master" que acabamos de atualizar.

# Como fazer um Merge

* Colocar apenas os commits novos na branch "master", porém, para isso, existe o comando git merge que move os commits de uma determinada branch para outra branch.

* Para utilizá-lo, primeiro é preciso ir para a branch para a qual se quer levar os commits, no caso, a "master" (git checkout master). Em seguida, deve-se dizer para o comando git merge de qual branch virão os commits novos, que, no caso, é a branch "desenvolvimento". Para isso, basta executar git merge desenvolvimento.

# Controle avançado de alterações

* **git diff:** Verifica as alterações que foram feitas, comparando os arquivos.

# Descartando alterações no Working Directory: git checkout

* verificar as alterações que foram feitas com o comando git diff e desfazer as alterações manualmente. Mas e se muita coisa foi alterada dentro de um arquivo? Para este problema, o Git nos possibilita descartar todas as alterações que estão no "Working Directory" de um determinado arquivo. Para isso, utilizamos o comando git checkout passando o nome do arquivo cujas alterações serão removidas. No nosso caso, temos:

> **git checkout nome-do-arquivo**

* **git checkout master nome-do-arquivo:** Esse comando trará o arquivo "proposta_1.html" como ele se encontra na branch "master" e o adicionará ao Index do repositório na branch "desenvolvimento", pronto para um commit.

* **git reset:** Permite desfazer qualquer número de commits, bastando utilizar o hash do commit que queremos manter como
HEAD.

* **git reset --hard:** Com este comando, as alterações são removidas do histórico local de commits e também tanto do index quanto do working directory, permanentemente.

* **git reset --soft:** Com este comando, as alterações são removidas do histórico local de commits, mas não são removidas do index.

* **git revert d5b609...:** Desfaz uma alteraão que um determinado commit fez, bastando apenas passar o identificador do commit.

* **git stash:** Vai guardar as alterações que ainda não foram commitadas, para serem commitadas mais tarde.

* **git stash list:** Com esse comando, conseguimos listar o que guardamos para realizar o commit.

* **git stash pop:** Retomando o ultimo item que estava listando no stash.

* **git stash apply stash@{0}:** Aqui estamos sendo mais especificos ainda para retormar o stash. Retoma de onde paramos
para realizar um ajuste. Assim sem prejudicar as alterações que estavamos realizando.

* **git stash drop:** Apaga/Joga fora nosso stash da alteração temporaria que fizemos.

* **git stash clear:** Exclui todos os estados.

# Procurando Commits que queremos desfazer com Bisect

* **git bisect start:** Passar o commit que achamos que é o bom e logo em seguida o commit que achamos que está com falha.

* **git bisect HEAD:**

* **git bisect good 561f444c85638b2619c15e7eef9f6e313b45db2b:**

* **git bisect bad:**