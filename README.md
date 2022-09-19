# SQL
## DISTINCT
```sh
DISTINCT x, y
FROM table
```
-- Pego os valores diferentes dessas colunas

## COUNT
```sh
COUNT(x) FROM table 
```
-- Pego a quantidade de itens dessa coluna 

## Alguns Operadores
- BETWEEM(entre um intervalo)
- LIKE(CONTAINS)
- IN(EM UM LOCAL)
- NOT(NEGAÇÃO)
- OR(OU)
- AND(E)

## ORDER BY
```sh
SELECT * FROM Table ORDER BY Column (ASC or DESC)
```
-- Ordeno os valores em crescente ou decrescente

## INSERT
```sh
INSERT INTO table (Columns...) VALUES (Values....) 
INSERT INTO table (Values.....)
```
-- Insiro valores em uma tabela especificando colunas ou não

## NULL
```sh
IS NULL
IS NOT NULL
```
-- Para verificar valores nullos ou não nullos

## UPDATE
```sh
UPDATE table SET column1 = value1, column2 = value2... WHERE condition
```
-- Atualizo valores em uma tabela

## DELETE
```sh
DELETE FROM table WHERE condition
DELETE FROM table
```
-- Deleto registros em uma tabela com condição ou sem

## TOP
```sh
SELECT TOP numero * FROM tabela 
```
-- Seleciona o primeiros registros de uma tabela de acordo com o numero informado

## MIN - MAX
-- Seleciono o menor e o maior valor de uma coluna

## FUNÇÕES
- COUNT() = Numero de linhas de certa coluna
- AVG() = Valor medio de uma coluna numerica
- SUM() = Soma total de uma coluna numerica

## LIKE
```sh
SELECT * FROM tabela WHERE Column LIKE '%a%' 
```
-- Usado junto ao where, posso utilizar (%) para varios caracteres ou (_) para um único
| Comando | Retorno |
| ------ | ------ |
| WHERE CustomerName LIKE 'a%' | todas palavras que comecem com "a" |
| WHERE CustomerName LIKE '%a' | todas palavras que terminam com "a" |
| WHERE CustomerName LIKE '%or%' | todas palavras que possuam "or" em alguma posição |
| WHERE CustomerName LIKE '_r%' | todas palavras que possuam "r" na segunda posição |
| WHERE CustomerName LIKE 'a_%' | todas palavras que iniciam com "a" e tenham 2 caracteres ou mais |
| WHERE CustomerName LIKE 'a__%' | todas palavras que iniciam com "a" e tenham 3 caracteres ou mais |
| WHERE ContactName LIKE 'a%o' | todas palavras que iniciam com "a" e terminam com "o" |

## IN
```sh
SELECT * FROM table WHERE column IN ('x','y')
```
-- Seleciono todos registros em que a coluna possui x ou y

## BETWEEN
```sh
SELECT * FROM table WHERE column BETWEEN value1 AND value2
```
-- Seleciono todos os valores dentro do intervalo definido por valor1 e 2 

## ALIAS
```sh
SELECT Column AS alias_name FROM table 
```
-- Utilizo a palavra AS para nomear uma coluna ou tabela temporaria
```sh
SELECT Column1, Column2 + ', ' + Column3 + ' ' + Column4 + ', ' + Column5 AS ColumnsConcatened
FROM table;
```
-- Utilizo a palavra AS para nomear uma coluna onde teve varias colunas concatenadas
```sh
SELECT o.Column1, o.Column2, c.Column1
FROM Customers AS c, Orders AS o
WHERE c.Column1='Around the Horn' AND c.Column2=o.CustomerID;
```
-- Atribuo um nome temporario a tabelas e as utilizo durante o comando

## JOIN 
```sh
SELECT table.Column1, table.Column2, table.Column3
FROM table
INNER JOIN table2 ON table.Column1 = table2.Column1;
```
-- Faço a junção de duas tabelas que possuam uma referencia igual, existem diferentes tipos de JOINs

 - (INNER) JOIN: Retorna registros que possuem valores correspondentes em ambas as tabelas
 - LEFT (OUTER) JOIN: Retorna todos os registros da tabela da esquerda e os registros correspondentes da tabela da direita
 - RIGHT (OUTER) JOIN: Retorna todos os registros da tabela da direita e os registros correspondentes da tabela da esquerda
 - FULL (OUTER) JOIN: Retorna todos os registros quando há uma correspondência na tabela esquerda ou direita

## UNION 
```sh
SELECT Column FROM table1
UNION
SELECT Column FROM table2
ORDER BY Column;
```
-- Retorno valores distintos entre as colunas especificadas, de duas tabelas diferentes, posso utilizar UNION ALL para retornar valores duplicados também

## GROUP BY 
```sh
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
```
-- Agrupo todas as linhas de uma tabela que contenham mesmo valores

## HAVING 
```sh
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
```
-- Utilizado como se fosse o where porem para funções agregadas

## EXISTS 
```sh
SELECT column_name(s)
FROM table_name
WHERE EXISTS
(SELECT column_name FROM table_name WHERE condition);
```
-- Utilizado para verificar se uma condição existe, retorna true ou false