# npm
Node Package Manager

**Configurações**

## Instalar npm
```$
sudo apt install npm
```

## Verificar versão do npm
```$
npm --version
```

## Atualizar npm
```$
npm install -g npm
```

### Atualizar para versão específica
```$
npm install -g npm@<numero da versão>
```

---
**Trabalhando com o npm**

## iniciar npm no projeto
!Não esquecer de criar um arquivo *.gitignore* e adicionar a pasta **node_modules** nele. Pois nessa pasta estarão todos os pacotes (para não subir para o GitHub, por exemplo).

```$
npm init
```$

responder todas as perguntas do terminal para que o npm crie o arquivo package.json com todas essas informações sobre o projeto.

*caso queira pular essas perguntas e criar um arquivo package.json e configurar depois, inclua `-y` ao rodar o comando acima:*
```$
npm init -y
```

*é possível editar ou inserir dados no próprio arquivo package.json manualmente depois a qualquer momento.*

## Instalar pacotes com npm
Você poderá optar por instalar globalmente e local, ou somente local:

* global: `npm i -g nome-do-pacote`
* local: `npm i nome-do-pacote --save-dev  // ou --save`

  Onde:
  * `--save-dev`: é usado para salvar o pacote para fins de desenvolvimento. Exemplo: testes unitários,minificação
  * `--save`: é usado para salvar o pacote necessário para o aplicativo ser executado.

***No caso de incluir `--save-dev` ou `--save`, as regras dos pacotes já serão automaticamente adicionadas no arquivo package.json em devDependencies (--save-dev) e Dependencies (--save).***

*salvar global (pc)/local(no próprio projeto)*

### Instalar versão específica de um pacote
```$
npm i <package-name>@<version>
```

*Se necessário acrescentar `--save` ou `--save-dev`.

## Instalar pacote via repo do GitHub
```$
npm install <end>
```

ex:

```$
npm i git://github.com/user-name/package-name.git#v0.1.0
```


## Desinstalar pacote
* Local:
  ```$
  npm uninstall <package-name>
  ```
* Global:
  ```$
  npm uninstall -g <package-name>
  ```

## Verificar se pacote está instalado ou versão instalada
```$
npm -v nome-do-pacote
```

## Verificar pacotes desatualizados
```$
npm outdated
```

## Atualizar todos os pacotes
Todos os listados no *package.json*:
```$
npm update
```

ou utilizados no --save e --save-dev:

```$
npm update --save/--save-dev
```

## Atualizar todos os pacotes para versão mais recente
***!arriscado***

```$
npm update --save/--save-dev -f
```

## Atualizar pacote específico
```$
npm update <nome do pacote>
```

## Remover todos os pacotes não utilizados
```$
npm prune
```

ou

### Remover todos os pacotes não utilizados de devDependencies
```$
npm prune --production
```

## Remover pacotes duplicados em *node-modules*
```$
npm dedupe
```

## Mostrar pacotes em cachê
```$
npm cache ls
```

## Limpar o cachê do npm
```$
sudo npm cache clean -f
```

## 'Cravar' versões de produção
```$
npm shrinkwrap --dev
```

ou manualmente, no arquivo *package.json*:

**retirar o símbolo ^ das versões, assim a versão não mudará.**

## Projeto já existente
Quando baixar projeto já existente será necessário instalar os pacotes.

rodar a instalação de todos os pacotes:
```$
npm i
```

ou

Instalar somente os pacotes de **Dependencies** e não os de **DevDependencies**:
```$
npm install --only=production
```
