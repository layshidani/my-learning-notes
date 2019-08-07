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
ver como [criar componentes]()

O próprio angular-cli irá acrescentar os imports necessários dos componentes no arquivo de módulo, porém é necessário acrescentar o trecho de **export** para indicar o que deve ser efetivamente exportado e exibido.

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
