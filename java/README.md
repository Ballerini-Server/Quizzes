# Quiz da tecnologia da semana: Java

## Sobrescrever um método

### 1) Sintaxe para override?

Como podemos sobrescrever o método de uma classe?

a)
```java

@Override
public String toString() {
  return "Sobrescrevendo a função toString()";
}

```

b)
```csharp

public String override toString() {
  return "Sobrescrevendo a função toString()";
}

```

c)
```java

public String toString() {
  return "Sobrescrevendo a função toString()";
}

```

d)
```java

public String toString(): override {
  return "Sobrescrevendo a função toString()";
}

```

### 2) Qual função é executada?

Considerando o seguinte código, o que vai ser mostrado no terminal?

```java

class Program
{
  public static void main(String[] args)
    {
      A instancia = new B();

      instancia.Print();
    }
}
class A
{
  public void Print()
  {
    System.out.println("A");
  }
}
class B extends A
{
  @Override
  public void Print()
  {
    System.out.println("B");
  }
}

```

a) n.d.a

b) A

c) Não compila

d) B


### 3) Contrutor filho

Como chamamos o construtor de uma classe pai através da classe filha?

a)
```java

public Filho(String name, int idade)
{
  base(name, idade);
}

```

b)
```java

public Filho(String name, int idade): base(name, idade)
{
}

```

c)
```java

public Filho(String name, int idade)
{
  super(name, idade);
}

```

d)
```java

public Filho(string name, int idade)
{
  return new Pai(name, idade);
}

```

## 4) Imutabilidade em string

O que aparecerá na tela?

```java

public static void main(String[] args) {
  String texto = "TESTE";
  texto.toLowerCase();
  System.out.println(texto);
}

```

a) teste

b) Teste

c) TESTE

d) error

## 5) Hash Map

O que vai ser mostrado seguindo esse código?

```java

import java.util.Collections;
import java.util.HashMap;
import java.util.Map;

public class Program {

  public static void main(String args[]) {
    Map hashMap = new HashMap();
    hashMap.put(11, "a");
    Collections.unmodifiableMap(hashMap);
    hashMap.put(12, "b");
    System.out.println(hashMap);
  }
}

```

a) { 11 = a }

b) { 11 = a, 12 = b }

c) UnsupportedOperationException

d) Compile time exception

### 6) Qual não existe?

Qual dessas formas não podemos usar para escrever em um arquivo?

a)
```java

OutputStream fos = new FileOutputStream("arquivo.txt");
OutputStreamWriter osw = new OutputStreamWriter(fos);
BufferedWriter bw = new BufferedWriter(osw);
bw.write("Escrevendo");

```

b)
```java

FileWriter fw = new FileWriter("arquivo.txt");
fw.write("Escrevendo");

```

c)
```java

PrintStream ps = new PrintStream("arquivo.txt");
ps.println("Escrevendo");

```

d)
```java

File file = open("arquivo.txt", "w");
file.println("Escrevendo");


```

### 7) JPA o que é falso?

Qual das seguintes afirmações relacionadas ao JPA é falsa? 

A) A Java Persistence API (JPA) mapeia classes Java para tabelas de banco de dados relacional e objetos dessas classes para linhas nas tabelas. Isso é conhecido como mapeamento objeto-relacional.

B) Você pode usar as ferramentas de mapeamento objeto-relacional do NetBeans IDE para selecionar um banco de dados e gerar classes automaticamente que usam JPA para interagir com esse banco de dados. Seus programas podem então usar essas classes para consultar o banco de dados, inserir novos registros, atualizar registros existentes e excluir registros. 

C) Ao contrário do JDBC, você terá que criar mapeamentos entre o código Java e as tabelas do banco de dados e poderá realizar manipulações de banco de dados complexas diretamente em Java.

D) JPA pode ser usado com qualquer sistema de gerenciamento de banco de dados que suporte JDBC.

### 8) EntityManage é?

Preencha: Objeto que implementa o EntityManager \_\_\_\_\_\_\_\_ gerencia as interações entre um programa e o banco de dados.

A) interface 

B) classe 

C) enumeração 

D) Nenhuma das anteriores.


### 9) variáveis de um classe

Como são conhecidas as variáveis ​​criadas dentro de uma classe e fora de qualquer método?

A) Estático

B) Global

C) Instância

D) Local

### 10) Como simplificar

Como simplificar esse trecho de código?
```java

Runnable r = new Runnable() {
  public void run() {
    System.out.println("Hello World");
  }
};
new Thread(r).start();

```

a)
```java

const r = () -> {
  System.out.println("Hello World");
};
new Thread(r).start();

```

b)
```java

new Thread(() -> System.out.println("Hello World")).start();

```

c)
```java

Runnable r = () -> System.out.println("Hello World");
new Thread(r).start();

```

d)
```java

Runnable r = () => System.out.println("Hello World");
new Thread(r).start();

```


### Extra 1) O que é?

Que tipo de "operação/ação" o seguinte código representa:

```java

public void Something(Connection conn, String origem, int nr_origem, String endereco)
  throws Exception {
  Something(conn, origem, nr_origem, nr_volume, endereco, false);
}

public void Something(Connection conn, String origem, int nr_origem, String endereco, boolean transaction_db_control
)
  throws Exception {
  SomethingDTO somethingDTO = new SomethingDAO()
  .getSomething(conn, origem, something, something);

  new SomethingMoreDAO().confirmSomething(conn, origem, something);

  if (!transaction_db_control) {
    conn.commit();
  }
}

```

A) Polimorfismo;
B) Herança;
C) Assinatura de Método;
D) Método com passagem de parâmetro;

### extra 2) hasMoreElements()

Num Iterator, hasMoreElements() método de enumeração foi trocado para?

a) hasNextElement()

b) isNext()

c) hasNext()

d) name remains same



## Gabarito:
1) A
2) D
3) C
4) C
5) B
6) D
7) C
8) A
9) C
10) B
extra 1) C
extra 2) C
