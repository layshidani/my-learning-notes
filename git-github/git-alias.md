# Git Alias
## Criar alias git
`git config --global alias.seu-alias comando-original`

> A opção --global quer dizer que o alias será aplicado no arquivo .gitconfig dentro do seu diretório home, e por isso o alias será aplicado em todos seus repositórios. Sem esta opção, o alias será aplicado no .gitconfig do repositório atual, logo só será aplicado apenas a ele. --[fonte](https://gist.github.com/kelvinst/331aff32508e2517afbd)

***IMPORTANTE: fechar e abrir de novo o terminal para funcionar.***

[saiba mais](https://haacked.com/archive/2014/07/28/github-flow-aliases/)...

**Alguns aliases**
Você também pode adicionar manualmente em seu arquivo `.gitconfig` da seguinte forma:

```
[alias]
  cm = !git add -A && git commit -m
  lg = log --all --graph --decorate --oneline --abbrev-commit
  co = checkout
  st = status -sb
  ec = config --global -e
  ac = !git add -A && git commit
  up = !git pull --rebase --prune $@ && git submodule update --init --recursive
  cob = checkout -b
  save = !git add -A && git commit -m 'SAVEPOINT'
  wip = !git add -u && git commit -m "WIP"
  undo = reset HEAD~1 --mixed
  amend = commit -a --amend
  wipe = !git add -A && git commit -qm 'WIPE SAVEPOINT' && git reset HEAD~1 --hard
  bclean = "!f() { git branch --merged ${1-master} | grep -v " ${1-master}$" | xargs git branch -d; }; f"
  bdone = "!f() { git checkout ${1-master} && git up && git bclean ${1-master}; }; f"
```
