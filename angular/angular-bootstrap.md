# Libs no projeto

## Adicionar Bootstrap ao projeto

- [ngx Bootstrap](https://github.com/valor-software/ngx-bootstrap/blob/development/docs/getting-started/ng-cli.md)
- [Bootstrap](https://getbootstrap.com/)

Para adicionar o Bootstrap ao projeto, você pode optar por inserir o link CDN no arquivo principal (**app.component.html**) ou utilizar o **[ngx bootstrap](https://github.com/valor-software/ngx-bootstrap/blob/development/docs/getting-started/ng-cli.md)**:

**Add ngx-bootstrap em um projeto que utiliza angular-cli**

- Instalar o ngx-bootstrap (se não tiver instalado):

```bash
npm install ngx-bootstrap bootstrap --save
```

- Adicionar o bootstrap ao projeto

```bash
ng add ngx-bootstrap
```

ou manualmente, após instalado:

- No arquivo **app.module.ts** importar o módulo que será utilizado.

  Exemplo:

```ts
// importa Alert do ngx-bootstrap
import { AlertModule } from 'ngx-bootstrap';

// ...

@NgModule({
   //...
   // em imports, add o AlertModule, juntamente com os outros imports
   imports: [AlertModule.forRoot(), ... ],
   // ...
})

```

- No arquivo **angular.json**, adicionar aos estilos e o scripts:

```json
// ...
"styles": [
  "./node_modules/bootstrap/dist/css/bootstrap.min.css",
  "styles.css",
      ],
// ...


```


- Adicionar a tag no html. Exemplo:

```html
<alert type="success"
  >Sucesso! Você está aprendendo a utilizar Bootstrap no angular!</alert
>
```

---

## Adicionar Materialize ao projeto

- [Materialize](https://materializecss.com/)
- [Angular2 Materialize](https://www.npmjs.com/package/angular2-materialize)

Veja instruções completas de como instalar e configurar neste [link](https://www.npmjs.com/package/angular2-materialize#installing--configuring-angular2-materialize-in-projects-created-with-the-angular-cli).

```bash
# parte css
npm install materialize-css --save

# parte abstração jquery
npm install angular2-materialize --save
```

```bash
npm install jquery@^2.2.4 --save
npm install hammerjs --save
```

<!-- ```bash
npm install --save ngx-materialize
``` -->

No final, confira se tudo foi adicionado corretamente aos arquivos:
**angular.json**:
```json
// ...
"styles": [
  "src/styles.scss",
// Add this:
 "node_modules/materialize-css/dist/css/materialize.min.css"
],
"scripts": [
// Add this:
 "node_modules/jquery/dist/jquery.min.js",
 "../node_modules/hammerjs/hammer.js",
 "node_modules/materialize-css/dist/js/materialize.min.js"
],
```

no arquivo **tsconfig.app.json**:
```json
// ...
"types": [
  // add :
  "jquery",
  "materialize-css"
    ]
```

em **app.module.ts**:
```ts
import { MaterializeModule } from 'angular2-materialize';
```

em **index.html**:
```html
<header>
  // ...
  <link href="http://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
</header>
```

