# Exercicio Aula 02




## A

a) No working dir, executar o comando:
`echo 01 > arquivo.txt`

Comando para verificação:
`ls`

Resultado:
>arquivo.txt

## B

b) Adicionar o arquivo no staging e conferir o status:
`git add arquivo.txt`

Comando para verificação:
`git status`

Resultado:
>On branch master
No commits yet
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   arquivo.txt

## C

c) Commitar o arquivo do staging com a descrição "git add example - arquivo.txt“
`git commit -m "git add example - arquivo.txt" `

Comando para verificação:
`git log`

Resultado:
>commit 43906c27c9b075dbaf8ac70a0f36625e406ff3c0 (HEAD -> master)
Author: anilho <alicio@contaswap.com>
Date:   Tue Aug 6 17:43:11 2024 -0300
    git add example - arquivo.txt

## D

d) Sobrescrever o conteúdo do arquivo.txt:
`echo 02 > arquivo.txt`

Comando para verificação:
`cat arquivo.txt`

Resultado:
>02

## E

e) Verificar o diffing no arquivo

Comando para verificação:
`git diff arquivo.txt`

Resultado:
>diff --git a/arquivo.txt b/arquivo.txt
index 8a0f05e..9e22bcb 100644
--- a/arquivo.txt
+++ b/arquivo.txt
@@ -1 +1 @@
-01
+02

e1) checagem adicional para validar o status do git
`git status`

Resultado:
>On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   arquivo.txt

## F

f) Adicionar novamente o arquivo no staging e conferir o status
`git add arquivo.txt`

Comando para verificação:
`git status`

Resultado:
>On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   arquivo.txt

## G

Verificar o diffing no arquivo
`git diff arquivo.txt`

Resultado:
>sem resposta - nao identificou alterações

## H

h) Sobrescrever o conteúdo do arquivo.txt:
`echo 03 > arquivo.txt`

Comando para verificação:
`cat arquivo.txt`

Resultado:
>03

## I

i) Verificar o diffing no arquivo (aqui o diff é entre o arquivo local e o staged)
`git diff arquivo.txt`

Resultado:
>diff --git a/arquivo.txt b/arquivo.txt
index 9e22bcb..75016ea 100644
--- a/arquivo.txt
+++ b/arquivo.txt
@@ -1 +1 @@
-02
+03

i1) se quiser ver o diff com o arquivo que está em staged com o comitado (o conteudo do commit é 01) 
`git diff --staged arquivo.txt`

Resultado:
>diff --git a/arquivo.txt b/arquivo.txt
index 8a0f05e..9e22bcb 100644
--- a/arquivo.txt
+++ b/arquivo.txt
@@ -1 +1 @@
-01
+02




## J

j) Fazer o restore do arquivo da área de staging e verificar o status
`git restore arquivo.txt`

Comando para verificação:
`cat arquivo.txt`

Resultado:
>02

## K

k) Realizar o commit do arquivo e verificar o log
`git commit arquivo.txt -m "restore do arquivo"`

Comando para verificação:
`git log`

Resultado:
>commit 76266b8c0cc839132f2b69334a3289e6b0c56c6a (HEAD -> master)
Author: anilho <alicio@contaswap.com>
Date:   Tue Aug 6 18:08:21 2024 -0300

    restore do arquivo

commit 43906c27c9b075dbaf8ac70a0f36625e406ff3c0
Author: anilho <alicio@contaswap.com>
Date:   Tue Aug 6 17:43:11 2024 -0300

    git add example - arquivo.txt


## L

l) Adicionar um arquivo gitignore com o seguinte conteúdo:
*.txt

Comando 
`echo "*.txt" > .gitignore`

## M

m) Criar um arquivo novo.txt e verificar o status
`echo novo > novo.txt`

Comando 
`git status`

Resultado:
> On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.gitignore

nothing added to commit but untracked files present (use "git add" to track)
