
# BRANCHES (ramificação)

Branches são como uma linha do tempo.

Quando você faz o 1º commit do seu repositório, o Git automáticamente cria a 1ª branch chamada master .

Quando necessário, você poderá criar outras branchs, como uma forma de ramificar o repositório e trabalhar em paralelo.

![](img/branch.png)

Exemplificando, vamos supor que você tenha um repositório do projeto de um site. Em algum momento você deseja fazer algumas modificações para aprimorar o site, modificando todo o estilo css da página. Porém será um processo mais demorado, e enquanto você continua a desenvolver o html, não quer que essas alterações em andamento do css prejudiquem ou até impessam seu trabalho com o html.
Ao mesmo tempo, você não pode simplesmente fazer um gitignore do css, pois afetaria o desenvolvimento html.
Assim você, cria uma nova ramificação da parte css. E pode fazer commits para cada branch separadamente, do html seguindo a linha do tempo principal master e a parte css em outra branch.
Assim, o último estado do css antes de ser ramificado da master, continuará lá ativo até que você termine as alterações e volte a atualização final para a branch master.

Outra exemplificação seria, quando uma equipe deseja ramificar o trabalho de cada um, para permitir o trabalho em paralelo quando necessário.

## Criar uma nova branch

```
git branch nome_da_nova_branch
```

\>>> ATALHO <<<
É possível também criar uma branche e já ir para ela automaticamente sem a necessidade do comando git branch e depois git checkout, para isso:
```
git checkout -b nome_da_nova_branch
```

## Efetivar branch através do commit

A ramificação só é efetivada quando você commitar o arquivo na ramificação.
Não se esqueça de commitar com o terminal ajustado na branch como explicado no tópico anterior.
![](img/commit_branch.png)

## Criar branch no repositório remoto

Quando criamos uma branch no repositório local, será necessário criar a mesma branch no repositório remoto.
Isso pode ser feito pelo próprio site do Github ou pelo terminal:
```
git branch master:nome_da_nova_branch
```

Lembrando que, quando trabalhamos em equipe, geralmente criamos ramificações somente no nosso repositório local, e ao final fazemos push somente do que é necessário no repositório remoto. Tudo isso vai depender de cada caso.

No tópico a seguir veremos um atalho para Criar branch já trackeada ao repositório remoto.

## Criar branch já trackeada ao repositório remoto

```
git branch nome_da_nova_branch origin/nome_da_nova_branch
```

## Visualizar Branchs

### Visualizar todas as braches (LOCAIS e REMOTAS)

```
git branch -a
```

### Visualizar braches LOCAIS

```
git branch
```

### Visualizar braches REMOTAS

```
git branch -r
```

Em qual branch estou?
com o comando git branch, o terminal mostrará todas as branchs existentes no repositório, e a branch em que você está irá aparecer em verde com \* (asterísco)
![](img/git_branch.png)

### Último commit foi commitado em qual branch?


```
git log --oneline
```

O terminal irá mostrar todos os commits realizados e na 1ª linha, podemos verificar através de HEAD em qual branch está o último commit.

## Mudar de branch, commitar entre branchs

Quando quiser mudar de branch para commitar, basta digitar no terminal:
```
git branch checkout nome_da_branch
```

## Deletar uma branch local

Para deletar uma branch, é necessário que você não esteja nela. Então certifique-se de que está na branch master antes de execultar o código.
```
git branch -d nome_da_branch_deletar
```

Pode acontecer de o Git acusar que a branch não foi completamente mesclada. Você pode mesclar corretamente e excluir. Ou, caso queira excluir e não mesclar, não salvando assim o commit, basta trocar o -d por -D:
```
git branch -D nome_da_branch_deletar
```

## Deletar uma branch remota

```
git push --delete
```

# Mesclar branches: merge e rebase

Supondo que naquele exemplo anterior, você terminou suas alterações em paralelo no css e deseja que a brach "teste", seja mesclada com a master para prosseguir com o projeto em completo.

1º certifique-se que você esteja na branch "master", se não estiver, use:
 ```
branch checkout master
```

## A diferença entre mesclar branches com merge e com rebase

* **merge**: mescla e a existência da ramificação fica registrada em um commit merge. Tem como vantagem manter um histórico leal.

