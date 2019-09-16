# Git Dicas
*Substituir comando entre < >*

## Histórico - Listar o que você fez no git

Enquanto o `git log` exibe apenas os commits, o `git reflog` exibe todo o histórico, incluindo: commits, checkout, merge, rebase etc.

```bash
git reflog
```

## Alterar (Reescrever) mensagem do último commit

```bash
git commit -v --amend

// digite
Y

// tecle enter
// altere a mensagem e depois ctrl + c para sair
```


## Commitar utilizando a mensagem do commit anterior

Considere ter esquecido alguma alteração em um arquivo após ter commitado. Você pode utilizar o `amend` para commitar de novo utilizando a mesma mensagem do último commit

```bash
git commit --amend --reuse-message HEAD
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

```bash
git branch -m <old-name> <new-name>
```

**Caso, também queira renomear uma branch remota, seguir os passos adicionais:**

```bash
git push origin --delete <old-name>
git push origin <new-name>
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
