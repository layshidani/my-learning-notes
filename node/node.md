# Node (Linux)


## Verificar se está instalado e versão
```
node -v
```

Deverá retornar a versão.

## Instalar Node


## Atualizar

Utilizar o gereciador [n](https://www.npmjs.com/package/n)

Para instalar:
```
npm i -g n
```

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
