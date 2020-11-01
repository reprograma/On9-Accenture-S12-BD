<!-- EXERCICIOS QUERIES DO BANCO DE DADOS - MongoDB Compass -->


<!-- 1.Todas as empresas cujo nome corresponde a 'Babelgum'. Recupere apenas o campo name. -->
{ name: {$all: ["Babelgum"]}}

<!-- 2. Todas as empresas com mais de 5.000 funcionários. Limite a pesquisa a 20 empresas e classifique-as por number of employees. -->
{ number_of_employees: {$gte: 5.000}}

<!-- 3. Todas as empresas fundadas entre 2000 e 2005, ambos os anos incluídos. Recupere apenas os campos name e founded_year. -->
{ name: {$elemMatch: { founded_year: <2000>, <2001>, <2002>, <2003>, <2004>, <2005> }}}

<!-- 4. Todas as empresas que tiveram um Valor de Avaliação superior a 100.000.000 e foram fundadas antes de 2010. Recupere apenas os campos name e ipo. -->
{ name: {$gte: {ipo: "100.000.000", founded_year: {$lte: "2010"}}}}

<!-- 5. Todas as empresas que tenham menos de 1000 funcionários e tenham sido fundadas antes de 2005. Ordene-as pelo número de funcionários e limite a pesquisa a 10 empresas. -->
{ name: {$lt: "1000", founded_year: {$lt: "2005", number_of_employees: {$eq: 10}}}}

<!-- 6. Todas as empresas que não incluem o campo partners. -->
{ name: {$nin: ["partners"]}}

<!-- 7. Todas as empresas que possuem um tipo nulo de valor no campo category_code. -->
{ category_code: {$eq: "null"}}

<!-- 8. Todas as empresas que têm pelo menos 100 funcionários, mas menos de 1000. Recupere apenas os campos name e number of employees. -->
{ name: {number of employees: {$eq: "100", $lt: "1000"}}}

<!-- 9. Ordene todas as empresas pelo preço de ipo de forma descendente. -->
{ ip: {$lte: price}}

<!-- 10. Recupere as 10 empresas com mais funcionários, ordenado pelo number of employees. -->
{ number of employees: {name: {$eq: 10, {gt: }}}

<!-- 11. Todas as empresas constituídas no segundo semestre do ano. Limite sua pesquisa a 1000 empresas. -->
{name: {$gte: "2015",  { founded_year {$lt: "2000", acquisition {$gte: "10.000.00}}

<!-- 12. Todas as empresas fundadas antes de 2000 que tenham um valor de aquisição superior a 10.000.000. -->
{ founded_year: {$lt: "2000", acquisition {$gte: "10.000.00"}}

<!-- 13. Todas as empresas adquiridas após 2015, ordenam pelo valor de aquisição e recuperam apenas os campos name e acquisition. -->
{ name: { founded_year: {$gt: "2015", acquisition {$gte: <value>}}}}

<!-- 14. Ordene as empresas por seu founded year, recuperando apenas seu name e founded year. -->
{founded_year: {$all: name}} ????

<!-- 15.Todas as empresas constituídas nos primeiros sete dias do mês, incluindo o sétimo. Classifique-os por seu acquisition price de forma descendente. Limite a pesquisa a 10 documentos. -->

<!-- 16. Todas as empresas da «web» category com mais de 4000 empregados. Classifique-os pela quantidade de funcionários em ordem crescente. -->

<!-- 17. Todas as empresas cujo valor de aquisição seja superior a 10.000.000 e a moeda seja 'EUR'. -->
{acquisition:  {$get: 10.000.00, currency: {$eq: "EUR"}}}


<!-- 18. Todas as empresas adquiridas no primeiro trimestre do ano. Limite a pesquisa a 10 empresas e recupere apenas os campos name e acquisition. -->

<!-- 19. Todas as empresas que foram fundadas entre 2000 e 2010, mas não foram adquiridas antes de 2011. -->
{name: {founded year: {$elemMatch: <2000>, ..., <2010>, deadpooled_year: {$nor: 2011}}}}
