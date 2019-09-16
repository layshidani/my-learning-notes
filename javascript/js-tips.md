# JavaScript Tips

## Parâmetro com valor default

Exemplo:

```js
const sum = (arg1, arg2 = 5) => {
  const result = arg1 + arg2;
  return 'O resultado é: ' + result;
}

sum(1)
// O resultado é: 6
// como só um argumento é passado, o valor default do segundo argumento é utilizado

sum(1, 2)
// O resultado é: 3
// os dois argumentos foram passados, então serão utilizados os valores passados
```

## Destructuring

- arrays:
  ```js
  // dado o array:
  const arr = [1, 2, 3, 4, 5];

  // aqui estamos atribuindo a variável um ao primeiro item do array, e dois ao segundo item, como se estivéssemos fazendo:
  // const um = arr[0];
  // const dois = arr[1];
  const [um, dois] = arr;

  // resultado:
  console.log(um);
  // 1

  console.log(dois);
  // 2
  ```
- objetos:
  ```js

  ```
