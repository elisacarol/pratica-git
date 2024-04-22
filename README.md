# pratica-git
Repositório para prática de comandos do Git

~~~bash

git config --global core.editor "code --wait"
~~~

O comando acima define o Visual Studio Code como o editor padrão das 
mensagens de commit 

~~~bash
git commit ~~allow-empty
~~~

O parâmetro '--allow-empty' permite a criação de um commit vazio, para 
fins de testes e prática do Git.

~~~bash
git commit -a
~~~

O parâmetro '-a' adiciona todos os arquivos modificados e
não ignorados ao commit atual.

~~~bash
tit checkout -b novoBranch
~~~

O parâmetro '-b' alterna para 'novoBranch' criando o branch, o mesmo
acontece com o comando 'git-switch' com o parâmetro '-c'.

~~~bash
git branch -D nomeBranch
git branch --delete origin nomeBranch
~~~

Para apagar um branch é preciso primeiro apagá-lo (1o comando) e depois propagar
a deleção para o repositório remoto (2o comando ). 

~~~bash

git log -- graph --oneline

~~~

Rebase Interativo

Para alterar o autor de um commit, você pode utiliar o rebase interativo e o comando commit --amend.

Antes, porém, verifique e o editor de mensagens do commit está configurado para o editor do próprio VSCode.

~~~bash

git rebase -i <referenciaCommit>

~~~
A referrência do commit deve ser sempre para o commit anterior ao commit que deve ser alterado.

No editor de commits, altere a instrução do commit desejado de pick pra edit. Em seguida grave e feche o
editor.

O rebase fará uma pausa para que você altere as  informações do autor.

~~~bash 

git commit --amend --reset-author --no-edit

~~~

Caso você queira especificar o autor, utilize a flag --author="Nome do Autor <email@autor>", nesse exato
formato.

Caso seu commit seja vazio, acresente ainda a flag --allow-empty.

Após o reparo do commit , continue o processo do rebase com o comando abaixo.

~~~bash

git rebase -- continue

~~~

Finalmente, confira o novo histórico localmente e envie o repositorio remoto forçadamente.

git push --force

TAGS

~~~bash
    git tag <tag> <referencia>

Utilize o comando tag para adicionar marcos ('milestones') a commits ou outras referências no histórico do Git.
Se você não especificar a referência, o Git vai atribuir a tag ao commit apontado  por HEAD.

Você deve fazer o push das tags para o repositório remoto separadamente com a flag --tags.

~~~bash

    git push --tags

TODO: apagar tags


Cherry-pick

~~~bash

    git cherry-pick <hashCommit>

~~~

O cherry-pick seleciona um commit e o adiciona ao final da arvore de ancestrais do ramo atual.


Apagar um branch

Para apagar um branch local:

~~~bash

    git branch -D <nomeBranch>

Para apagar um branch remoto através do push:

~~~bash

    git push --delete <remote> <nomeBranch>

~~~

