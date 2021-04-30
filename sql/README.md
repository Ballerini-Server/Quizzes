# Quiz da tecnologia da semana: SQL

## 1) Criando tabelas

Como podemos criar uma tabela "pessoas" com os campos id (número), nome(texto)?

a)
```sql
CREATE TABLE pessoas (
   NOT NULL id int,
   NOT NULL nome varchar,
)
```

b)
```sql
CREATE DATABASE pessoas (
  id int NOT NULL,
  nome varchar NOT NULL,
) 
```

c)
```sql
CREATE TABLE pessoas (
  id,
  nome
)
```

d)
```sql
CREATE TABLE pessoas (
  id int,
  nome varchar(255),
)
```

## 2) Como atualizar um valor

Como fazemos para atualizar o nome de uma pessoa?

a)
```sql
UPDATE pessoas(
  SET nome='novoNome'
  WHERE nome='nomeAntigo' 
)
```

b)
```sql
UPDATE pessoas  SET nome='novoNome'  WHERE nome='nomeAntigo'
```

c)
```sql
select pessoas
  set nome='novoNome'
  where nome='nomeAntigo'
```

d)
```sql
UPDATE pessoas
  WHERE nome='nomeAntigo'
  SET nome='novoNome'
```

## 3) O que é NOT NULL

Qual é a finalidade de utilizar os termos NOT NULL para criar um campo numa tabela?
```sql
CREATE DATABASE pessoas 
  id int NOT NULL
```

a) Serve para dizer que a tabela deve iniciar com pelo menos um elemento já

b) Serve para dizer que o campo não pode estar vazio

c) Serve para dizer que o campo deve estar vazio na criação

d) É apenas um padrão de convensão, não significa nada

## 4) O que é Alter

Para que serve o termo ALTER em SQL?

a) Deletar linhas da tabela

b) Mudar as informações na tabela

c) Mudar a estrutura da tabela

d) Adicionar linhas na tabela

## 5) DELETE

Qual a forma correta de deletar um item da tabela?

a)
```sql
DELETE FROM pessoas WHERE nome='Matan';
```

b)
```sql
DROP FROM pessoas WHERE nome='Matan';
```

c)
```sql
DELETE FROM pessoas;
```

d)
```sql
DROP ROW FROM pessoas WHERE nome='Matan';
```

## 6) Usando IN

Qual dessas é a forma correta de usar o operador IN

a)
```sql
SELECT * FROM pessoas
LIKE pais IN ('UK', 'France', 'USA');
```

b)
```sql
SELECT * FROM pessoas
WHERE ('UK', 'France', 'USA') IN pais;
```

c)
```sql
SELECT * FROM pessoas
WHERE pais IN ('UK', 'France', 'USA');
```

d)
```sql
SELECT * FROM pessoas
WHERE pais IN 'UK', 'France', 'USA';
```

## 7) Como ordernar a lista por nome?

Como podemos ordenar o resultado da query através do nome?

a)
```sql
SELECT * FROM pessoas
ORDER BY nome;
```

b)
```sql
ORDER BY nome 
SELECT * FROM pessoas
```

c)
```sql
SELECT * FROM pessoas
SORT nome;
```

d)
```sql
SELECT * FROM pessoas
WHERE ORDER BY nome;
```

## 8) Como fazer relacionamento muitos pra 1?

O que devemos adicionar na criação da tabela pessoas para ela ter um relacionamento de muitas pra um pais?
```sql
CREATE TABLE pais (
  id int PRIMARY KEY,
  nome varchar(255),
)

CREATE TABLE pessoas (
  id int PRIMARY KEY,
  nome varchar(255),
  paisId int,
)
```

a)
```sql
FK__pessoas__pais FOREIGN KEY (paisId) REFERENCES pais(id),
```

b)
```sql
CONSTRAINT FK__pessoas__pais FOREIGN KEY (paisId) FROM pais(id),
```

c)
```sql
CONSTRAINT FK__pessoas__pais PRIMARY KEY (paisId) REFERENCES pais(id),
```

d)
```sql
CONSTRAINT FK__pessoas__pais FOREIGN KEY (paisId) REFERENCES pais(id),
```

## 9) Relacionamento many to many

Qual é a forma correta de termos no banco de dados um relacionamento de muitos pra muitos?

a) Basta que cada tabela tenha um array de chaves estrangeiras para a outra

b) Basta que cada tabela tenha uma chaves estrangeiras para a outra

c) Deve ser criado uma tabela intermediária que faz relacionamento um pra muitos com ambas as tabelas principais

d) Basta que tenha um campo em cada tabela com o nome da propriedade referência na outra tabela, exemplo: pessoasId em aulas, e aulasId em pessoas

## 10) Usando INNER JOIN

Dado essa relação entre pais e pessoas, como pegamos uma lista que mostre os dados da pessoa e o nome do país?
```sql
CREATE TABLE pais (
  id int PRIMARY KEY,
  nome varchar(255),
)

CREATE TABLE pessoas (
  id int PRIMARY KEY,
  nome varchar(255),
  paisId int,
  CONSTRAINT FK FOREIGN KEY (paisId) REFERENCES pais(id),
)
```

a)
```sql
SELECT pessoas.id, pessoas.nome, pais.nome
  FROM pessoas
  INNER JOIN pais on pessoas.paisId=pais.id
```

b)
```sql
SELECT pessoas.id, pessoas.nome, pais.nome
  FROM pessoas
```

c)
```sql
SELECT * FROM pais
```

d)
```sql
SELECT pessoas.id, pessoas.nome, pais.nome
  FROM pessoas
  INNER JOIN pais where pessoas.paisId=pais.id
```

## Gabarito:
1) D
2) B
3) B
4) C
5) A
6) C
7) A
8) D
9) C
10) A
