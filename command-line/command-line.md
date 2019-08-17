*comando entre `< >`: modificar para nome e excluir < >*

# Linha de comando
* Digitar: comando
* Teclar: *ENTER*

<!-- ## Abrir linha de comando
**Windows**
* teclar: windows + R
* digitar: cmd
* teclar: *ENTER* -->

**Bash**
`ctrl + alt + t`

## Acessar informações sobre comandos - Manual (man)
`man <nome-do-comando>`

ou

`<nome-do-comando> --help`

## Break
deu ruim, dá break para interromper o processo.
`ctrl + c`

## Limpar terminal
`clear`

ou atalho teclado: `ctrl + l`

## AutoCompletar nome de arquivos e pastas
`tab`

## Ativar programa em execuçao em segundo plano
`ctrl + z`

## Sair
`exit`

shortcut: `ctrl + d`

## Interromper comando
`ctrl` + `c`

## Quit (q)
`q`

## Histórico de comandos (history)
`history`

---

## Sigla para diretório atual (.)
`.`

## Escrever (>)

## Ler (<)

---
## Mover cursor para o início da linha
`ctrl + a`

## Mover cursor para o final da linha
`ctrl + e`

## Apagar linha inteira
`ctrl + u`

## Apagar linha até o cursor
`ctrl + k`

## Apagar última palavra
`ctrl + w`

## Reescrever última palavra apagada
`ctrl + y`


---

## Mostrar caminho do local atual
(pwd = *P*rint *w*orking *d*irectory)

`pwd`

## Navegar entre pastas (cd)
(cd = *c*hange *dir*ectory)

`cd <nome-da-pasta>`

(-> Entre várias pastas: `cd <nome-da-pasta/nome-da-pasta/nome-da-pasta>`)

## Voltar uma pasta (..)
`cd ..`

## Abrir pasta graficamente através da linha de comando
Navegue até o endereço da pasta que deseja abrir graficamente e depois digite o comando

em qualquer distro:

`xdg-open .`

mint:

`nemo .`

gnome:

`nautilus .`

## Abrir pasta no navegador através da linha de comando
Navegue até o endereço da pasta que deseja abrir graficamente e depois digite o comando

`<nome-do-navegador> .`

## Listar aquivos do diretório (ls)
`dir` (windows)

`ls` (linux)

## Listar com mais detalhes
`ls -l`
`ls -la` ou `ls -a`  (mostra também arquivos ocultos)

## Listar por ordem de tamanho (-S)
`ls -lhS`

## Copiar (cp)
`cp <old> <new>`

ou, caso dê erro ao copiar o diretório:
`cp -Rv <old> <new>`

## Criar novo diretório (mkdir)
(mkdir = '*M*a*k*e *Dir*etory')
`mkdir <nome-diretório>`

## Criar novo arquivo em branco (touch)
(Cria um arquivo em branco se não existe, ou atualiza a data de modificação se existir.)

`touch <nome-do-arquivo.extensão>`

## Criar novo arquivo com texto (echo)
`echo <texto> > <nome-do-arquivo.extensão>`

ex:
`echo teste texto > teste1.txt`
(cria um arquivo com o texto "teste texto" no bloco de notas)

## Adicionar texto a um arquivo existente (>>)
`echo <texto> >> <nome-do-arquivo.extensão>`

## Visualizar conteúdo do arquivo no terminal (cat)
(cat = con*cat*enate)

`cat <nome-do-arquivo.extensão>`

ex:
`cat teste1.txt`

// resultado: teste texto

## Verificar diferença entre dois arquivos (diff)
`diff <file-name-1> <file-name-2>`

## Mover arquivos ou pastas de um diretório para outro (mv)
(mv = *m*o*v*e)

`mv <nome-do-arquivo.extensão/caminho>`

ex1: `mv teste.txt/desktop`

ex2: para um arquivo que está salvo em Lab/Arquivo, quero movê-lo de *Arquivo* para *Lab* que é uma pasta anterior, podemos usar o atalho *..* :
`mv teste.txt ..`

ex3: para mover um arquivo teste1.txt para desktop, o atalho **~**, atalho para a raiz e desktop:
`mv teste1.txt ~/desktop`

