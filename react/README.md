# Quiz da tecnologia da semana: React

## useState
### 1 Qual o return de useState()

O `useState` é um hook muito utilizado para controlar o estado de uma variável no react (usando componentes no formato de função), qual é o formato do `state` no exemplo a seguir?
```jsx
const state = useState(0);
```

a) `state` é a própria variável que usamos normalmente;

b) `state` é um objeto contendo 2 elementos, `state.state` é o valor da variável que usamos normalmente, e o `state.setState` é uma função para alterarmos o valor da variável;

c) `state` é uma lista com 2 elementos, onde o primeiro elemento é a variável que usamos normalmente, e o segundo elemento é uma função para alterarmos o valor da variável;

d) `state` é um componente React com os dados atualizados;

## useEffect

### 2 Quais parâmetros recebe

O `useEffect` é um hook do react que recebe 2 parâmetros, quais são esses parâmetros?

a) Os valores criados com `useSate`, o primeiro parâmetro deve ser a variável, o segundo parâmetro deve ser a função para alterar a variável;

b) Um componente React para ser renderizado e uma lista de dependência parar colocar dentro do componente passado no primeiro parâmetro;

c) O primeiro parâmetro é uma função que vai ser executada quando o compponente for montado, o segundo parâmetro é uma função que vai ser executada quando o componente for desmontado;

d) O primeiro parâmetro é uma função, o segundo parâmetro é uma lista de dependências que, quando seus valores forem alterados, a função passada no primeiro parâmetro será executada;

### 3 Se tem return na função, para que server?

**Enunciado**
Considerando o seguinte uso do `useEffect`, quando será executado o console.log?
```jsx
useEffect(()=>{
  return ()=>{
    console.log('Hello')
  }
},[])
```
**a)** O `console.log` será executado quando o componente for desmontado;

**b)** O `console.log` será executado quando o componente for atualizado;

**c)** O `console.log` será executado quando o componente for criado;

**d)** O `console.log` será executado quando uma variável do componente tiver seu valor alterado;

## Children props

### 4 prop children 

Como fazemos para fazer os elementos filhos em um componente que nós mesmos criamos aparecer na tela?

```jsx
<Componente>
  <div>
    <h1>Hello World</h1>
  </div>
</Componente>
```

**a)** Eles aparecem automaticamente;

**b)** Não tem como fazer isso no react;

**c)** O componente recebe a propriedade children dentro das props
```jsx
function Componente(props){
  return (
    {props.children}
  )
}
```

**d)** Tem que usar o `useContext` para acessar as propriedades
```jsx
function Componente(){
  const props = useContext(this)
  return (
    {props.children}
  )
}
```

## useContext

### 5 Context.Provider

Ao criar um contexto com `React.createContext`, como devemos fazer para que os componentes da aplicação tenham acesso as variáveis dele?
```jsx
const Context = createContext();

export function UsingContext ({children}){
  const [page, setPage]= useState(1)

  return (
    <Context.Provider value={{page, setPage}}>
      {children}
    </Context.Provider>
  )
}
```

**a)**
```jsx
<App>
  <UsingContext/>
<App/>
```

**b)**
```jsx
<>
  <App/>
  <UsingContext/>
</>
```

**c)**
```jsx
<UsingContext>
  <App/>
</UsingContext>
```

**d)**
```jsx
<Context>
  <App/>
</Context>
```

### 6 useContext value objects

Imaginando o seguinte componente de contexto, como podemos usar o `useContext` para para ter acesso aos valores dele?
```jsx
export const Context = createContext();

export function UsingContext ({children}){
  const [page, setPage]= useState(1)

  return (
    <Context.Provider value={{page, setPage}}>
      {children}
    </Context.Provider>
  )
}
```

**a)** 
```jsx
const [page, setPage] = useContext(Context)
```

**b)** 
```jsx
const {page, setPage} = useContext(Context)
```

**c)** 
```jsx
useContext((page, setPage)=>{
}, [Context])
```

**d)**
```jsx
const {page, setPage}=useContext(Context=>{
  return Context.data
})
```

## Class Components

### 7 controle de estado

Qual a forma correta de fazermos a atualização da variável `count` nesse componente?
```jsx
export default class ClassComponent extends Component {
  constructor() {
    super()
    this.state = {
      count: 0    // <-- essa variável
    }
    this.handleChange = this.handleChange.bind(this)
  }
  handleChange(event) {
    // o que colocar aqui?
  }
  render() {
    return (
      <div className="content">
        <input
          type="number"
          value={this.state.count}
          onChange={this.handleChange}
        />
      </div>
    )
  }
}
```

**a)**
```jsx
this.state.count = 0
```