* **rebase**: o Git irá "rebasear" e as ramificações passarão a ser uma só recriando uma base linear na branch master.
No momento em que você cria a ramificação, o Git guarda o estado dos determinados arquivos e quando você faz rebase, o Git compara os arquivos anteriores com os novos e é como se fizesse um novo commit e a ramificação, praticamente, não tivesse existido.

## :::merge::: para Mesclar branches

Use o comando merge para mesclar:
```
git merge nome_da_branch_que _deseja_mesclar -m "mensagem sobre o commit"
```

No caso do exemplo:
```
git merge testar
```

Ou seja, uma vez, que já estamos em "master", informamos ao git para "trazer"/"mesclar" a branch testar com master.

:::Agora, existem algumas excessões:::

Caso não tenha sido criado nenhum commit na branch master que entre em conflito com os commits do branch paralelo, temos o que chamamos de "fast-forward", os commits da branch passam automaticamente para a branch principal (master) sem conflito ou complicações.

Caso algum commit entre em conflito, o merge automático não vai funcionar, e temos que seguir alguns passos adicionais. Assim teremos que decidir como resolver o conflito com nossos arquivos, seja adicionando-os, ou excluindo, dependendo do caso.

Feito o merge certinho, podemos deletar a branch adicional, caso não seja mais necessária, seguindo os passos já mencionados anteriormente (```git branch -d nome_da_branch_a_deletar```)

## :::rebase::: para Mesclar branches

```
git rebase nome_da_branch_que_deseja_mesclar
```

Cuidado, sempre é aconselhavel somente fazer rebase em branchs locais, uma vez que fazer isso em branches compartilhadas com outras pessoas pode gerar conflitos.

Em alguns casos em que a branch master tiver commits à frente de outra branch, será necessário fazer um rebase ao contrário.

Ou seja, fazer o rebase a partir da outra branch para levar a master para lá (fazendo isso você iguala a linha do tempo) e depois fazendo um novo rebase para levar/tombar da nova branch para a branch master. Isso irá gerar um fast forward sem conflitos na branch master compartilhada.
Para ilustrar melhor esta situação, veja o exemplo:

# Corrigir conflitos

Lembre-se que se o seu terminal estiver apontando para uma determinada branch, todas as alterações que você estiver fazendo sobre os documentos irão refletir naquela branch em questão.

Então, não se esqueça de alterar a branch quando necessário. Uma vez que alterações realizadas no mesmo documento local irão "aparecer" de maneira diferente no próprio documento, dependendo da branch em que você estiver.

Muitas vezes os conflitos entre arquivos acontecem justamente porque algumas linhas de código, por exemplo, estão de forma diferente dependendo da branch.

Por isso, para resolver esse tipo de conflito, é necessário ver qual linha do arquivo está desatualizada em relação à outra branch e atualizá-la.

### Conflitos e abortar merge

Antes de finalizar o processo de rebase, para corrigir conflitos, etc, é possível cancelar a operação com:
```
git merge --abort
```

Algumas vezes podem ocorrer problemas de conflitos entre os commits, neste caso você deverá corrigir os conflitos e abortar o merge ou para continuar depois de corrigir basta fazer o merge novamente.

### Conflitos e abortar rebase

Antes de finalizar o processo de rebase, para corrigir conflitos, etc, é possível cancelar a operação com:
```
git rebase --abort
```

Algumas vezes podem ocorrer problemas de conflitos entre os commits, neste caso você deverá corrigir os conflitos e abortar o rebase ou para continuar depois de corrigir, não é necessário começar a operação novamente como ocorre com o merge, aqui podemos continuar de onde paramos com:
```
git rebase --continue
```

## Tracking: rastreando branchs entre repositório local e remoto

Pode acontecer durante os commits locais, de estar desatualizado no repositório remoto, para resolver isso:


```
git push -u origin master
```

Neste exemplo, na hora de fazer o push, acrescenta-se -u para atualizar e igualar a branch master nos repositórios. Lembrando que usamos "origin" como exemplo (conforme explicado é um nome que se dá), e usou-se a branch master, mas pode ser feito para qualquer outra branch que se deseja atualizar a posição.

Feito isso uma vez, a branch de ambos repositórios será sempre rastreada e atualizada durante os push normais.
Lembrando que os repositórios remotos que são clonados para o repositório local já vem trackeados automaticamente.
Então se você "mandar" um ```git push``` ele já opera sozinho sem necessidade de acrescentar origin master, por exemplo.

Quando fazemos um ```git push origin master``` para enviar as atualizações de commits para o repositório
