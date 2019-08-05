# Exemplo arquivo de configuração do Firebase

Criar o arquivo **firebase-config.js**

```js
import firebase from 'firebase/app';
import 'firebase/auth';
import 'firebase/firestore';

// key do projeto gerada pelo Firebase
const key = "sdkjsdjfklsdjfkjdsfREOKDFKSKDLKSDLsdjfksj";

// copiar dados do projeto no Firebase
// configurações do projeto >>> Geral >>> Seus aplicativos >>> Firebase SDK snippet >>> Configuração >>> só copiar o snippet de configuraçao como o exemplo abaixo:

const firebaseConfig = {
  apiKey: key,
  authDomain: "project-name-f8f37.firebaseapp.com",
  databaseURL: "https://project-name-f8f37.firebaseio.com",
  projectId: "project-name-f8f37",
  storageBucket: "project-name-f8f37.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:1234567890123db4"
};

firebase.initializeApp(firebaseConfig);

export default firebase;
```