**b)**
```jsx
this.state.setState({
  count: 0
})
```

**c)**
```jsx
setState({count: 0})
```

**d)**
```jsx
this.state.count.update(0)
```


### 8 passando props

Como recebemos as propriedades do componente no formato de classe?
```jsx
<ComponenteFilho nome="React" />
```

**a)**
```js
class ClassComponent extends Component {
  onInit(props){
    console.log(props.nome)  // Retorna React
  }
}
```

**b)**
```js
class ClassComponent extends Component {
  constructor(props) {
    super(props)
    console.log(props.nome)  // Retorna React
  }
}
```

**c)**
```js
class ClassComponent extends Component {
  componentDidMount(props){
    console.log(props.nome)  // Retorna React
  }
}
```

**d)**
```js
class ClassComponent extends Component {
  componentDidCatch(props){
    console.log(props.nome)  // Retorna React
  }
}
```

### 9 como iniciar?

Como podemos iniciar um projeto usando o react-app com npm?

**a)** npx create-react-app myreactapp

**b)** npx create react app myreactapp

**c)** npx create react-app myreactapp

**d)** npx create myreactapp react-app


## 10 eventos

### Como receber eventos no react

Como podemos fazer com que o componente pai tenha acesso ao resultado da função getUserFromAPI?
```jsx
function ComponenteFilho(){
  async function handleClick(){
    const user = await getUserFromAPI();
    // passar user para o componente pai
  }

  return (
    <button onClick={handleClick}>Buscar dados</button>
  )
}
```

**a)** Devemos fazer com que o componente filho receba uma variável, e vai ser atribuido nessa variável o valor do `user`
```jsx
// ComponentePai.jsx
<ComponenteFilho nomeDaVariavel={user}/>
// ComponenteFilho.jsx
function ComponenteFilho({nomeDaVariavel}){
  async function handleClick(){
    const user = await getUserFromAPI();
    nomeDaVariavel = user
  }
  // ...
}
```

**b)** Devemos fazer com que o componente filho receba uma função, essa função recebe o `user` como parâmetro, e o componente pai vai usar essa função, o comportamento é similar ao evento no html puro;
```jsx
// ComponentePai.jsx
<ComponenteFilho nomeDaFuncao={(user)=>{/*faz alguma coisa*/}}/>

// ComponenteFilho.jsx
function ComponenteFilho({nomeDaFuncao}){
  async function handleClick(){
    const user = await getUserFromAPI();
    nomeDaFuncao(user)
  }
  // ...
}
```

**c)** Devemos criar um `useCallback` para receber o valor do user, ele vai automaticamente mandar para o componente pai
```jsx
// ComponentePai.jsx
<ComponenteFilho callback={(user)=>{/*faz alguma coisa*/}}/>

// ComponenteFilho.jsx
const callback = useCallback(user)

function ComponenteFilho({nomeDaFuncao}){
  async function handleClick(){
    const user = await getUserFromAPI();
    callback(user)
  }
  // ...
}
```

**d)** Devemos usar `this.bind` para linkar a variável que recebemos no componente filho, com o resutlado da `getUserFromAPI`
```jsx
// ComponentePai.jsx
<ComponenteFilho nomeDaVariavel={user}/>

// ComponenteFilho.jsx
function ComponenteFilho({nomeDaVariavel}){
  async function handleClick(){
    const user = await getUserFromAPI();
    this.bind(user)
  }
  // ...
}
```

## Extras

### imperativeHandle: como usar? FAIL


Considerando esses dois componentes, qual vai ser o log no console quando clicar no botão do componente pai?
```jsx
// Componente pai
const inputRef = useRef(null);
const handleClick = () => {
  console.log(inputRef.current)
};
return (
  <>
    <InputTextoImperative ref={inputRef}/> 
    <button onClick={handleClick}>Clique em Mim</button>
  </>
)

// InputTextoImperative.jsx (componente filho)
function InputTextoImperative(props, ref) {
  const inputRef = useRef(null);
  useImperativeHandle(ref, () => ({
    focus: () => {
      inputRef.current.focus();
    },
    nome: 'Rafaella Ballerini'
  }));

  return (
    <input ref={inputRef} type="text" />
  );
}

export default forwardRef(InputTextoImperative);
```

**a)** A referência para o input do componente InputTextoImperative;

**b)** A referencia para o componente InputTextoImperative;

**c)** Vai dar erro por causa do uso do `forwardRef`;

**d)** Um objeto contendo 2 propriedades, `nome` e uma função `focus`;


## Gabarito:
1) C
2) D
3) A
4) C
5) C
6) B
7) B
8) B
9) A
10) B
EXTRA) B