ex4: para mover um arquivo teste1.txt que está no desktop para a pasta atual, use o atalho **.**:
`mv desktop/teste1.txt .`


## Renomear arquivos ou pastas
`mv <nome-atual.extensão> <novo-nome.extensão>`

## Copiar arquivo (cp)
(cp = *c*o*p*y)

`cp <nome-do-arquivo.extensão> <nome-da-copia.extensão>`

## Apagar arquivo (rm)
(rm = *r*e*m*ove)

`rm <nome-do-arquivo.extensão>`


## Remover diretório e todos os arquivos dentro dele
`rm -rf <nome-do-diretorio>/`

## Verificar tipo de arquivo (file)
`file <nome-do-arquivo.extensão>`

ex: `file teste.txt`
=> resultado: ASCII text

---
## Verificar se um programa está disponível (which)

`which <NOME_DO_PROG>`

---

## Fazer download através de uma url (curl)
`curl <URL>`

## Fazer download de arquivos grandes através de uma url (curl -OL)
`curl -OL <URL>`

---

## Repetir comandos prévios
`!`

ou

`ctrl + r`


---
# Processos em execução
`ps`

## Processor ordenados
`top`

## kill processos (kill)
`kill -<NÌVEL> <PID>`

onde *PID* é o ID do processo, é possível encontrá-lo com o comando `ps`.

## Kill processos combinando com o nome do processo
`pkill -<NÌVEL> -f <NOME_DO_PROCESSO>`

---
# Arquivos de texto

## Mostrar arquivo de texto grande (less)
`less <NOME_DO_ARQ.EXTENSAO>`

- navegue pelo texto usando seta para cima e para baixo
- tecle `q` (quit) para sair

### Procurar letras ou palavras (/)
Depois de executar o comando less mostrado acima, digite

`/termoProcurado`

- utilize `n` para navegar até a próxima ocorrência
- utilize `N` para navegar até a ocorrência anterior

## Contar palavras - Word Count (wd)
`wc <NOME_DO_ARQ.EXTENSAO>`

o resultado mostrado será:
quantidade de linhas | quantidade de palavras | tamanho do arquivo | nome do arquivo

## Procurar e exibir todas as ocorrências (grep)
`grep <TERMO_PROCURADO> <NOME_DO_ARQUIVO.EXTENSÃO>`

## Procurar e exibir todas as ocorrências ignorando case sensitive (grep -i)
`grep -i <TERMO_PROCURADO> <NOME_DO_ARQUIVO.EXTENSÃO>`

### Combinação de grep e wc
`grep <TERMO_PROCURADO> <NOME_DO_ARQUIVO.EXTENSÃO> | wc`

## Mostrar começo do arquivo de texto (head)
`head <NOME_DO_ARQ.EXTENSAO>`

ou

`1G` (se usando o comando less)

## Mostrar final do arquivo de texto (tail)
`tail <NOME_DO_ARQ.EXTENSAO>`

ou

`lG` (se usando o comando less)

## Contar palavras - Word Count (wd)
`wc <NOME_DO_ARQ.EXTENSAO>`

o resultado mostrado será:
quantidade de linhas | quantidade de palavras | tamanho do arquivo | nome do arquivo

---
# Alias
Ver [Git alias](https://github.com/layshidani/my-learning-notes/blob/master/git-github/git-alias.md)

## Listar alias linux
`alias`

## Criar alias linux
este comando cria o alias apenas para a seção atual:

`alias seu-alias='comando original`

***IMPORTANTE: fechar e abrir de novo o terminal para funcionar.***

Para criá-los definitivamente:

> Para criá-los, é preciso modificar o arquivo .bashrc que se encontra em /home/NomeDoUsuário/.bashrc (se o arquivo não existir, crie-o) e adicionar cada apelido no final do arquivo. --[fonte](https://www.linuxdescomplicado.com.br/2015/06/criar-comandos-usando-alias.html)

ex:
`alias desligar='sudo shutdown -h now'`

## Deletar alias linux e github
`unalias seu-alias`

---

## Abrir html pelo navegador (Criar Servidor HTTP)
Navegue até a pasta onde está seu html e rode o comando abaixo na linha de comando:

```
python -m SimpleHTTPServer 8000
```

## Verificar se o sistema é 32 ou 64 bits

```bash
uname -m
```
