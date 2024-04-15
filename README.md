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

