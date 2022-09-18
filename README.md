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
