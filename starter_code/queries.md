# Entrega do exercício da semana

### 1. Todas as empresas cujo nome corresponde a ***'Babelgum'***. Recupere apenas o campo name.
~~~
FILTER {name:"Babelgum"}
PROJECT {name:1}
~~~
### 2.Todas as empresas com mais de 5.000 funcionários. Limite a pesquisa a 20 empresas e classifique-as por number of employees.
~~~
FILTER {number_of_employees:{$gt:5000}}
SORT {number_of_employees:1}
LIMIT {20}
~~~
### 3. Todas as empresas fundadas entre 2000 e 2005, ambos os anos incluídos. Recupere apenas os campos name e founded_year.
~~~
FILTER {founded_year:{$gte:2001, $lte: 2005 }}
PROJECT {name:1, founded_year:1}
~~~
### 4. Todas as empresas que tiveram um Valor de Avaliação superior a 100.000.000 e foram fundadas antes de 2010. Recupere apenas os campos name e ipo.
~~~
FILTER {$and:[{"ipo.valuation_amount":{$gte:100000000}},{founded_year:{$lt:2010}}]}
PROJECT {name:1, ipo:1}
~~~
### 5. Todas as empresas que tenham menos de 1000 funcionários e tenham sido fundadas antes de 2005. Ordene-as pelo número de funcionários e limite a pesquisa a 10 empresas.
~~~
FILTER {$and:[{number_of_employees:{$lt:1000}},{founded_year:{$lt:2005}}]}
SORT {number_of_employees:1}
LIMIT {10}
~~~
### 6. Todas as empresas que não incluem o campo partners.
~~~
FILTER {partners: []}
~~~
### 7. Todas as empresas que possuem um tipo nulo de valor no campo category_code.
~~~
FILTER {category_code:null}
~~~
### 8. Todas as empresas que têm pelo menos 100 funcionários, mas menos de 1000. Recupere apenas os campos name e number of employees.
~~~
FILTER {number_of_employees:{$gte: 100, $lt:1000}}
PROJECT {name:1, number_of_employees:1}
~~~
### 9. Ordene todas as empresas pelo preço de ipo de forma descendente.
~~~
SORT {ipo:-1}
~~~
### 10. Recupere as 10 empresas com mais funcionários, ordenado pelo number of employees
~~~
SORT {number_of_employees:-1}
LIMIT {10}
~~~
### 11. Todas as empresas constituídas no segundo semestre do ano. Limite sua pesquisa a 1000 empresas.
~~~
FILTER {founded_month:{$gte:7}}
LIMIT {1000}
~~~
### 12. Todas as empresas fundadas antes de 2000 que tenham um valor de aquisição superior a 10.000.000
~~~
FILTER {$and:[{founded_year:{$lt:2000}},{"acquisition.price_amount":{$gt:10000000}}]}
~~~
### 13. Todas as empresas adquiridas após 2015, ordenam pelo valor de aquisição e recuperam apenas os campos name e acquisition.
~~~
FILTER {"acquisition.acquired_year":{$gt:2005}}
PROJECT {acquisition:1}
SORT {"acquisition.price_amount":1}
~~~
### 14. Ordene as empresas por seu founded year, recuperando apenas seu name e founded year.
~~~

PROJECT {name:1, founded_year:1}
SORT {founded_year:1}
~~~

### 15. Todas as empresas constituídas nos primeiros sete dias do mês, incluindo o sétimo. Classifique-os por seu acquisition price de forma descendente. Limite a pesquisa a 10 documentos.
~~~

FILTER {founded_day:{$lte:7}}
SORT {"acquisition.price_amount":-1}
LIMIT {10}
~~~