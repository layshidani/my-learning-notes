# Angular v2
> Angular é uma plataforma de aplicações web de código-fonte aberto e front-end baseado em TypeScript liderado pela Equipe Angular do Google e por uma comunidade de indivíduos e corporações. Angular é uma reescrita completa do AngularJS, feito pela mesma equipe que o construiu. [--Wiki](https://g.co/kgs/guUR7X)

## Table of Contents
- [Preparando o ambiente de desenvolvimento com Angular cli](#preparando-o-ambiente-de-desenvolvimento-com-angular-cli)
  * [Iniciar um novo projeto com o Angular cli](#iniciar-um-novo-projeto-com-o-angular-cli)
  * [Rodando a aplicação](#rodando-a-aplicação)
- [Componentes](#componentes)
  * [Criar componente utilizando o angular cli](#criar-componente-utilizando-o-angular-cli)
  * [Criar o primeiro componente manualmente](#criar-o-primeiro-componente-manualmente)
  * [Usar o component manualmente](#usar-o-component-manualmente)
- [Templates](#templates)
  * [Interpolação e Diretivas](#interpolação-e-diretivas)
    * [Interpolação](#interpolação)
    * [Diretivas](#diretivas)
- [Modules](#modules)
  * [Criar módulo](#criar-módulo)
  * [Adicionar componentes ao módulo](#adicionar-componentes-ao-módulo)
- [Services e Injeção de Dependência](#services-e-injeção-de-dependência)
---

# Preparando o ambiente de desenvolvimento com Angular cli

[Angular cli reference](https://angular.io/cli)

Pre-requisitos:
* NodeJS instalado


```$
sudo npm i -g @angular/cli
```

```$
sudo npm i -g typescript
```

## Iniciar um novo projeto com o Angular cli
```$
ng new app-name
```

Entre no diretório do projeto para começar a trabalhar nele:
```$
cd app-name
```

## Rodando a aplicação
O comando abaixo irá fazer o build da aplicação e rodar no [http://localhost:4200/](http://localhost:4200/), você poderá acompanhar pelo browser o efeito das alterações do projeto.

```$
ng serve
```

ou abreviado:

```$
ng s
```


---
# Componentes
> Angular 2 é orientado a componentes, isso significa que você vai escrever diversos componentes minúsculos que juntos constituirão uma aplicação inteira. Um Component é a combinação de um template HTML com uma classe que controla parte da tela. [--Matera](http://www.matera.com/blog/post/comecando-com-angular-2)


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
> Em Angular, um módulo é um mecanismo para agrupar componentes, diretivas, canais e serviços relacionados, de forma que possam ser combinados com outros módulos para criar uma aplicação. Uma aplicação Angular pode ser vista como um quebra-cabeça onde cada peça (ou cada módulo) é necessária para poder ver a imagem completa.
> Outra analogia para entender os módulos angulares são as classes. Em uma classe, podemos definir **métodos públicos ou privados**. Os métodos públicos são a API que outras partes do nosso código podem usar para interagir com ela, enquanto os métodos privados são detalhes de implementação ocultos. Da mesma forma, um módulo pode exportar ou ocultar componentes, diretivas, tubulações e serviços. Os elementos exportados devem ser usados ​​por outros módulos, enquanto os que não são exportados (ocultos) são usados ​​apenas dentro do próprio módulo e não podem ser acessados ​​diretamente por outros módulos de nosso aplicativo. [--Angular 2 training book](https://angular-2-training-book.rangle.io/modules/introduction)


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

## Criar módulo
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
> O serviço é simplesmente uma função javascript, juntamente com suas propriedades e métodos associados, que podem ser incluídos (via injeção de dependência) nos componentes do Angular 2. Eles permitem desenvolver código para tarefas específicas que podem ser usadas nesses componentes. [--Coursetro](https://coursetro.com/posts/code/20/Angular-2-Services-Tutorial---Understanding-&-Creating-Them)
> Angular distingue componentes de serviços para aumentar a modularidade e a reutilização. Ao separar a funcionalidade relacionada à visualização de um componente de outros tipos de processamento, você pode tornar suas classes de componentes simples e eficientes. [--Angular.io](https://angular.io/guide/architecture-services)


Para criar na raiz do projeto (dir app):

```$
ng g s service-name
```

Para criar em um diretório de componente já existente:

```$
ng g s dir-name/service-name
```

Este comando irá criar dois arquivos:
* service-name.service.spec.ts
* service-name.service.ts

!Boas práticas fazer o uso de services para injetar dados, ao invés de fazer direto por diretiva.

Utilizando o mesmo exemplo das diretivas:

Seguimos 3 passos:

1. no arquivo **numbers.service.ts**:
```ts
import { Injectable } from '@angular/core';

// @injectable é um decorator
@Injectable({
  providedIn: 'root'
})
export class NumbersService {

  constructor() { }

  getNumbers() {
    // adiciona um return com os valores a serem injetados:
    return ['1', '2', '3'];
  }
}
```

2. no arquivo **numbers.component.ts**:
```ts
import { Component, OnInit } from '@angular/core';

// importar a classe NumbersService
import { NumbersService } from './numbers.service';

@Component({
  selector: 'app-numbers',
  templateUrl: './numbers.component.html',
  styleUrls: ['./numbers.component.sass']
})
export class NumbersComponent implements OnInit {
  // retirar o array daqui e inserir no arquivo de service:
  // numbers: string[] = ['1', '2', '3'];
  numbers: string[];

  // Instanciar via construtor (pode ser private ou public)
  constructor(private numbersService: NumbersService) {
    this.numbers = this.numbersService.getNumbers();
  }

  ngOnInit() {
  }

}
```

3. no arquivo **numbers.component.html**:
```html
  <ul>
    <li *ngFor="let num of nums"> {{ num }}</li>
  </ul>
```

Por fim,
O resultado será:

* 1
* 2
* 3
