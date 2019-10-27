# Iniciar Git em um repositório

## Repositório local já existente

1. Navegue até a pasta do repositório

  Digite o comando:

  ```
  git init
  ```
2.  criar um repositório no repositório remoto e copiar o endereço SSH ou HTTP do repositório
3.  no terminal digitar o comando abaixo ((este nome origin pode ser o nome que você quiser, mas é mais comumente utilizado o origin):
    ```
    git remote add origin endereço
    ```
4.  adicione seus arquivos com o comando `git add`.
5.  commite os arquivos `git commit -m 'msg de commit'`.
6.  enviar arquivos para o repositório remoto:
    ```
    git push origin master
    ```
7.  da primeira vez que conectar ao repositório remoto (seu primeiro repositório nesta máquina) irá pedir usuário e senha do repositório remoto, após informar, ele automaticamente irá fazer o push dos seus arquivos.

## Começar com o repositório remoto
1. criar um repositório no repositório remoto e copiar o endereço SSH ou HTTP do repositório
2. navegue com terminal até o local onde deseja salvar o repositório na sua máquina
3. clone o repositório remoto com `git clone <endereco>`

