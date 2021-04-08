# Quiz da tecnologia da semana: CSS

## selectors: umas 2 perguntas;

### 1) Selectors: Pergunta 1 

Como fazer com que todas as <li> (exceto a primeira) tenham borda no top?

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
  <li>Item 4</li>
  <li>Item 5</li>
</ul>
```
**a)**
```css
ul li + li{
  border-top: 1px solid black;
}
```
**b)**
```css
li{
  border-top: 1px solid black;
}
```
**c)**
```css
ul li:first-child{
  border-top: 1px solid black;
}
```
**d)**
```css
ul li{
  border-top: 1px solid black;
}
```

### 2) Selectors: Pergunta 2

Qual é o mais espefícico?

**a)**
```css
div {}
```
**b)**
```css
#content p {}
```
**c)**
```css
#menu .item {}
```
**d)**
```css
button:hover{}
```

## Flexbox: umas 2 perguntas;

### 3) Flexbox: Pergunta 1

Como deixar todos os elementos com espaçamento entre eles?
```html
<nav>
  <li>Home</li>
  <li>Contact</li>
  <li>SignIn</li>
</nav>
```

**a)**
```css
nav {
  width: 100%;
  display: flex;
  justify-content: center;
}
```

**b)**
```css
nav {
  width: 100%;
  display: flex;
  justify-content: space-between;
}
```

**c)**
```css
nav {
  width: 100%;
  display: flex;
  align-content: space-between;
}
```

**d)**
```css
nav {
  width: 100%;
  display: flex;
  align-items: space-between;
}
```

### 4) Flexbox: Pergunta 2

Qual das alternativas abaixo corresponde a forma correta de habilitar o flex-box?

```html
<div class="flex-container">
  <div>Flex 1</div>
  <div>Flex 2</div>
  <div>Flex 3</div>
</div>
```

**a)**
```css
.flex-container{
  flex: 1;
}
```

**b)**
```css
.flex-container{
  flex-direction: row;
}
```

**c)**
```css
.flex-container{
  display: flex;
}
```

**d)**
```css
.flex-container{
  display: grid;
}
```

### 5) Importando css

Qual dessas opções faz o import correto dos estilo?

**a)**
```html
<css href="./styles.css"></css>
```

**b)**
```html
<body styles="./styles.css" rel="stylesheet">
```

**c)**
```html
<link rel="stylesheet" href="./style.css">
```

**d)**
```html
<head src="style.css">
```

## Gabarito:
1) A
2) C
3) B
4) C
5) C