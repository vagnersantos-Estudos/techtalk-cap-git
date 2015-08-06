#Roteiro de apresentação

- Criar repositório local
```
mkdir proj1
cd proj1
cat "linha 1 - inicial" > f1.md
git status
git init
git status
```

- Primeiro commit
```
git add f1.md
git commit -m "commit inicial"
```

- Mostrar a area de stage - _staged_ e _working directory_
```
cat "linha 1 - arquivo 2" > f2.md
mkdir dir1
cat "linha 1 - inicial - commit inicial" > f1.md
git status
```
- Stash
    - `git stash;  git status`
    - `git stash list`
    - `git stash pop;  git status`
    - `git stash clear`
    - `git stash list`

- mostrar add (file) e add (_ponto_)
```
git add .
git status
```

```
touch f3.md
touch dir1/f4.md
cd dir1
git add .
cd ..
git status
```

```
touch f5.md
touch dir1/f6.md
git add .
git status
```

- mostrar o **diff**
    - `git diff --cached`
    - `git grep "inicial"`
    - `git grep "linha"`
- desfazer tudo
```
ls
git status
git reset --hard HEAD
ls
git status
```

- Criar repositório remoto - **mudar de diretório**
    - `git init --bare repo1.git`
    - `git init --bare repo2.git`
- Conectar com repositório remoto - **voltar para o repositório**
    - adicionar remoto `git remote add origin url`
    - adicionar remoto `git remote add repo2 url`
    - trocar url `git set-url origin url`
- Enviar as alterações
    - `git push origin master`
    - `git push repo2 master`
- Novo working directory - simular 2 usuários - **mudar de diretório**
    - `git clone repo1.git proj2`
 
- Criar branch local - **voltar para proj1**
```
git branch b1
cat "linha 2" >> f1.md
git status
git commit -m "Commit linha 2 no branch"
git log -1
```

```
git branch master
cat "linha 1" >> f2.md
git add f2.md
git status
git commit -m "Commit f2 linha 1 no master"
git status
git log -1
```

- Fazer merge - *mostrar método comum do README.md*
```
git branch b1
git pull --rebase origin master
```

- Confito - **proj2**
```
git branch b1p1
cat f1.md
cat "linha 3" >> f1.md
git commit -m "Linha 3"
git pull --rebase origin master
```

- Arrumar o conflito e continuar
    - `git rebase --continue`
    
- Criar branches remotos `git push b1p1`

- Mostrar alias
    - vim .gitconfig
    - [alias]
