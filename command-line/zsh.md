# ZSH (Linux Mint)
**Zsh: interpretador de comandos (Shell)**
## Instalar ZSH
```$
sudo apt install zsh
```

## Instalar Oh My Zsh e tornar o shell padrão
```$
curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh; zsh
```
deverá aparecer escrito **Shell Changed**, caso não apareça, rodar o comando:

```$
sudo usermod --shell $(which zsh) <seu_usuario>
```

## Habilitar temas e plugins
*Reabrir terminal para que as mudanças tenham efeito*

Quanto quiser modificar o tema ou adicionar plugins, deverá incluí-los no arquivo **.zshrc**.
Você pode ir até a pasta raiz, habilitar a visualização de arquivos ocultos e editar o arquivo em seu editor ou pelo terminal:

```$
cd ~
```

Editar no próprio terminal

```$
vi .zshrc
```

ou abrir no seu editor de preferência, no VSCode, por exemplo:

```$
code .zshrc
```

### Plugins
Procure no arquivo **.zshrc** a parte de plugins e add:

Exemplo:

```
plugins=(
  git
  dnf
  zsh-syntax-highlighting
  zsh-autosuggestions
  )
```

Alguns plugins legais:
* [AutoSuggestions](https://github.com/zsh-users/zsh-autosuggestions)

  Rode no terminal:
  ```$
  git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
  ```

  Depois,adicione na lista de plugins do arquivo **.zshrc**.


### Temas
Lista de temas:
* [Oficial](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes)
* [Completa](https://zshthem.es/all/)

Procure no arquivo **.zshrc** a parte de tema (ZSH_THEME) e add o nome do tema:

Exemplo:
```
ZSH_THEME="fino"
```
