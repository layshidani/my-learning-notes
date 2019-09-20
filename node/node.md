# Node (Linux)


## Verificar se está instalado e versão
```
node -v
```

Deverá retornar a versão.

## Instalar Node

```$
sudo apt install nodejs
```

## Instalar npm
```$
sudo apt install npm
```

## Atualizar

Utilizar o gereciador [n](https://www.npmjs.com/package/n)

Limpar o cachê do npm:

```$
sudo npm cache clean -f
```

Baixar lib **n** que gerencia NodeJS:
```$
sudo npm install -g n
```

Instalar versão estável:
```$
sudo n stable
```

## Remover node
listar versões instaladas:
```$
n
```

versão específica:
```$
n rm <version ...>
```

todas as versões menos a versão atual:
```$
n prune
```

---

<!-- ### Windows problema node não roda no git bash
Precisamos adicionar o caminho para a variável de ambiene.

Pelo git bash:

Abra o arquivo **~\.bash_profile** no vscode ou outro editor de preferência:

```$
code ~\.bash_profile
```

Adicione a linha abaixo no arquivo:

`PATH="/usr/local/share/npm/bin:/usr/local/bin:/usr/local/sbin:~/bin:$PATH"` -->

### Windows problema node não roda no shell windows
Precisamos adicionar o caminho para a variável de ambiene.

```
where node
```

depois

```
where npm
```

