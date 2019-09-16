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
