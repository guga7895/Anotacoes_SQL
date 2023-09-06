# Anotacoes_SQL
Anotações relacionadas a estudos externos sobre SQL

## Anotacoes
--SELECT customer_id AS [ID], first_name AS [NOME] 
--FROM Customers 
--WHERE first_name IN("John") OR last_name IN ("Doe")

--SELECT item 
--FROM Orders
--WHERE item LIKE 'M%'

--SELECT age from Customers
--WHERE age > 23 
--AND age BETWEEN 25 AND 29

--SELECT first_name,last_name,item,amount
--FROM Customers
--LEFT OUTER JOIN Orders ON Customers.customer_id = Orders.customer_id

--------------------------------------------------------------------------------------

--CREATE TABLE TabelaTeste ('ID_NF' int,
--                        	'ID_ITEM' int,
--                          'COD_PROD' int,
--                          'VALOR_UNIT' float,
--                          'QUANTIDADE' int,
--                          'DESCONTO (%)' int)

--INSERT INTO TabelaTeste
--VALUES (1,1,1,25,10,5),
--(1,2,2,13.5,3,NULL)

--SELECT ID_NF, ID_ITEM, COD_PROD, VALOR_UNIT, QUANTIDADE FROM TabelaTeste
--WHERE "DESCONTO (%)" IS NULL

--SELECT ID_NF,
--ID_ITEM,
--COD_PROD,
--VALOR_UNIT,
--(VALOR_UNIT - VALOR_UNIT * "DESCONTO (%)"/100) AS "VALOR VENDIDO"
--FROM TabelaTeste
--WHERE "DESCONTO (%)" IS NOT NULL

--UPDATE TabelaTeste 
--SET "DESCONTO (%)" = 0 
--WHERE "DESCONTO (%)" IS NULL

--SELECT ID_NF, (sum(QUANTIDADE * VALOR_UNIT)) AS VALOR_TOTAL
--FROM TabelaTeste
--GROUP BY ID_NF
--ORDER BY ID_NF DESC

--SELECT ID_NF, 
--(sum(QUANTIDADE * VALOR_UNIT-VALOR_UNIT*"DESCONTO (%)"/100)) AS VALOR_VENDIDO
--FROM TabelaTeste
--GROUP BY ID_NF
--ORDER BY VALOR_VENDIDO DESC 

--DELETE FROM TabelaTeste
--WHERE ID_NF = 1 AND VALOR_UNIT=40

--SELECT TOP(1) *
--FROM TabelaTeste
--ORDER BY QUANTIDADE DESC

--SELECT ID_NF,COD_PROD, QUANTIDADE, ID_ITEM 
--FROM TabelaTeste
--WHERE QUANTIDADE >= 10
--GROUP BY ID_NF

--SELECT COD_PROD, (sum("DESCONTO (%)")/COUNT(ID_ITEM)) AS MEDIA
--FROM TabelaTeste
--GROUP BY COD_PROD

--SELECT COD_PROD, 
--MIN("DESCONTO (%)") AS MINIMO,
--MAX("DESCONTO (%)") AS MAXIMO,
--AVG("DESCONTO (%)") AS MEDIA
--FROM TabelaTeste
--GROUP BY COD_PROD
