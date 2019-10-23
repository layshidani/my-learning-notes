# Git Dicas
*Substituir comando entre < >*

## Histórico - Listar o que você fez no git

Enquanto o `git log` exibe apenas os commits, o `git reflog` exibe todo o histórico, incluindo: commits, checkout, merge, rebase etc.

```bash
git reflog
```

## Atalho para fazer push sem digitar o nome da branch em que você está (HEAD)
```bash
git push origin +HEAD
```

## Alterar (Reescrever) mensagem do último commit

```bash
git commit -m  'mensagem certa' --amend
```

ou (neste caso, irá abrir o editor no terminal para alterar):

```bash
git commit -v --amend

# digite
Y

# tecle enter
# altere a mensagem e depois ctrl + c para sair
```

## Refazer o último commit

### Refazer o último commit utilizando a mensagem do commit anterior

Considere ter esquecido alguma alteração em um arquivo após ter commitado. Você pode utilizar o `amend` para commitar de novo utilizando a mesma mensagem do último commit:

```bash
# primeiro add o arquivo e em seguida:

git commit --amend --reuse-message HEAD
```

ou

### Refazer o último commit

```bash
# primeiro add o arquivo e em seguida:

git commit --amend --no-edit
```

## Desfazer commits

- com **soft**: apaga só os commits
- com **hard**: apaga os commits e o código

### Desfazer o último commit

```bash
# mantendo as alterações do commit que você deseja desfazer:
git reset --soft HEAD^

# deletando todas as alterações do commit que você deseja desfazer:
git reset --hard HEAD^
```

### Desfazer commits por quantidade (do mais atual para o mais antigo)

```bash
# Desfaz apenas os commits
git reset --soft HEAD~<quantidade de commits>

# Desfaz os commits e o código
git reset --hard HEAD~<quantidade de commits>
```

## Procurar commits com uma mensagem/palavra

```bash
git log -S <"string-to-search">
```

## Verificar log entre datas

Exemplo:

```bash
git log --since='JAN 01 2019' --until='DEC 25 2019'
```

## Desfazer todas as alterações (untracked)

- visualizar arquivos que estão fora da *working tree*:
  ```bash
  git clean -n -d
  ```
- deletar arquivos:
  ```bash
  git clean -f -d
  ```

## Desfazer todas as alterações (tracked)

```bash
git checkout .
```

## Voltar (checkout) para versão anterior de arquivo

```bash
git checkout <hash> <file-name.extension>
```

## Renomear branch
- local:
  ```bash
  git branch -m <new-name>
  ```

- remota, seguir os passos adicionais:
  ```bash
  git push origin :<old-name> <new-name>

  # ou
  git push origin --delete <old-name>
  git push origin <new-name>
  ```

- Resetar a branch *upstream* para o novo nome da branch:
  ```bash
  git push origin -u <new-name>
  ```

## Remover arquivo adicionado acidentalmente

### Arquivo ainda não commitado:

```bash
git reset </path/file-name.extension>
```

### Arquivo já commitado:

```bash
git reset --soft HEAD~1

git reset </path/file-name.extension>

rm </path/file-name.extension>

git commit
```

## Desfazer merge e manter o histórico de commits

```bash
# ir para a master
git checkout master

# git log para verificar a hash correta
git log --oneline

# fazer a reversão utilizando a hash do merge correspondente
git revert -m 1 <merge-commit-hash>
```

## Remover tag de uma branch
- remota:
  ```bash
  git push origin :refs/tags/<tag-name>
  ```
- local:
  ```bash
  git tag -d <tag-name>
  ```

## Squash ('comprimir' commits em um só)
Considerando que você deseja comprimir/transformar seus últimos 5 commits em 1 só.. para isso fazemos o squash.

- desfaz os últimos 5 commits: `git reset --soft HEAD~5`
- faz o processo de add e commit com a mensagem certa
- faz push para o repositório remoto

## Cherry Pick

> git cherry-pick is a powerful command that enables arbitrary Git commits to be picked by reference and appended to the current working HEAD. Cherry picking is the act of picking a commit from a branch and applying it to another. git cherry-pick can be useful for undoing changes. For example, say a commit is accidently made to the wrong branch. You can switch to the correct branch and cherry-pick the commit to where it should belong.
> [Atlassian](https://www.atlassian.com/git/tutorials/cherry-pick)

### Pick 1 commit

```bash
git cherry-pick <hash>
```

### Pick vários commits

```bash
git cherry-pick <hash1> <hash2> <hash3>
```

### Pick de um commit até outro commit

```bash
git cherry-pick <hash1...hash3>
```

## git log do último commit
```bash
git log -1
```

---

## Git Stash
> O git stash armazena temporariamente as alterações que você fez na sua cópia de trabalho para poder trabalhar em outra coisa e depois voltar e reaplicá-las posteriormente.
> [Atlassian](https://www.atlassian.com/git/tutorials/saving-changes/git-stash)

Opções de Git stash ([Atlassian](https://www.atlassian.com/git/tutorials/saving-changes/git-stash)):
![Git stash options](./img/git-stash-options.svg)

- stash **tracked files**:
  ```bash
  git stash
  ```

- stash também dos **untracked files**:
  ```bash
  git stash -u

  # -u = --include-untracked
  ```

- stash todos os arquivos, incluindo os **ignored files**:
  ```bash
  git stash -a

  # -a = --all
  ```

também é possível adicionar mensagens/descrições aos *stashs*, assim como fazemos com os commits:

```bash
git stash save <"message">
```

### Listar stashs

```bash
git stash list
```

### Deletar *stash* específica

```bash
git stash drop stash@{<index>}
```

### Deletar todas *stash*

```bash
git stash clear
```

### Reaplicando alterações que estão em *stash*

- Padrão, último *stash*:
  ```bash
  git stash apply
  ```
- Escolher qual *stash* (como em um array, utilize o `git stash list` para visualizar a lista de *stashs*):
  ````bash
  git stash pop stash@{<index>}
  ```

### Visualizar Stash diff (stash show)

```bash
git stash show

# ou, para visualização completa (-p = --patch):

git stash show -p
```

### Criar branch a partir de *stash*

```bash
git stash branch <branch-name> stash@{<index>}
```
