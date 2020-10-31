1. Todas as empresas cujo nome corresponde a 'Babelgum'. Recupere apenas o campo `name`.

  - ** `query` **: { name: "Babelgum" }
  - ** `projeção` **: { name: 1, _id: 0 }

2. Todas as empresas com mais de 5.000 funcionários. Limite a pesquisa a 20 empresas e classifique-as por `number of employees`.

  - ** `query` **: { number_of_employees: { $gt: 5000 } }
  - ** `sort` **: { name: 1 }
  - ** `limit` **: 20

3. Todas as empresas fundadas entre 2000 e 2005, ambos os anos incluídos. Recupere apenas os campos `name` e` founded_year`.

  - ** `query` **: { founded_year: { $gte: 2000, $lte: 2005 } }
  - ** `projeção` **: { name: 1, founded_year: 1, _id: 0 }

4. Todas as empresas que tiveram um Valor de Avaliação superior a 100.000.000 e foram fundadas antes de 2010. Recupere apenas os campos `name` e `ipo`.

  - ** `query` **: { $and: [ { "ipo.valuation_amount": { $gt: 100000000 } }, { founded_year: { $lt: 2010 } } ] }
  - ** `projeção` **: { name: 1, ipo: 1, _id: 0 }

5. Todas as empresas que tenham menos de 1000 funcionários e tenham sido fundadas antes de 2005. Ordene-as pelo número de funcionários e limite a pesquisa a 10 empresas.

  - ** `query` **: { $and: [ { number_of_employees: { $lt: 1000} }, { founded_year: { $lt: 2005 } } ] }
  - ** `sort` **: { number_of_employees: 1 }
  - ** `limit` **: 10

6. Todas as empresas que não incluem o campo `partners`.

  - ** `query` **: { $ne: partners }

7. Todas as empresas que possuem um tipo nulo de valor no campo `category_code`.

  - ** `query` **: { category_code: null }

8. Todas as empresas que têm pelo menos 100 funcionários, mas menos de 1000. Recupere apenas os campos `name` e `number of employees`.

  - ** `query` **: { number_of_employees: { $gte: 100, $lt: 1000 } }
  - ** `projeção` **: { name: 1, number_of_employees: 1, _id: 0 }

9.  Ordene todas as empresas pelo preço de `ipo` de forma descendente.

- ** `sort` **: { "ipo.valuation_amount": -1 }

10. Recupere as 10 empresas com mais funcionários, ordenado pelo `number of employees`

  - ** `sort` **: { number_of_employees: -1 }
  - ** `limit` **: 10

11. Todas as empresas constituídas no segundo semestre do ano. Limite sua pesquisa a 1000 empresas.

  - ** `query` **: { founded_month: { $gt: 6 } }
  - ** `limit` **: 1000

12. Todas as empresas fundadas antes de 2000 que tenham um valor de aquisição superior a 10.000.000

  - ** `query` **: { $and : [ { founded_year: { $lt:2000 } }, { "acquisition.price_amount": { $gt:10000000 } } ] }

13. Todas as empresas adquiridas após 2015, ordenam pelo valor de aquisição e recuperam apenas os campos `name` e `acquisition`.

  - ** `query` **: { "acquisition.acquired_year": { $gt: 2015 } }
  - ** `projeção` **: { name: 1, acquisition: 1, _id: 0 }
  - ** `sort` **: { "acquisition.price_amount": -1 }

Obs.: Na consulta pelo ano 2015 não retornou as empresas, mas trocando para 2013 ou 2014, por exemplo, ele retorna as empresas.

14. Ordene as empresas por seu `founded year`, recuperando apenas seu` name` e `founded year`.

  - ** `projeção` **: { name: 1, founded_year: 1, _id: 0 }
  - ** `sort` **: { founded_year: -1 }

15. Todas as empresas constituídas nos primeiros sete dias do mês, incluindo o sétimo. Classifique-os por seu `acquisition price` de forma descendente. Limite a pesquisa a 10 documentos.

  - ** `query` **: { founded_day: { $lte: 7 } }
  - ** `sort` **: { "acquisition.price_amount": -1 }
  - ** `limit` **: 10

16. Todas as empresas da «web» `category` com mais de 4000 empregados. Classifique-os pela quantidade de funcionários em ordem crescente.

  - ** `query` **: { $and: [ { category_code: "web" }, { number_of_employees: { $gt:4000 } } ] }
  - ** `sort` **: { number_of_employees: 1 }

17. Todas as empresas cujo valor de aquisição seja superior a 10.000.000 e a moeda seja 'EUR'.

  - ** `query` **: { $and: [ { "acquisition.price_amount": { $gt: 10000000 } }, { "acquisition.price_currency_code": "EUR" } ] }

18. Todas as empresas adquiridas no primeiro trimestre do ano. Limite a pesquisa a 10 empresas e recupere apenas os campos `name` e `acquisition`.

  - ** `query` **: { "acquisition.acquired_month": { $lte: 3 } }
  - ** `projeção` **: { name: 1, acquisition: 1, _id: 0 }
  - ** `limit` **: 10

19. Todas as empresas que foram fundadas entre 2000 e 2010, mas não foram adquiridas antes de 2011.

  - ** `query` **: { $and: [ { founded_year: { $gte: 2000, $lte: 2010 } }, { "acquisition.acquired_year": { $gte: 2011 } } ] }

