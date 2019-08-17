# GIT e GITHUB
Meu Notebook - Lays Marie Hidani

## Sumário

*   [\# O que é Git e Github](#O-que-é:-Git-e-GitHub)
    *   [Mais sobre o Git](#Mais-sobre-o-Git)

    *   [Terminal](#Terminal)
    *   [GUI](#GUI)

    *   [Mais sobre o GitHub](#Mais-sobre-o-GitHub)
*   [# Como funciona o repositório](#Como-funciona-o-repositório)
    *   [Principais estados do git](#Principais_estados-do-git)

    *   [Untracked (sem rastro/não traçado)](#Untracked-(sem-rastro/não-traçado))
    *   [Staged ("palco"/área de preparo)](#Staged-("palco"/área-de-preparo))
    *   [Commit (Consolidar)](#Commit-(Consolidar))
  *   [\# Modified (Modificado)](#Modified-(Modificado))

*   [\# Comandos Terminal](#comandos-terminal)
*   [\# Configuração inicial/preparatória](#Configuração-inicial/preparatória)
    *   [Configurar usuário](#Configurar-usuário)
    *   [Configurar email](#Configurar-email)
    *   [Verificar configuração](#Verificar-configuração)
    *   [Trocar nome de usuário ou email](#Trocar-nome-de-usuário-ou-email)
    *   [Apagar nome de usuário](#Apagar-nome-de-usuário)
    *   [Apagar e-mail](#Apagar-e-mail)
    *   [Diretório do repositório](#Diretório-do-repositório)
    *   [Visualizar o arquivo oculto do Git](#Visualizar-o-arquivo-oculto-do-Git)
*   [\# Status do diretório](#Status-do-diretório)
    *   [Status dentro de pastas do diretório](#Status-dentro-de-pastas-do-diretório)
    *   [Iniciar um Git](#Iniciar-um-Git)
    *   [Desligar Git no repositório](#Desligar-Git-no-repositório)
*   [\# GitHub: cadastrar chave SSH. Autenticação](#GitHub:-cadastrar-chave-SSH.-Autenticação)
*   [\# Sobre o parentesco entre commits](#Sobre-o-parentesco-entre-commits)
    *   [Visualizar pais](#Visualizar-pais)
*   [\# Utilizando o Git](#Utilizando-o-Git)
*   <!-- TODO parei aqui -->
    *   [\[add\] Adicionar arquivos ao STAGED :::de UNTRACKED ou de MODIFIED para STAGED:::](#\[add\]-Adicionar-arquivos-ao-STAGED-:::de-UNTRACKED-ou-de-MODIFIED-para-STAGED:::)
    *   [\[commit\] :::de STAGED para COMMITED:::](#commit_sc)
    *   [Atalho para add e commit de uma vez](#atalho_add)
    *   [Modificar o editor de texto padrão do Git](#change_editor)
    *   [Recapitulando...](#recapitulando_utilizando_git)
*   [Visualizar alterações (git log)](#git_log)
    *   [Visualizar Commits resumidos em 1 linha](#git_log_oneline)
    *   [Visualizar últimos commits](#git_log_ultimos)
    *   [Visualizar alterações em todas as branchs resumidas em uma linha](#git_log_alt)
    *   [Visualizar graficamente](#git_log_graph)
    *   [Visualizar detalhes de um commit específico](#git_log_det)
    *   [\[diff\] Histórico de diferença entre modificações](#git_log_diff)
    *   [ver histórico com formatação específica (hash abreviada, autor, data e comentário)](#git_log_hist_format)
    *   [Visualizar histórico de um arquivo específico pelo caminho](#git_log_hist_caminho)
    *   [Visualizar histórico de um arquivo específico que contêm uma determinada palavra](#git_log_hist_palavra)
    *   [Exibir histórico modificação de um arquivo com parâmetros](#git_log_hist_param)
    *   [Visualizar commits de determinado autor](#git_log_autor)
*   [\[gitignore\] Ignorar determinados arquivos na hora de commitar](#gitignore)

    [\>ATALHO gitignore: todos os arquivos de mesma extensão](#gitignore_atalho)

    [\>Adicionar um arquivo que esta listado no .gitignore (geral ou do repositório)](#gitignore_add)
- [GIT e GITHUB](#git-e-github)
  - [Sumário](#sum%c3%a1rio)
- [O que é: Git e GitHub](#o-que-%c3%a9-git-e-github)
  - [Mais sobre o Git](#mais-sobre-o-git)
    - [Terminal](#terminal)
    - [GUI](#gui)
  - [Mais sobre o GitHub](#mais-sobre-o-github)
- [Como funciona o repositório](#como-funciona-o-reposit%c3%b3rio)
  - [Principais estados do git](#principais-estados-do-git)
    - [Untracked (sem rastro/não traçado)](#untracked-sem-rastron%c3%a3o-tra%c3%a7ado)
    - [Staged ("palco"/área de preparo)](#staged-%22palco%22%c3%a1rea-de-preparo)
    - [Commit (Consolidar)](#commit-consolidar)
    - [Modified (Modificado)](#modified-modificado)
- [\# Comandos Terminal](#comandos-terminal)
- [Configuração inicial/preparatória](#configura%c3%a7%c3%a3o-inicialpreparat%c3%b3ria)
  - [\# Configurar usuário](#configurar-usu%c3%a1rio)
  - [\# Configurar email](#configurar-email)
  - [\# Verificar configuração](#verificar-configura%c3%a7%c3%a3o)
  - [\# Trocar nome de usuário ou email](#trocar-nome-de-usu%c3%a1rio-ou-email)
  - [\# Apagar nome de usuário](#apagar-nome-de-usu%c3%a1rio)
  - [\# Apagar e-mail](#apagar-e-mail)
  - [\# Diretório do repositório](#diret%c3%b3rio-do-reposit%c3%b3rio)
  - [\# Visualizar o arquivo oculto do Git](#visualizar-o-arquivo-oculto-do-git)
- [\# Status do diretório](#status-do-diret%c3%b3rio)
  - [\# Status dentro de pastas do diretório](#status-dentro-de-pastas-do-diret%c3%b3rio)
  - [\# Iniciar um Git](#iniciar-um-git)
  - [\# Desligar Git no repositório](#desligar-git-no-reposit%c3%b3rio)
- [GitHub: cadastrar chave SSH. Autenticação](#github-cadastrar-chave-ssh-autentica%c3%a7%c3%a3o)
  - [1º passo: Gerar as chaves](#1%c2%ba-passo-gerar-as-chaves)
  - [2º passo: Adicionar sua chave SSH pública](#2%c2%ba-passo-adicionar-sua-chave-ssh-p%c3%bablica)
  - [3º passo: adicionar repositório local para remoto](#3%c2%ba-passo-adicionar-reposit%c3%b3rio-local-para-remoto)
- [Sobre o parentesco entre commits](#sobre-o-parentesco-entre-commits)
  - [Visualizar pais](#visualizar-pais)
- [Utilizando o Git](#utilizando-o-git)
  - [\[add\] Adicionar arquivos ao STAGED](#add-adicionar-arquivos-ao-staged)
  - [\[commit\]](#commit)
  - [Atalho para add e commit de uma vez](#atalho-para-add-e-commit-de-uma-vez)
  - [Modificar o editor de texto padrão do Git](#modificar-o-editor-de-texto-padr%c3%a3o-do-git)
  - [Recapitulando...](#recapitulando)
- [Visualizar alterações (git log)](#visualizar-altera%c3%a7%c3%b5es-git-log)
  - [Visualizar Commits resumidos em 1 linha](#visualizar-commits-resumidos-em-1-linha)
  - [Visualizar últimos commits](#visualizar-%c3%baltimos-commits)
  - [Visualizar alterações em todas as branchs resumidas em uma linha](#visualizar-altera%c3%a7%c3%b5es-em-todas-as-branchs-resumidas-em-uma-linha)
  - [Visualizar graficamente](#visualizar-graficamente)
  - [Visualizar detalhes de um commit específico](#visualizar-detalhes-de-um-commit-espec%c3%adfico)
  - [\[diff\] Histórico de diferença entre modificações](#diff-hist%c3%b3rico-de-diferen%c3%a7a-entre-modifica%c3%a7%c3%b5es)
  - [ver histórico com formatação específica (hash abreviada, autor, data e comentário)](#ver-hist%c3%b3rico-com-formata%c3%a7%c3%a3o-espec%c3%adfica-hash-abreviada-autor-data-e-coment%c3%a1rio)
  - [Visualizar histórico de um arquivo específico pelo caminho](#visualizar-hist%c3%b3rico-de-um-arquivo-espec%c3%adfico-pelo-caminho)
  - [Visualizar histórico de um arquivo específico que contêm uma determinada palavra](#visualizar-hist%c3%b3rico-de-um-arquivo-espec%c3%adfico-que-cont%c3%aam-uma-determinada-palavra)
  - [Exibir histórico modificação de um arquivo com parâmetros](#exibir-hist%c3%b3rico-modifica%c3%a7%c3%a3o-de-um-arquivo-com-par%c3%a2metros)
  - [Visualizar commits de determinado autor](#visualizar-commits-de-determinado-autor)
- [\[gitignore\] Ignorar determinados arquivos na hora de commitar](#gitignore-ignorar-determinados-arquivos-na-hora-de-commitar)
  - [ATALHO gitignore: todos os arquivos de mesma extensão](#atalho-gitignore-todos-os-arquivos-de-mesma-extens%c3%a3o)
  - [Adicionar um arquivo que esta listado no .gitignore (geral ou do repositório)](#adicionar-um-arquivo-que-esta-listado-no-gitignore-geral-ou-do-reposit%c3%b3rio)
- [Git diff](#git-diff)
  - [Visualizar últimas atualizações que estão em :::modified:::](#visualizar-%c3%baltimas-atualiza%c3%a7%c3%b5es-que-est%c3%a3o-em-modified)
  - [Visualizar últimas modificações em um arquivo específico](#visualizar-%c3%baltimas-modifica%c3%a7%c3%b5es-em-um-arquivo-espec%c3%adfico)
  - [Visualizar últimas atualizações que estão em :::staged:::](#visualizar-%c3%baltimas-atualiza%c3%a7%c3%b5es-que-est%c3%a3o-em-staged)
  - [comparar modificações entre commits](#comparar-modifica%c3%a7%c3%b5es-entre-commits)
- [Desfazer alterações](#desfazer-altera%c3%a7%c3%b5es)
  - [Desfazer alterações: arquivo em :::untracked:::](#desfazer-altera%c3%a7%c3%b5es-arquivo-em-untracked)
  - [Desfazer alterações: arquivos em :::modified::: (já feito add, mas não commit)](#desfazer-altera%c3%a7%c3%b5es-arquivos-em-modified-j%c3%a1-feito-add-mas-n%c3%a3o-commit)
  - [Desfazer alterações: arquivos já commitados](#desfazer-altera%c3%a7%c3%b5es-arquivos-j%c3%a1-commitados)
    - [1º caso SOFT](#1%c2%ba-caso-soft)
    - [2º caso MIXED](#2%c2%ba-caso-mixed)
    - [3º caso DELETAR HARD](#3%c2%ba-caso-deletar-hard)
  - [Reverter alterações](#reverter-altera%c3%a7%c3%b5es)
    - [1° caso](#1%c2%b0-caso)
    - [2° caso](#2%c2%b0-caso)
- [Arquivo deletado manualmente pelo OS, como commitar](#arquivo-deletado-manualmente-pelo-os-como-commitar)
- [Desfazer: arquivo deletado da máquina](#desfazer-arquivo-deletado-da-m%c3%a1quina)
- [Remover arquivo/pasta pelo Git](#remover-arquivopasta-pelo-git)
  - [Remover arquivo](#remover-arquivo)
  - [Remover pasta](#remover-pasta)
- [Renomear arquivo local](#renomear-arquivo-local)
  - [1ª opção: renomear pelo computador](#1%c2%aa-op%c3%a7%c3%a3o-renomear-pelo-computador)
  - [2ª opção: pelo Git](#2%c2%aa-op%c3%a7%c3%a3o-pelo-git)
- [1ª vez conectar conta do Github](#1%c2%aa-vez-conectar-conta-do-github)
  - [Gerar chaves SSH](#gerar-chaves-ssh)
  - [Adicionar chave SSH](#adicionar-chave-ssh)
- [\[remote add\] Repositório local para remoto - da sua máquina para Github](#remote-add-reposit%c3%b3rio-local-para-remoto---da-sua-m%c3%a1quina-para-github)
  - [Verificar se está conectado](#verificar-se-est%c3%a1-conectado)
  - [Verificar detalhes do repositório no Github](#verificar-detalhes-do-reposit%c3%b3rio-no-github)
- [push: sincronizar alterações locais para o repositório do Github](#push-sincronizar-altera%c3%a7%c3%b5es-locais-para-o-reposit%c3%b3rio-do-github)
- [clone: trazer repositório remoto para o arquivo local](#clone-trazer-reposit%c3%b3rio-remoto-para-o-arquivo-local)
- [pull: sincronizar alterações do repositótio remoto para o local](#pull-sincronizar-altera%c3%a7%c3%b5es-do-reposit%c3%b3tio-remoto-para-o-local)
- [Trabalhando com repositórios de outras pessoas](#trabalhando-com-reposit%c3%b3rios-de-outras-pessoas)
  - [Modo Colaborador](#modo-colaborador)
  - [Pull request](#pull-request)
  - [FORK, uma cópia de outros repositórios para o seu repositório](#fork-uma-c%c3%b3pia-de-outros-reposit%c3%b3rios-para-o-seu-reposit%c3%b3rio)
- [BRANCHES (ramificação)](#branches-ramifica%c3%a7%c3%a3o)
  - [Criar uma nova branch](#criar-uma-nova-branch)
  - [Efetivar branch através do commit](#efetivar-branch-atrav%c3%a9s-do-commit)
  - [Criar branch no repositório remoto](#criar-branch-no-reposit%c3%b3rio-remoto)
  - [Criar branch já trackeada ao repositório remoto](#criar-branch-j%c3%a1-trackeada-ao-reposit%c3%b3rio-remoto)
  - [Visualizar Branchs](#visualizar-branchs)
    - [Visualizar todas as braches (LOCAIS e REMOTAS)](#visualizar-todas-as-braches-locais-e-remotas)
    - [Visualizar braches LOCAIS](#visualizar-braches-locais)
    - [Visualizar braches REMOTAS](#visualizar-braches-remotas)
    - [Último commit foi commitado em qual branch?](#%c3%9altimo-commit-foi-commitado-em-qual-branch)
  - [Mudar de branch, commitar entre branchs](#mudar-de-branch-commitar-entre-branchs)
  - [Deletar uma branch local](#deletar-uma-branch-local)
  - [Deletar uma branch remota](#deletar-uma-branch-remota)
- [Mesclar branches: merge e rebase](#mesclar-branches-merge-e-rebase)

# O que é: Git e GitHub

Git e GitHub são duas coisas diferentes.

Git é um sistema de controle de versões. Todo o trabalho acontece na sua máquina (computador)

Já o GitHub é uma plataforma de hospedagem, controle de versão e colaboração. Funciona como uma espécie de "rede social" colaborativa dos programadores. Podendo visualizar o seu código e de toda a comunidade dentro da plataforma, clonar, etc.
[Faça o download do Git](https://git-scm.com/downloads)
[Acesse o GitHub](https://github.com/)

## Mais sobre o Git

![](img/git1.png)

> É um sistema de controle de versões distribuído, usado principalmente no desenvolvimento de software, mas pode ser usado para registrar o histórico de edições de qualquer tipo de arquivo. O Git foi inicialmente projetado e desenvolvido por Linus Torvalds para o desenvolvimento do kernel Linux, mas foi adotado por muitos outros projetos.
> Cada diretório de trabalho do Git é um repositório com um histórico completo e habilidade total de acompanhamento das revisões, não dependente de acesso a uma rede ou a um servidor central.
> \-Wikipedia-

> O workflow básico do Git pode ser descrito assim:
>
> 1.  Você modifica arquivos no seu diretório de trabalho.
> 2.  Você seleciona os arquivos, adicionando snapshots deles para sua área de preparação.
> 3.  Você faz um commit, que leva os arquivos como eles estão na sua área de preparação e os armazena permanentemente no seu diretório Git.
>
>
> \- GIT -

[Saiba mais](https://git-scm.com/book/pt-br/v1/Primeiros-passos-No%C3%A7%C3%B5es-B%C3%A1sicas-de-Git)

### Terminal

Os comandos e interação do Git se dá pelo terminal (prompt de comando/shell/etc), após a instalação, também serão adicionados dois novos terminais a sua máquina (built-in do Git): o Git CMD (padrão Windows) e o Git Bash (padrão MacOs e Linux).

Mesmo que seu OS seja Windows, Mac ou Linux, você pode optar por usar qualquer um dos terminais GitCMD ou Git Bash.

Você pode optar por usar o terminal de sua própria máquina, ou os terminais do Git, ou mesmo qualquer outro de sua preferência.

### GUI

Você poderá ainda usar o GUI ("Graphical User Interface"), onde, ao invés de executar os comandos via terminal, você poderá usar uma interface gráfica. O próprio Git já vem com um GUI na instalação (built-in): o Git GUI, mas existem outros para baixar conforme a sua preferência. Acesse o link abaixo para fazer o download: [GUIs](https://git-scm.com/downloads/guis)

## Mais sobre o GitHub

![](img/github.png)

> GitHub é uma plataforma de hospedagem de código-fonte com controle de versão usando o Git. Ele permite que programadores, utilitários ou qualquer usuário cadastrado na plataforma contribuam em projetos privados e/ou Open Source de qualquer lugar do mundo. GitHub é amplamente utilizado por programadores para divulgação de seus trabalhos ou para que outros programadores contribuam com o projeto, além de promover fácil comunicação através de recursos que relatam problemas ou mesclam repositórios remotos (issues, pull request).
> \-Wikipedia-
>
> O GitHub é uma plataforma de hospedagem de código para controle de versão e colaboração. Ele permite que você e outros trabalhem juntos em projetos de qualquer lugar.
> \-GitHub- [Saiba mais](https://guides.github.com/)

Basta acessar o site do [GitHub](https://github.com/) e se cadastrar para começar a usar o site.

# Como funciona o repositório

![repositório](img/7.png)

## Principais estados do git

*   Preparado (staged/index)
*   Modificado (modified)
*   Consolidado (comitted)

*   Clone: copiar do repositório para seu arquivo local
*   Push: copiar do arquivo local para o repositório
*   Add: comando para que o Git passe a "olhar" seus arquivos. Os arquivos passam de "Untracked" para "Staged" antes do 1º commit, e de "Modified" para "Staged", do 1º commit em diante
*   Commit: consolidar todas as mudanças
*   Pull: salvar commits do servidor para seu arquivo local

### Untracked (sem rastro/não traçado)

É o primeiro estado do arquivo. Os arquivos estão na sua máquina, mas não estão aos cuidados do Git. Uma vez adicionado (add) ao Git, ele não volta mais ao estado de untracked.
![](img/1.png)

### Staged ("palco"/área de preparo)

Depois de dar o comando "add" ao Git, os arquivos passam para a área "staged", onde o git já está cuidando dos arquivos e está de olho em todas as alterações que estão acontecendo.

Em uma definição livre, pode ser considerada uma área de preparo, uma espécie de "palco", onde o Git assiste da plateia todas as modificações :)

Não é um passo essencialmente obrigatório. Podendo simplesmente usar o atalho de adicionar juntamente com o commit, porém é muito útil para ter mais controle sobre as alterações antes de commitar. Dessa forma, é recomendada.
![](img/2.png)

### Commit (Consolidar)

Depois que comitamos o arquivo ele passa para a área "commited", que em uma tradução livre, consolida todas as mudanças do arquivo, oficializa.
![](img/3.png)

### Modified (Modificado)

Sempre que ocorrer uma modificação no arquivo, ele sairá de "commited" e passará para uma nova área chamada "modified".

Quando o arquivo é "add" pela primeira vez ele sai de "untracked" (não rastreado) e passa a ser rastreado pelo Git, dessa forma, ele não irá voltar a estar em "untracked".

Ao invés disso, sempre que houver uma modificação, ele sairá de "commited" e passará para "modified", aguardando ser adicionado (add) a "staged" novamente e depois ser commitado.
![](img/4.png)
![](img/5.png)
![](img/6.png)

# \# Comandos Terminal

Utilizaremos para esses exemplos o terminal Git Bash.

Antes de executar os comandos de Git, o terminal deverá sempre estar configurado para a pasta do repositório em questão. Ver # Diretório do repositório

# Configuração inicial/preparatória

A configuração inicial deve ser feita somente quando inicia-se um novo repositório. Em repositórios já existentes, pula-se essa etapa.

## \# Configurar usuário

```
git config --global user.name nome_de_usuario
```


(ex: git config --global user.name hlays)

Tipos de usuário:

*   Global: configuração para minha máquina
*   System: todos os usuários dessa máquina vão usar o mesmo login
*   Local: para um repositório específico, caso específico. Por exemplo,uma pessoa usa sua máquina certa vez para commitar.

Assim, pode-se configurar como global, local, ou system, dependendo do caso. Na maior parte das vezes, utiliza-se global.

## \# Configurar email

```
git config --global user.email e-mail
```

ex:
```
git config --global user.email meuemail@gmail.com
```

## \# Verificar configuração

```
git config --global --list
```

Pode abreviar usando --l ao invés de --list
ex:
```
git config --global --l
```

## \# Trocar nome de usuário ou email

Basta executar o comando config de novo.

## \# Apagar nome de usuário

```
git config --global --unset user.name
```

Neste caso, levando em consideração que foi configurado usuário como global.

## \# Apagar e-mail

```
git config --global --unset email
```

Neste caso, levando em consideração que foi configurado usuário como global.

## \# Diretório do repositório

```
cd caminho_da_pasta
```

Dicas de abreviação/atalho

*   Para voltar uma pasta acima/pasta anterior. Digite: cd ..
*   Diretório principal: cd ~
*   Listar o conteúdo de um diretório. Dentro da pasta em questão digite: dir
*   Adicionar local padrão (Se você está sempre usando o mesmo diretório e deseja deixá-lo como padrão para sempre que abrir o terminal): basta clicar com o botão direito do mouse sobre o ícone do terminal do Git >>> Propriedades >>> Atalho >>> Iniciar em: >>> coloque o caminho para o seu diretório padrão >>> Aplicar >>> ok
    ![](img/local_padrao.png)
    ![](img/local_padrao2.png)

ex:
```
cd desktop/projetos/site
```

Para listar os arquivos da pasta `ls`

## \# Visualizar o arquivo oculto do Git

```
cd .git
ls
```

# \# Status do diretório

Este comando será muito utilizado durante o uso do Git, por ele poderemos visualizar qual o status de nossos arquivos, se untracked, modified, staged, commited..
```
git status
```

## \# Status dentro de pastas do diretório

```
git status -u
```

## \# Iniciar um Git

```
git init
```

## \# Desligar Git no repositório

Se por algum motivo não deseja mais usar o controle de versões e deseja desligar o Git do repositório (esse comando irá remover/deletar o Git do repositório em questão):
```
rm -rf .git/
```

# GitHub: cadastrar chave SSH. Autenticação

Na primeira vez que você for fazer push de um repositório de sua máquina para o GitHub (somente a primeira vez mesmo, os próximos repositórios não necessitarão dessa autenticação), você deverá gerar um conjunto de chaves SSH, uma pública e uma privada, elas servirão para autenticar seus gits no GitHub. Onde sua Chave pública do github será autenticada pela chave privada da sua máquina. Não se preoculpe que não é tão complicado quanto parece. Para acessar o passo-a-passo do próprio GitHub, basta acessar: [link](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

## 1º passo: Gerar as chaves

No terminal digite o comando abaixo. Você deverá informar o mesmo e-mail que está cadastrado no GitHub
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

O prompt irá informar que está gerando as chaves. depois disso irá perguntar onde você deseja salvar a chave privada, se quiser no local já sugerido pelo git, basta teclar ENTER.

Depois disso ele irá perguntar se você deseja salvar uma senha adicional, geralmente não é necessário, então basta teclar ENTER. caso for inserir senha, deve-se digitar a senha e depois confirmar a mesma.

## 2º passo: Adicionar sua chave SSH pública

Entre no diretório das chaves salvas:
```
cd ~/.ssh/
```

Depois irá mostrar o nome das chaves, a que interessa é a .pub, copie o nome dela. Pode usar o comando \[cat\] ou \[more\].
Digite:
```
cat id_rsa.pub
```

Irá aparecer sua chave pública no terminal..copie.

Vá no site do Github, clique em sua imagem de perfil
(botão verde no canto superior direito da tela) >>> settings (lado esquerdo da tela) >>> SSH and GPG keys >>> new SSH key (botão verde no canto superior direito da tela) >>> Digitar o nome/titulo (geralmente coloca-se o nome do seu pc) e colar a chave >>> Add SSH Key.

## 3º passo: adicionar repositório local para remoto

1.  criar um repositório no Github e copiar o endereço SSH do repositório.
2.  no terminal digitar o comando abaixo ((este nome origin pode ser o nome que você quiser, mas é mais comumente utilizado o origin):
    ```
    git remote add origin endereço_ssh
    ```

3.  enviar arquivos para o GitHub:
    ```
    git push origin master
    ```
4.  da primeira vez que conectar ao GitHub (seu primeiro repositório nesta máquina) irá pedir usuário e senha do Github, após informar, ele automaticamente irá fazer o push dos seus arquivos.

Quando quiser verificar se o repositório está conectado, digite:
```
git remote
```
(deverá aparecer: origin)

Para verificar detalhes:
```
git remote -v
```

# Sobre o parentesco entre commits

Os commits aparecem da ordem de criação mais recente para a mais antiga, e dizemos que o commit mais recente é filho do mais antigo, sucessivamente.
Ex:
$ git log --oneline
a7b2440 (HEAD -> master) c4 - alterações
d6ec6be C3 - Acresc nome do curso e prof
13e1d6c C2a - outro html chamado curso com o link do curso
bd5dcc8 C2 - add novo paragrafo
98f7dd4 C1 - h1 e parágrafo
e0a52d7 C0 - Primeiro commit

Então: C0 é pai de C1, C1 é pai de C2, C4 é filho de c3, etc.

## Visualizar pais

```
git log --parents --oneline
```

# Utilizando o Git

## \[add\] Adicionar arquivos ao STAGED
:::de UNTRACKED ou de MODIFIED para STAGED:::

Adiciona o arquivo para os cuidados do git (stage: área do Git)
```
git add nome do arquivo.extensão
```

Para adicionar todos os arquivos de uma vez:
```
git add .
```

## \[commit\]
:::de STAGED para COMMITED:::

Commitar (o git tira uma “foto” do estado atual do projeto p/ acompanhar as mudanças)
```
git commit -m “mensagem de minha preferência”
```

Ex:
```
git commit -m “C0 - Primeiro commit do projeto”
```

Obs: \*Se vc não colocar a mensagem, automaticamente ele irá abrir um editor de texto para que você digite a mensagem.

Neste caso, digite a mensagem no editor que irá abrir, crtl + S para salvar e depois feche o editor, ou digite q no git bash (se tiver aberto dentro do próprio prompt do git) para sair do editor.

## Atalho para add e commit de uma vez

```
git commit -am “mensagem de minha preferência”
```

## Modificar o editor de texto padrão do Git

O editor de texto padrão do Git é o VIM, durante a instalação você também recebe um opção de alterar essa configuração. Mas se por algum motivo, depois de instalado, desejar mudar o editor padrão:
```
git config --global core.editor nome do editor que deseja
```

## Recapitulando...

Sempre que quiser atualizar uma mudança no repositório, repetir:

1.  `git add nome_do_arquivo_extensão`
2.  `git commit + mudanças realizadas ex: git commit -m “C1 - Alterações na parte de css do código”)`

Uma vez, que devemos passar os arquivos de MODIFIED para COMMITED novamente.

Sempre que ocorre alguma mudança em um arquivo, o Git inteligentemente irá mostrar no terminal todas as alterações sofridas pelo documento, com linhas na cor verde e sinal (+) para as linhas de código que são adicionadas ao arquivo e cor vermelha e sinal (-) para o que é retirado.

# Visualizar alterações (git log)

Para visualizar todos os commits realizados Modo completo (tecle ENTER ou seta para baixo até chegar ao final (end).. para sair: tecle (q)

```
git log
```

## Visualizar Commits resumidos em 1 linha

```
git log --oneline
```

## Visualizar últimos commits

Para visualizar o ultimo commit em uma linha:
```
git log -1 --oneline
```

Para visualizar os 2 últimos commits em uma linha:
```
git log -2 --oneline
```

Assim, por diante, basta trocar o número. Para verificar não resumidos em uma linha, basta tirar o trecho de código --oneline.

## Visualizar alterações em todas as branchs resumidas em uma linha

Você visualizar todos os commits realizados no repositório independentemente da branch, através do comando:
```
git log --oneline --all
```

## Visualizar graficamente

Ou para ficar ainda melhor, é possível verificar graficamente:
```
git log --oneline --all --graph
```

## Visualizar detalhes de um commit específico

Visualização completa, contendo modificações realizadas:
```
git show número_da_hash
```

Você pode encontrar a hash de cada commit através do comando
```
git log --oneline
```

\>>> Por exemplo, quero informações sobre o commit C5, cuja hash é 574cc01.

![](img/hash.png)
Digito no terminal:

```
git show 574cc01
```

Para Visualização resumida (sem info sobre linhas de código modificadas):
```
git log -1 stat
```

## \[diff\] Histórico de diferença entre modificações

```
git log -p -posição_do_commit
```

Ex: Exibir histórico com diff das duas últimas alterações:
```
git log -p -2
```

## ver histórico com formatação específica (hash abreviada, autor, data e comentário)

```
git log --pretty=format:"%h - %an, %ar : %s"
```

Onde:

*   %h: Abreviação do hash;
*   %an: Nome do autor;
*   %ar: Data;
*   %s: Comentário.

## Visualizar histórico de um arquivo específico pelo caminho

```
git log -- caminho_do_arquivo
```

## Visualizar histórico de um arquivo específico que contêm uma determinada palavra

```
git log --summary -S [caminho_do_arquivo]
```

## Exibir histórico modificação de um arquivo com parâmetros

O M pode ser substituido por: Adicionado (A), Copiado (C), Apagado (D), Modificado (M), Renomeado (R), entre outros.
```
git log --diff-filter=M --
```

## Visualizar commits de determinado autor

```
git log --author=nomedoautor
```

Ex:
```
git log --author=hlays
```

# \[gitignore\] Ignorar determinados arquivos na hora de commitar

Serve para listar todos os arquivos que não deverão ser lançados no repositório, ou seja, que estão na pasta mas deverão ser ignorados pelo git. Recomenda-se criar apenas um único gitignore em trabalhos em grupo e commitá-lo, assim todos terão acesso aos nomes dos arquivos ignorados e evita de que um mesmo arquivo seja ignorado mais vezes por outras pessoas.
No github você pode encontrar vários templates de gitignore.
Passos:

1.  criar um arquivo com extensão (.gitignore) na pasta onde estão os arquivos de commit
2.  num editor de texto adicionar no arquivo .gitignore o nome dos arquivos que deverão ser ignorados. Todos esses arquivos depois de terem o nome salvo no .gitignore não aparecerão mais em git status. exemplo:
    `fonte.txt` e
    `img21.png`
3.  salvar e fazer o commit deste arquivo .gitignore como outro arquivo qualquer

## ATALHO gitignore: todos os arquivos de mesma extensão

Vamos supor que queremos que o git ignore todos os arquivos em formato txt que estão na pasta. Basta salvar no arquivo .gitignore \* + extensão do tipo de arquivo a ser ignorado (no editor de texto):
`*.txt`

## Adicionar um arquivo que esta listado no .gitignore (geral ou do repositório)

```
git add -f nome_do_arquivo.extensão
```

# Git diff

Para comparar:

*   modified e commited:
    ```
    git diff
    ```
*   staged e commited:
      ```
      git diff --staged``` ou ```git diff --cached
      ```
*   commited e commited:
    ```
    git diff hash_do_commit_antigo..hash_do_commit_atual
    ```

## Visualizar últimas atualizações que estão em :::modified:::

Geralmente de um arquivo que você acabou de mexer e ainda não fez commit das últimas atualizações.
O console irá mostrar todas as modificações realizadas que estão diferentes da última atualização commitada pelo git (compara modified e commited).

Em verde (+) tudo o que foi acrescentado e em vermelho (-) tudo o que foi removido.

Tecle ENTER ou seta para baixo até chegar ao final do documento (END) e então tecle (q) para sair. Comando:
```
git diff
```

## Visualizar últimas modificações em um arquivo específico

```
git diff nome_do_arquivo.extensão
```

## Visualizar últimas atualizações que estão em :::staged:::

Para visualizar modificações que não estão em modified acrescentar (--staged ou --cached)
```
git diff --staged
```

## comparar modificações entre commits

```
git diff hash_do_commit_antigo..hash_do_commit_atual
```

Exemplo. Dados os commits abaixo, para comparar C5 e C6:
Lays@Krasco MINGW64 ~/desktop/teste\_git (master)

$ git log --oneline

99a627b (HEAD -> master) c7 - atualizações diversas
6d30e14 C7 - mudanças no corpo do projeto
fc5cbee C6 - arquivo git ignore
574cc01 C5 - Acrescentado img e algumas alterações
a7b2440 c4 - alterações
d6ec6be C3 - Acresc nome do curso e prof
13e1d6c outro html chamado curso com o link do curso
bd5dcc8 "add novo paragrafo em "
98f7dd4 C1 - h1 e parágrafo
e0a52d7 C0 - Primeiro commit
```
-> comando : git diff 574cc01..fc5cbee
```

Resumindo...
![](img/modificar.png)

# Desfazer alterações

Supondo que você deseja desfazer alterações no arquivo..vai depender em que ponto ele está: untracked, modified, commited.
\* Ao invés de desfazer, o mais aconselhado é reverter, para ao invés de apenas deletar a alteração, manter documentado. Ver reverter mais abaixo.

## Desfazer alterações: arquivo em :::untracked:::

```
git checkout --nome_do_arquivo.extensão
```

## Desfazer alterações: arquivos em :::modified::: (já feito add, mas não commit)

1.  1º tira ele de modified e leva de volta para untracked:
    ```
    git reset nome_do_arquivo.extensão
    ```
2.  2º já é possível fazer checkout e reverter alterações
    ```
    git checkout --nome_do_arquivo.extensão
    ```

## Desfazer alterações: arquivos já commitados

### 1º caso SOFT

Tirar arquivo de commit e passar de volta para staged, sem deletar o arquivo, usa-se o comando --soft + a hash do pai, ou seja, a hash do commit anterior ao que eu quero apagar. e depois é possível fazer o checkout.
```
git reset --soft hash_do_pai
```

### 2º caso MIXED

Tirar arquivo de commit e passar para modified (fora do staged), sem deletar o arquivo, usa-se o comando --mixed + a hash do pai, ou seja, a hash do commit anterior ao que eu quero apagar e depois é possível fazer o checkout.
```
git reset --mixed hash_do_pai
```

### 3º caso DELETAR HARD

Tirar arquivo de commit e deletar o arquivo (todos os commits e arquivos que estão depois do que o commit em questão deixam de existir, são deletados e fica só do commit pai/anterior para baixo). Usa-se o comando --hard + a hash do pai, ou seja, a hash do commit anterior ao que eu quero apagar e depois é possível fazer o checkout.
```
git reset --mixed hash_do_pai
```

## Reverter alterações

Quase semelhante ao desfazer, mas nesse caso será criado um commit que indica a reversão. É o mais aconselhado.

### 1° caso

Com mensagem sobre a reversão, neste caso o editor de texto irá abrir para que você insira a mensagem sobre o por que da reversão, ou digite (-m “mensagem”) após o hash
```
git revert hash_do_commit_a_ser_revertido
```

### 2° caso

Sem mensagem sobre a reversão:
```
git revert hash_do_commit_a_ser_revertido --no-edit
```

# Arquivo deletado manualmente pelo OS, como commitar

Quando deletar um arquivo do arquivo local de sua máquina, o git irá reconhecer isso e se você verificar no comando git status irá verificar que ele está em uma nova instância do git chamada “deleted” , para confirmar essa exclusão e manter documentado esse processo.

Deve-se:
```
git rm nome_do_arquivo.extensão
```
```
git commit
```

OU
```
git add nome_do_arquivo.extensão
```
```
git commit
```

Os dois métodos são distintos. Quando removemos pelo sistema operacional ou por alguma ide e queremos commitar essa ação, temos que add ao stage e commitar. Agora se commitarmos diretamente pelo git (com git rm) não precisamos fazer o add, pois a deleção já vai para a stage. Nesse caso é só um corte de caminho para não precisar usar o git add.

# Desfazer: arquivo deletado da máquina

```
git checkout -- nome_do_arquivo.extensão
```

# Remover arquivo/pasta pelo Git

## Remover arquivo

```
git rm nome_do_arquivo.extensão
```

## Remover pasta

```
git rm -r nome da pasta
```

# Renomear arquivo local

## 1ª opção: renomear pelo computador

1.  renomeie normalmente o arquivo pela pasta.
2.  Faça ```git add do arquivo```
3.  Assim ele irá passar para o estado de RENAMED quando você verificar pelo ```git status```
4.  Agora faça o commit do arquivo normalmente com ```git commit```

## 2ª opção: pelo Git

1.  No terminal:
    ```git mv nome_antigo.extensão novo_nome.extensão```
2.  Assim ele irá passar para o estado de RENAMED quando você verificar pelo ```git status```
3.  Agora faça o commit do arquivo normalmente com ```git commit``` para consolidar a mudança

# 1ª vez conectar conta do Github

## Gerar chaves SSH

Quando usar pela primeira vez, deverá conectar a sua conta do Github na sua máquina, para isso, é necessário Connectar o SSH da sua conta. Onde sua Chave pública do github será autenticada pela chave privada da sua máquina. [link para instruções](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

No terminal, digite:
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

O terminal irá informar que está gerando as chaves.
Depois disso irá perguntar onde você deseja salvar a chave privada, se quiser no local já sugerido pelo git, basta teclar ENTER.

Depois disso ele irá perguntar se você deseja salvar uma senha adicional, geralmente não é necessário, então basta teclar ENTER. caso for inserir senha, deve-se digitar a senha e depois confirmar a mesma.

## Adicionar chave SSH

Digite no terminal para entrar no diretório das chaves salvas:
```
cd ~/.ssh/
```

O terminal irá mostrar o nome das chaves, a que interessa é a .pub, copie o nome dela. Pode usar o comando ```cat``` ou ```more```. Digite:
```
cat id_rsa.pub
```

Irá aparecer sua chave pública no terminal (um conjunto de caracteres com diversas linhas..copie.

Agora, vá no site do Github, clique em sua imagem de perfil (botão verde no canto superior direito da tela) >>> settings (lado esquerdo da tela) >>> SSH and GPG keys >>> new SSH key (botão verde no canto superior direito da tela) >>> Digitar o nome/titulo (geralmente coloca-se o nome do seu pc) e colar a chave >>> Add SSH Key.

# \[remote add\] Repositório local para remoto - da sua máquina para Github

1.  criar um repositório no Github e copiar o endereço SSH do repositório.
2.  no terminal digitar:
    ```
    git remote add origin endereço_ssh
    ```
    Este nome origin pode ser o nome que você quiser, mas é mais comumente utilizado o origin. Este comando serve para adicionar seu repositório local no Github.
3.  enviar arquivos para o Github. Digite no terminal:
    ```
    git push origin master
    ```
4.  Da 1ª vez, irá pedir usuário e senha do Github, após informar, ele automaticamente irá fazer o push dos seus arquivos.

## Verificar se está conectado

```
git remote
```

Deve aparecer: origin, ou o nome que você tenha usado.

## Verificar detalhes do repositório no Github

```
git remote -v
```

# push: sincronizar alterações locais para o repositório do Github

Sempre que quiser atualizar os commits locais também no Github fazer:
```
git push origin master
```

# clone: trazer repositório remoto para o arquivo local

Este é o inverso. Quando você cria o repositório no Github e deseja trazer para a máquina, não basta fazer um simples download do repositório, pois não seria uma cópia completa, uma vez que, faria uma cópia dos arquivos simplesmente e não do repositório em si com o Git.
Será necessário clonar o repositório remoto utilizando o comando clone

Não esqueça de estar com o local que deseja salvar o repositório configurado no terminal
```
git clone endereço_do_repositorio
```

você deverá encontrar o endereço SSH do repositório na página do repositório do Github. Fica localizado em um botão verde do lado direito da tela. Você pode clonar tantos seus próprios repositório, quanto em repositórios criados por outras pessoas com quem irá trabalhar no projeto em questão.

# pull: sincronizar alterações do repositótio remoto para o local

```
git pull origin master
```

origin, ou o nome que você tenha usado..

# Trabalhando com repositórios de outras pessoas

## Modo Colaborador

Geralmente, se você colabora com repositórios da empresa onde trabalha, ou em projetos opensource, por exemplo, dos quais você faz parte da equipe, quando você desejar enviar seus commits com alterações do repositório em questão, precisará estar ajustado no Git como Colaborador, caso contrário ao tentar fazer o commit, será informado de "acesso negado".

Para isso, o dono do repositório deverá ir até a página do repositório em questão, clicar em settings >>> colaborators >>> e inserir seu nome de usuário.

Assim, sendo um colaborador, toda vez que enviar um commit, o dono do repoitório será notificado sobre suas alterações e deverá permitir ou não que elas sejam consolidadas.

## Pull request

Geralmente, se você colabora com projetos opensource, por exemplo, dos quais você deseja colaborar de alguma forma, quando você faz alterações em arquivos e deseja commitá-los para o repositório original (que não foi criado por você), deverá solicitar essa permissão através do botão pull request no Github. Suas alterações serão avaliadas e consideradas pelos colaboradores oficiais do repositório.
Isso permite o controle sobre o projeto, sem que qualquer um mexa no repositório sem permissão e evitando alterações indesejadas.

## FORK, uma cópia de outros repositórios para o seu repositório

Quando você faz um fork, cria uma cópia de um repositório remoto de outra pessoa para o seu repositório remoto, assim quando fizer alterações e commits nos arquivos deste repositório, estes serão refletidos no seu repositório e não no original.

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


A diferença entre mesclar branches com merge e com rebase:

merge: mescla e a existência da ramificação fica registrada em um commit merge. Tem como vantagem manter um histórico leal.

rebase: o Git irá "rebasear" e as ramificações passarão a ser uma só recriando uma base linear na branch master.
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

# Tracking: rastreando branchs entre repositório local e remoto

Pode acontecer durante os commits locais, de estar desatualizado no repositório remoto, para resolver isso:


```
git push -u origin master
```

Neste exemplo, na hora de fazer o push, acrescenta-se -u para atualizar e igualar a branch master nos repositórios. Lembrando que usamos "origin" como exemplo (conforme explicado é um nome que se dá), e usou-se a branch master, mas pode ser feito para qualquer outra branch que se deseja atualizar a posição.

Feito isso uma vez, a branch de ambos repositórios será sempre rastreada e atualizada durante os push normais.
Lembrando que os repositórios remotos que são clonados para o repositório local já vem trackeados automaticamente.
Então se você "mandar" um ```git push``` ele já opera sozinho sem necessidade de acrescentar origin master, por exemplo.

Quando fazemos um ```git push origin master``` para enviar as atualizações de commits para o repositório

# Editar url remota

```
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
```

Para conferir se a url foi editada com sucesso, basta digitar o comando abaixo e verificar o endereço correspondente:

```
git remote -v
```
