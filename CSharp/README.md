# Quiz da tecnologia da semana: CSharp

## Print na tela

### 1) Como fazer Print

Como fazemos no C# para printar algo no terminal?

a) Console.Print("Hello World!");
b) Console.Write("Hello World!");
c) Print("Hello World!");
d) Console.WriteLine('Hello World!')


## Interface

### 2) Qual dessas interfaces não vai dar erro

2) Qual dessas interfaces não vai dar erro?

a)
```csharp

interface IInterface
{
  static string Name { get; set; }
  static void Init();
}

```
b)
```java

interface IInterface
{
  String Name;
  void Init()
}

```
c)
```ts

interface IInterface
{
  Name: string;
  Init: ()=>void;
}

```
d)
```csharp

interface IInterface
{
  string Name { get; set; }
  void Init();
}

```

### 3) Como declarar que uma classe implementa uma interface

Como declarar que uma classe usa uma interface?

a)
```csharp

public class MinhaClasse : IInterface
{

}

```
b)
```java

public class MinhaClasse implements IInterface
{

}

```
c)
```java

public class MinhaClasse extends IInterface
{

}

```
d)
```csharp

public class MinhaClasse<IInterface>
{

}

```

## Declarando Variáveis

### 4) Array

Qual dessa é a forma correta de declarar um array no CSharp?

a)
```java

String[3] listaEmTexto = { "Csharp", "Java", "Javascritp" };

```
b)
```csharp

String[] listaEmTexto = ["Csharp", "Java", "Javascritp" ];

```
c)
```csharp

String[] listaEmTexto = ( "Csharp", "Java", "Javascritp" );

```
d)
```csharp

String[] listaEmTexto = { "Csharp", "Java", "Javascritp" };

```
## Herança

### 5) Contrutor filho

Como chamamos o construtor de uma classe pai através da classe filha?

a)
```csharp

public Filho(string name, int idade)
{
  base(name, idade)
}

```

b)
```csharp

public Filho(string name, int idade): base(name, idade)
{

}

```

c)
```csharp

public Filho(string name, int idade)
{
  super(name, idade)
}

```

d)
```csharp

public Filho(string name, int idade)
{
  return new Pai(name, idade)
}

```

### 6) Qual função é executada?

Considerando o seguinte código, o que vai ser mostrado no terminal?
```csharp

class A
{
  public virtual void Print()
  {
    Console.WriteLine("A");
  }
}
class B : A
{
  public override void Print()
  {
    Console.WriteLine("B");
  }
}
class Program
{
  static void Main(string[] args)
    {
      A instancia = new B();

      instancia.Print();
    }
}

```

a) B

b) Não compila

c) n.d.a

d) A

### 7) O que acontece quando tenho 2 objetos com a mesma referência

O que vai ser mostrado no Console?
```csharp

class A
{
  public String Name { get; set; }
}
class Program
{
  static void Main(string[] args)
  {
    A primeiro = new A();
    A segundo = primeiro;
    primeiro.Name = "Trocando o nome";
    Console.WriteLine(segundo.Name);
  }
}

```

a) Não Compila

b) ""

c) "Trocando o nome"

d) Error

### 8) Sintaxe delegate

Considerando o seguinte encadeamento de delegates, o que será mostrado em tela?
```csharp


public delegate string WriteMessage(string message);
public static WriteMessage LogToConsole = (string message) =>
  {
    Console.WriteLine(message);
    return message + message;
  };
static void Main(string[] args)
{
  WriteMessage Testando = LogToConsole;
  Testando += LogToConsole;
  var response = Testando("message");
}


```

a)
message

b)
message
messagemessage

c)
messagemessage

d)
message
message

### Simplificando delegates

Como simplificar o seguinte código?

```csharp

Func<int, int, int> sum = delegate (int a, int b) { return a + b; };

```

a)
```csharp

Func<int, int, int> sum = (int a, int b) { return a + b; };

```

b)
```csharp

Func<int, int, int> sum = delegate (int a, int b) => return a + b;

```

c)
```csharp

Func<int, int, int> sum = (a, b) => a + b;

```

d)
```csharp

Func<int, int, int> sum = delegate (a, b) => a + b;

```

### 10) Try/Catch sintaxe

Como podemos verificar erros diferentes em um bloco Try/Catch?

a) Não podemos;

b)
```ts

try{

}catch (exception){
  if(typeof exception == DivideByZeroException){
  }
  else if(typeof exception == SystemException){
  }
}

```

c)
```csharp

try{
} catch (DivideByZeroException exception){
} catch (SystemException exception){
}

```

d)
```csharp

try{
} (DivideByZeroException exception) => {
} (SystemException exception) => {
}

```



## Gabarito:
1) B
2) D
3) A
4) D
5) B
6) A
7) C
8) D
9) C
10) C
