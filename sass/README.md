# Quiz da tecnologia da semana: SASS

## Identação

### 1) Como estilizar um elemento

Como fazemos no .sass para um input ter um fundo preto?

a)
```sass
input
  background-color: black
```

b)
```sass
input:
  background-color: black
```

c)
```sass
input {
  background-color: black
}
```

d)
```sass
input do:
  background-color: black
```

## Encadeamento

### 2) Como estilizar um elemento dentro de outro

Qual a melhor forma de estilizar a div com fundo preto, e o input dentro da div com border-radius de 4px, usando .sass

a)
```sass
div
  background-color: black

div  input
    border-radius: 4px
```

b)
```sass
div{
  background-color: black
  input{
    border-radius: 4px
  }
}
```

c)
```sass
div
  background-color: black
  input
    border-radius: 4px
```

d)
```sass
div{
  background-color: black
}
input{
  border-radius: 4px
}
```

## mixins

### 3) Como utilizar mixin

Como podemos utilizar esse mixin em um elemento em .sass?
```sass
@mixin nomeMixin()
  display: flex
  align-items: center
  justify-content: center
```

a)
```sass
.container @include nomeMixin
  flex-direction: column
```

b)
```sass
.container
  @include nomeMixin()
  flex-direction: column
```

c)
```sass
.container
  @extend nomeMixin
  flex-direction: column
```

d)
```sass
.container
  @extend nomeMixin()
  flex-direction: column
```

### 4) Passando parâmetros

Como criamos um mixin recebendo o parâmetro declarando o tipo do flex-direction?

a)
```sass
@mixin nomeMixin(type)
  display: flex
  align-items: center
  justify-content: center
  flex-direction: $type
```

b)
```sass
@mixin nomeMixin($type)
  display: flex
  align-items: center
  justify-content: center
  flex-direction: $type
```

c)
```sass
@mixin nomeMixin(var type)
  display: flex
  align-items: center
  justify-content: center
  flex-direction: $type
```

d)
```sass
@mixin nomeMixin var type
  display: flex
  align-items: center
  justify-content: center
  flex-direction: $type
```

## darken

### 5) Syntaxe darken()

Qual é a forma correta de utilizar a função darken?

a)
```sass
color: #302326.darken(0.3)
```

b)
```sass
color: darken(#302326, 15)
```

c)
```sass
color: darken #302326, 0.3
```

d)
```sass
color: $darken(#302326, 0.3)
```

## import

### 6) Syntaxe import

Considerando que tenho esses 2 arquivos .sass, o que vai acontecer ao utilizar o $background no main.sass?
```sass

# constants.sass

$background: #302326

# main.sass

@import "./constants.sass"

body
  background-color: $background
```

a) O background do body vai ficar com valor vazio (none)

b) O background do body vai ficar com o valor padrão (white)

c) O background do body vai ficar com o valor #302326

d) Vai dar erro na hora de transformar pra css

## extends

### 7) Utilidade

Como podemos utilizar essa classe como base para outros elementos no .sass?
```sass
.flex
  display: flex
  align-items: center
  justify-content: center
```

a)
```sass
.container extends flex
```

b)
```sass
.container(.flex)
```

c) 
```sass
.container
  @import .flex
```

d)
```sass
.container
  @extend .flex
```

## each

### 8) Qual o resultado no css

Qual o resultado desse código quando transpilado de .sass para css?
```sass
$colors: (blue, red, yellow)

@each $color in $colors
  .#{$color}-text
    color: $color
```

a)
```css
.1-text {
  color: blue;
}

.2-text {
  color: red;
}

.3-text {
  color: yellow;
}
```

b)
```css


.blue-text {
  color: blue;
}

.red-text {
  color: red;
}

.yellow-text {
  color: yellow;
}
```

c)
```css


.color1-text {
  color: blue;
}

.color2-text {
  color: red;
}

.color3-text {
  color: yellow;
}

```

d)
```css
.c1-text {
  color: blue;
}

.c2-text {
  color: red;
}

.c3-text {
  color: yellow;
}
```

### 9) if else

Como declarar os blocos if else no .sass?

a)
```
@mixin teste($direction)
  @if direction == up
    background: blue
  @else if direction == right
    background: red
```

b)
```
@mixin teste($direction)
  @if $direction == up
    background: blue
  @else if $direction == right
    background: red
```

c)
```
@mixin teste($direction)
  @if $direction == up
    background: blue
  @else $direction == right
    background: red
```

d)
```
@mixin teste($direction)
  $direction == up? background: blue : background: red
```

### 10) Truthyness

Considerando o seguinte mixin e a chamada dele pelo <body>, qual css vai ser considerado no final?
```sass
@mixin teste($value)
  @if ($value)
    background-color: blue
  @else
    background-color: red

body
  @include teste(0)
```

a)
```css

body {
  background-color: blue;
}

```

b)
```css

body {
  background-color: red;
}

```

c)
```css

body {
  background-color: none;
}

```

d) Erro para transpilar


## Gabarito:
1) A
2) C
3) B
4) B
5) B
6) C
7) D
8) B
9) B
10) A
