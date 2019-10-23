# Paradigmas

## Programação orientada a objetos

- reutilização de código
- manutenção
- entendimento do código -> representação mais próxima de um objeto no mundo real (tem características e pode executar ações)
- *se comparada a programação estruturada, onde o código é executado de forma sequencial, a execução do código na OOP é um pouco mais lenta (hoje facilmente solucionado pela qualidade dos hardwares)*.

### 4 Conceitos chave

- **abstração**:
- identidade única
- propriedades (características) - exemplo: `nome, idade`
- métodos (ações) - exemplo: `falar()`
- **encapsulamento**: segurança -> evita o acesso direto às propriedades do objeto
- **herança**: reuso do código
- herança direta, de pai para filho. Algumas linguagens permitem mais de uma herança direta.
- herança indireta (de avó para neto, etc)
- **polimorfismo**: modificar um método herdado

### Definições

- **classes**: agrupa um conjunto de objetos que possuem os mesmos métodos, propriedades, relacionamentos, etc.

> Uma classe é uma forma de definir um tipo de dado em uma **linguagem orientada a objeto**. Ela é formada por dados e comportamentos.
> Para definir os dados são utilizados os atributos, e para definir o comportamento são utilizados métodos. Depois que uma classe é definida podem ser criados diferentes objetos que utilizam a classe.
> [DevMedia]([https://www.devmedia.com.br/principais-conceitos-da-programacao-orientada-a-objetos/32285](https://www.devmedia.com.br/principais-conceitos-da-programacao-orientada-a-objetos/32285))

- **objetos**: instâncias de classes
> Em ciência da computação, **objeto** é uma referência a um local da memória que possui um valor. Um objeto pode ser uma variável, função, ou estrutura de dados.
Em programação orientada a objetos, a palavra _objeto_ refere-se a uma instância de uma classe.

> Em programação orientada a objetos, um objeto passa a existir a partir de um "molde" (classe); a classe define o comportamento do objeto, usando atributos, propriedades e métodos.
> [Wiki]([https://pt.m.wikipedia.org/wiki/Objeto_(ci%C3%AAncia_da_computa%C3%A7%C3%A3o](https://pt.m.wikipedia.org/wiki/Objeto_(ci%C3%AAncia_da_computa%C3%A7%C3%A3o)))

- **escopo de uma variável**:
- global -> toda a classe
- local -> método onde ela está contida (ou bloco dentro do método)
- **visibilidade**: define a forma como métodos e atributos podem ser acessados:
- `public`: fora da classe (diretamente de qualquer classe)
- `private`: somente dentro da classe
- `protected`: dentro da própria classe e de classes filhas.
- **associação de classes**: associar duas classes de tal modo que seus objetos podem se comunicar.
- **classe agregada**: uma classe contida dentro de outra

## Funtional Programming (FP)
> É um paradigma de programação que descreve uma computação como uma expressão a ser avaliada.
> [eusoudev]([https://eusoudev.com.br/programacao-funcional](https://eusoudev.com.br/programacao-funcional)/)

> Em um programa imperativo, o desenvolvedor indica como o mesmo deve se comportar enquanto está em execução, já em um programa funcional, você determina um resultado a ser obtido, e a computação será feita de acordo com a melhor forma para obter tal resultado, o que vai acarretar em uma melhor performance.
> [Pedro Henrique, [medium.com](http://medium.com)]([https://medium.com/@phinfonet/programa%C3%A7%C3%A3o-funcional-o-que-diabos-%C3%A9-isso-da9f230b9be2](https://medium.com/@phinfonet/programa%C3%A7%C3%A3o-funcional-o-que-diabos-%C3%A9-isso-da9f230b9be2))

> No paradigma funcional eu não dito ao meu código o que ele deve fazer, quando e como. Não irei desenvolvê-lo passo a passo. Eu penso meu código como uma sequência de funções e/ou passos, as quais de maneira composta irão resolver meu problema.

> De maneira simples: código funcional é um código composto de múltiplas funções que se compõem para resolver um problema. Pense da seguinte forma: eu tenho um dado de entrada e preciso transformá-lo em um dado de saída. Usando PF eu vou abstrair as lógicas de transformações do meu código em funções, e usá-las no momento oportuno para transformar este meu dado.
> [Training center]([https://medium.com/trainingcenter/programa%C3%A7%C3%A3o-funcional-para-iniciantes-9e2beddb5b43](https://medium.com/trainingcenter/programa%C3%A7%C3%A3o-funcional-para-iniciantes-9e2beddb5b43))

- Declarativa
- Stateless
- Imutabilidade: data never changes (const, map)
- princípio da responsabilidade única: cada função deve exercer uma única tarefa
- no side effects
- **composition**: reaproveitamento de código, junção de funções mais básicas para executar tarefas mais complexas
- **curry**: ação de transformar uma função que receba múltiplos argumentos em uma cadeia de funções onde cada função receba somente um argumento

- **first class functions**: representam um valor, assim sendo, podem ser utilizadas como argumentos e recebidas como resultado
- **high order functions**: funções que aceitam funções como argumentos e/ou retornam funções, permitindo a abstração de ações e valores
- **pure functions**: funções puras, não modificam o escopo ao redor. Seu retorno é determinado somente pelos seus próprios argumentos, e o retorno sempre será o mesmo dado os mesmos argumentos.
   ```js
    function dobro(num) {
      return (num * 2)
    }
  ```
