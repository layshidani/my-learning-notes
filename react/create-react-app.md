[Reactjs](https://pt-br.reactjs.org/docs/create-a-new-react-app.html)

* No local onde deseja criar

```$
npm init react-app nome-da-app
```

ou

```$
npm install -g create-react-app
```

```$
npm start
```

## Instalações

```$
// eslint
npm i --save-dev eslint

// Firebase
npm i --save firebase

// Firebase Tools
npm install -g firebase-tools

// instalar rotas
npm i --save react-router-dom

// fontawesome
npm i --save @fortawesome/fontawesome-svg-core
npm i --save @fortawesome/free-solid-svg-icons
npm i --save @fortawesome/react-fontawesome
```

---
### Firebase no arquivo

```js
import firebase from 'firebase';

const firebaseConfig = {
  ...
}

firebase.initializeApp(firebaseConfig);

export default 

import firebase from './firebaseConfig';

// Firestore
const database = firebase.firestore();
```
---

```js
handleClick = () => {
  const object = {
    ...
  }
  database.collection('laboratoria').add(object)
}
```
---
### Adicionando React Dom e fontawesome no arquivo

```js
import ReactDOM from 'react-dom'
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome'
import { faCoffee } from '@fortawesome/free-solid-svg-icons'
 
const element = <FontAwesomeIcon icon={faCoffee} />
```
---

## Deploy no Firebase
```$
firebase deploy --only functions
```
---

```
git commit -am "jdsjkd"
```

```
git tag v1.0.0
```
---

# Deploy

```
npm run build
```

irá criar a pasta build.

mude a configuração no arquivo `firebase.json` para que ele abra o **hosting** na pasta **build** ao invés de public:


```
{
  "firestore": {
    "rules": "firestore.rules",
    "indexes": "firestore.indexes.json"
  },
  "functions": {
    "predeploy": [
      "npm --prefix \"$RESOURCE_DIR\" run lint"
    ],
    "source": "functions"
  },
  "hosting": {
    "public": "build", // mudar aqui 
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ],
    "rewrites": [
      {
        "source": "**",
        "destination": "/index.html"
      }
    ]
  }
}
```

```
firebase deploy --only hosting
```
