# Ambiente de desenvolvimento Angular

```$
sudo npm i -g @angular/cli
```

```$
sudo npm i -g typescript
```


ng new my-dream-app
cd my-dream-app
ng serve

## Componentes
É possível criar os componentes manualmente ou de forma mais simplificada, utilizando o `angular-cli`.

Os arquivos de componentes estão em:

**src >>> app**

### Criar componente utilizando o angular cli
Basta digitar no terminal:

```$
ng g c nome-do-componente
```

onde:
* g: gerar
* c: component

Esse comando irá criar a pasta do component e os arquivos.
Neste caso, ele também irá criar o arquivo html onde você deverá editar o conteúdo do seu component. É uma forma diferente da demonstrada no modo manual com template string, ambas as formas podem ser utizadas (template string, html separado).

### Criar o primeiro componente manualmente
**> Arquivos**

**!Convenção: Criar nome das pastas e dos arquivos de componentes em Kebab Case (com letra minúscula e palavras separadas por "-")**
1. Cria a pasta nome
2. Cria o arquivo nome-component.ts


```ts
import { Component } from '@angular/core';

@Component({
  // nome da tag
  selector: 'meu-primeiro-component',
  // conteúdo da tag
  template: `
    <p>Meu primeiro component com Angular 2!</p>
  `
})

export class MeuPrimeiroComponent { }
```
**!Convenção: classes são escritas em Pascal Case (todas as primeiras letras em maiúsculo)**

### Usar o component manualmente
Vá até o arquivo *.module.ts*. Por exemplo:

**app.module.ts**

1. Importe a classe:
2. Acrescente o component nas **declarations**.

Exemplo:

```ts
import { MeuPrimeiroComponent } from './meu-primeiro/meu-primeiro.component';

@NgModule({
  declarations: [
    AppComponent,
    MeuPrimeiroComponent
  ],
```

Vá até o arquivo html que deseja adicionar. Por exemplo:

**app.component.html**

adicione o componente onde desejar:

```html
<meu-primeiro-component></meu-primeiro-component>
```

