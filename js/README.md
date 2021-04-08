# Quiz Javascript

## const, var e let

### diferenças

1) Qual é a diferença entre `const`, `var` e `let` no javascript?

a) `const` faz uma variável não poder mudar de valor, `let` permite que ela altere seu valor sem sair do escopo, `var` inicia a variável no início do arquivo (hoisting);

b)`let` permite que ela altere seu valor sem sair do escopo, `var` inicia a variável no início do arquivo (hoisting), `const` declara uma função anônima (lambda);

c) `const` faz uma variável não poder mudar de valor, `let` instancia uma classe, `var` inicia a variável no início do arquivo (hoisting);

d) `const` faz uma variável não poder mudar de valor, `let` inicia a variável no início do arquivo (hoisting), `var` permite que ela altere seu valor sem sair do escopo;


### código válido

2) Qual dos seguintes códigos, não vai dar erro?

a)
```js
console.log(texto)
const texto = "Boa noite!"
```

b)
```js
function imprimeTexto(){
  console.log(texto)
}
imprimeTexto()
let texto = "Boa noite!"
```

c)
```js
function imprimeTexto(){
  const texto = "Boa noite!"
}
imprimeTexto()
console.log(texto)
```


d)
```js
function imprimeTexto() {
  console.log(texto)
}
const texto = "Boa noite!"
imprimeTexto()
```

## == ou ===

### Qual vai dar o valor esperado

3) Qual dessas comparações vai dar falso?

a)
```js
console.log([]==0)
```

b)
```js
console.log("10"===10)
```

c)
```js
console.log("10"==10)
```

d)
```js
console.log(undefined==null)
```

## Arrow Function

### Como usar?

4) Como fazemos a declaração de uma arrow function no javascript?

a)
```js
const minhafuncao => function () {
}
```
b)
```js
const minhafuncao = (){
}
```
c)
```js
function minhafuncao(){
}
```

d)
```js
const minhaFuncao = () => {
}
```

### Como abreviar se já tem o retorno direto

5) Como podemos simplificar a seguinte arrow function?
```js
const sum = (a, b) =>{
  return a + b
}
```

a)
```js
const sum = (a, b) => a + b
```

b)
```js
const sum(a, b) => a + b
```

c)
```js
function sum(a, b)=> a + b
```

d)
```js
const sum = a + b
```

## Math.random

### Qual da o retorno correto

6) Qual é a forma correta de utilizar a função Math.random, se queremos números de 1 até 10?

a)
```js
const numero = Math.random(10)*10
```

b)
```js
const numero = Math.random(10)*10+1
```

c)
```js
const numero = Math.random *10+1
```

d)
```js
const numero = Math.random(10)
```

## Map

### Parametros

7) A função map(), recebe como parâmetro outra função que você declara, essa função recebe 3 parâmetros, quais são eles?

```js
const list = [1,2,3,4]
list.map((a, b, c)=>{})
```

a)
a: A lista por completo;
b: O índice do elemento na lista;
c: O elemento da lista;

b)
a: O elemento da lista;
b: O elemento anterior;
c: A lista por completo;

c)
a: O elemento da lista;
b: O índice do elemento na lista;
c: A lista por completo;

d)
a: O elemento da lista;
b: O índice do elemento na lista;
c: O elemento anterior;

## Eventos

### Como chamar?

8) Qual dessas opções é **errada** para chamar uma função no evento de click de um elemento?

a)
```js
const div = document.getElementById('idlegal');

div.onclick((event) => {
})
```

b)
```js
const div = document.getElementById('idlegal');
div.addEventListener('click', (event) => {
})
```

c)
```html
<div onclick="respondendoEvento(event)"></div>
<script>
  function respondendoEvento(event) {
  }
</script>
```
```js
function respondendoEvento(event) {
}
```

d)
```html
<div onclick="respondendoEvento(this)"></div>
<script>
function respondendoEvento(event) {
}
</script>
```
```js
function respondendoEvento(event) {
}
```

## Filter

### Qual o retorno

9) Qual o retorno da função filter, usada em um array?

a) Um objeto contendo os elementos do array que correspondem a condição filtrada;
b) Uma lista dos elementos que correspondem a condição filtrada;
c) O primeiro elemento que corresponde a condição filtrada;
d) A quantidade de elementos que correspondem a condição filtrada;

## Template String

### Como usar
B

10) Qual dessas opções é a forma correta de concatenar texto e valores em uma string?

a)
```js
const world = "World";
const texto = f'Hello {}!',(world);
```

b)
```js
const world = "World";
const texto = `Hello ${world}!`;
```

c)
```js
const world = "World";
const texto = f'Hello {world}!';
```

d)
```js
const world = "World";
const texto = 'Hello {$1}!', (world);
```

## Gabarito:
1) A
2) D
3) B
4) D
5) A
6) B
7) C
8) D
9) B
10) B