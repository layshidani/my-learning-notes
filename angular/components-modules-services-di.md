# Componentes

É possível criar os componentes manualmente ou de forma mais simplificada, utilizando o `angular-cli`.

Os arquivos de componentes estão em:

**src >>> app**

## Criar componente utilizando o angular cli

Basta digitar no terminal:

```$
ng g c nome-do-componente
```

ou se já existir o diretório:

```$
ng g c diretorio/nome-do-componente
```

onde:

- g: gerar
- c: component

Esse comando irá criar a pasta do component e os arquivos.
Neste caso, ele também irá criar o arquivo html onde você deverá editar o conteúdo do seu component. É uma forma diferente da demonstrada no modo manual com template string, ambas as formas podem ser utizadas (template string, html separado).

No arquivo **nome-do-componente.component.ts**, gerado na criação do componente, haverá o seletor que você poderá usar no HTML, por exemplo:

No arquivo **btn.component.ts**:

```ts
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-btn", // este seletor
  templateUrl: "./btn.component.html",
  styleUrls: ["./btn.component.sass"]
})
export class BtnComponent implements OnInit {
  constructor() {}

  ngOnInit() {}
}
```

O seletor **app-btn**, poderá ser usado no html como:

```html
<app-btn></app-btn>
```

**!Nota: se o component estiver importado no app.module.ts que é o module raíz do projeto, você também poderá utilizar o component dentro dos arquivos html de outros components.**

## Criar o primeiro componente manualmente

**> Arquivos**

**!Convenção: Criar nome das pastas e dos arquivos de componentes em Kebab Case (com letra minúscula e palavras separadas por "-")**

1. Cria a pasta nome
2. Cria o arquivo nome-component.ts

```ts
import { Component } from "@angular/core";

@Component({
  // nome da tag
  selector: "meu-primeiro-component",
  // conteúdo da tag
  template: `
    <p>Meu primeiro component com Angular 2!</p>
  `
})
export class MeuPrimeiroComponent {}
```

**!Convenção: classes são escritas em Pascal Case (todas as primeiras letras em maiúsculo)**

## Usar o component manualmente

Vá até o arquivo _.module.ts_.

Por exemplo, para usar no módulo raíz:
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
# Templates

**html = template**

!Boa prática: no Component -> Utilizar template string somente se tiver até 3 linhas. Mais do que isso é recomendado um arquivo HTML a parte.

## Interpolação e Diretivas

### Interpolação

Podemos usar a interpolação para atribuir valores em um componente.

```ts
{{ x }}
```

Por exemplo:

no arquivo **exemplo.component.ts**

```ts
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-exemplo",
  templateUrl: "./exemplo.component.html",
  styleUrls: ["./exemplo.component.sass"]
})
export class ExemploComponent implements OnInit {
  myName: string;

  constructor() {
    this.myName = "Lays";
  }

  ngOnInit() {}
}
```

Depois de ter feito todos as configurações necessárias no arquivo de **modules**.

Podemos utilizar a interpolação no arquivo **exemplo.component.html**

```html
   <h2>Olá, meu nome é {{ myName }}!</h2>
```

Inserindo o componente para exibição, o resultado será:

**Olá, meu nome é Lays**

### Diretivas

Exemplo:
**no arquivo nomes.component.ts:**
```ts
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-numbers',
  templateUrl: './numbers.component.html',
  styleUrls: ['./numbers.component.sass']
})
export class NumbersComponent implements OnInit {
  numbers: string[] = ['1', '2', '3'];

  constructor() { }

  ngOnInit() {
  }

}
```

**no arquivo nomes.component.html:**
```html
  <ul>
    <li *ngFor="let num of nums"> {{ num }}</li>
  </ul>
```

O resultado será:

* 1
* 2
* 3


---
# Modules
O angular-cli cria automaticamente um arquivo **app.modules.ts**:

(esse é o módulo raiz do projeto)

```ts
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppRoutingModule } from './app-routing.module';

// importar components
// boa prática: agrupar os imports de components após pular uma linha dos imports iniciais
import { AppComponent } from './app.component';
import { MeuPrimeiroComponent } from './meu-primeiro/meu-primeiro.component';
import { Componente2Component } from './componente2/componente2.component';

// declaratios, imports são metadados
@NgModule({
  // declarations: componentes, diretivas e pipes
  declarations: [
    AppComponent,
    MeuPrimeiroComponent,
    Componente2Component
  ],
  // import: outros módulos para serem utilizados dentro deste módulo ou de algum componente que pertence a este módulo
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  // providers: serviçoes disponíveis para os componentes, e nesse caso, na aplicação global, já que AppModule é global:
  providers: [],
  // instanciado no carregamento da SPA:
  bootstrap: [AppComponent]
})

export class AppModule { }
```

## Criar módulo no terminal (angular-cli)
(esse é um módulo de funcionalidade do projeto)

Na pasta do projeto, digite no terminal:

```$
ng g m nome-do-modulo
```

Ex:
```$
ng g m my-module
```

irá criar um diretório com o nome do módulo (ex: my-module), com o arquivo **.ts** correspondente ao módulo criado:

```ts
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';

@NgModule({
  declarations: [],
  imports: [
    CommonModule
  ]
})
export class MyModuleModule { }
```

## Adicionar componentes ao módulo
ver como [criar componentes](https://github.com/layshidani/my-learning-notes/blob/master/angular/components.md)

Se você tiver a extensão [Auto Import](https://marketplace.visualstudio.com/items?itemName=steoates.autoimport), ela irá acrescentar os imports necessários dos componentes no arquivo de módulo, porém é necessário acrescentar o trecho de **export** para indicar o que deve ser efetivamente exportado e exibido.

```ts
,
  exports: [
    NomeDoComponent
  ]
```

Assim, nosso arquivo de exemplo fica assim:

```ts
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';

import { BtnComponent } from './btn.component';

@NgModule({
  declarations: [BtnComponent],
  imports: [
    CommonModule
  ],
  exports: [
    BtnComponent
  ]
})
export class BtnModule { }
```

Depois disso será necessário importar o módulo de funcionalidade dentro do módulo raíz (app.module.ts).

Exemplo:
no arquivo **app.module.ts**:

Importar a classe:
```ts
import { BtnModule } from './btn/btn.module'
```

Em seguida, importar o módulo no NgModule:

```ts
@NgModule({
  declarations: [
    AppComponent,
    MeuPrimeiroComponent,
    Componente2Component
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    BtnModule // importar o módulo aqui
  ],
  providers: [],
  bootstrap: [AppComponent]
})
```

Também é possível fazer uso de componentes privados, não incluindo-os no imports.

**!Nota: se o component estiver importado no app.module.ts que é o module raíz do projeto, você também poderá utilizar o component dentro dos arquivos html de outros components.**

---

# Services e Injeção de Dependência

