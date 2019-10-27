# Ignorar determinados arquivos na hora de commitar (ignore)

Criamos um arquivo com extensão *gitignore*, onde listamos todos os arquivos e pastas que não deverão ser lançados no repositório, ou seja, que estão na pasta mas deverão ser ignorados pelo git.

Como, por exemplo, arquivos de sistema, anotações, etc.

O git irá ignorar as alterações feitas nos arquivos listados, assim como, quando você fizer **push**, estes arquivos e pastas não serão enviados para o repositório remoto.

Recomenda-se criar apenas um único gitignore em trabalhos em grupo e commitá-lo, assim todos terão acesso aos nomes dos arquivos ignorados e evita de que um mesmo arquivo seja ignorado mais vezes por outras pessoas.

Na web você consegue encontrar vários templates já prontos. Um site interessantes para gerar o gitignore é o [gitignore.io](https://www.gitignore.io/).

Passos:

1.  criar um arquivo com extensão (.gitignore) na pasta onde estão os arquivos de commit
2.  num editor de texto listar no arquivo .gitignore o nome dos arquivos que deverão ser ignorados. Todos esses arquivos depois de terem o nome salvo no .gitignore não aparecerão mais em git status. exemplo:
    `fonte.txt` e
    `img21.png`
3.  salvar e fazer o commit deste arquivo .gitignore como outro arquivo qualquer

um exemplo de arquivo **.gitignore**:

```

# Created by https://www.gitignore.io/api/linux,windows,angular
# Edit at https://www.gitignore.io/?templates=linux,windows,angular

### Angular ###
## Angular ##
# compiled output
dist/
tmp/
app/**/*.js
app/**/*.js.map

# dependencies
node_modules/
bower_components/

# IDEs and editors
.idea/

# misc
.sass-cache/
connect.lock/
coverage/
libpeerconnection.log/
npm-debug.log
testem.log
typings/

# e2e
e2e/*.js
e2e/*.map

#System Files
.DS_Store/

### Linux ###
*~

# temporary files which can be created if a process still has a handle open of a deleted file
.fuse_hidden*

# KDE directory preferences
.directory

# Linux trash folder which might appear on any partition or disk
.Trash-*

# .nfs files are created when an open file is removed but is still being accessed
.nfs*

### Windows ###
# Windows thumbnail cache files
Thumbs.db
Thumbs.db:encryptable
ehthumbs.db
ehthumbs_vista.db

# Dump file
*.stackdump

# Folder config file
[Dd]esktop.ini

# Recycle Bin used on file shares
$RECYCLE.BIN/

# Windows Installer files
*.cab
*.msi
*.msix
*.msm
*.msp

# Windows shortcuts
*.lnk

# End of https://www.gitignore.io/api/linux,windows,angular
```

## ATALHO gitignore: todos os arquivos de mesma extensão

Vamos supor que queremos que o git ignore todos os arquivos em formato txt que estão na pasta. Basta salvar no arquivo .gitignore \* + extensão do tipo de arquivo a ser ignorado (no editor de texto):
`*.txt`

## Adicionar um arquivo que está listado no .gitignore (force)

Se por algum motivo especial, você quiser adicionar, commitar, etc um arquivo que está listado no arquivo gitignore, podemos utilizar o comando `force` ou sua abreviação `-f`:

```
git add -f nome_do_arquivo.extensão
```
