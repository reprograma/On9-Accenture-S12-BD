01_ Todas as empresas cujo nome corresponde a 'Babelgum'. Recupere apenas o campo name.
	filter { name: "Babelgum"}
	project { name: 1 }
	

02_ Todas as empresas com mais de 5.000 funcionários. Limite a pesquisa a 20 empresas e classifique-as por number of employees.	
	filter { number_of_employees: { $gt: 5000 } }
	sort { number_of_employees: 1 }
	limit 20


03_ Todas as empresas fundadas entre 2000 e 2005, ambos os anos incluídos. Recupere apenas os campos name e founded_year.	
	filter { founded_year: { $gte:2000,  $lte:2005}}
	project {name: 1, founded_year:1}


04_ Todas as empresas que tiveram um Valor de Avaliação superior a 100.000.000 e foram fundadas antes de 2010. Recupere apenas os campos name e ipo.	
	filter { $and: [ {"ipo.valuation_amount": {$gt:100000000}}, {founded_year:  {$lt: 2010}} ] }
	project {name: 1, ipo:1}


05_ Todas as empresas que tenham menos de 1000 funcionários e tenham sido fundadas antes de 2005. Ordene-as pelo número de funcionários e limite a pesquisa a 10 empresas.	
	filter { $and: [ {number_of_employees: {$lt: 1000}}, {founded_year:  {$lt: 2005}} ] }
	sort { number_of_employees: 1 }
	limit 10


06_ Todas as empresas que não incluem o campo partners.	
	filter { $ne: partners}


07_ Todas as empresas que possuem um tipo nulo de valor no campo category_code.
	
	filter {category_code: null}


08_ Todas as empresas que têm pelo menos 100 funcionários, mas menos de 1000. Recupere apenas os campos name e number of employees.
	
	filter { number_of_employees: { $gte: 100,  $lt: 1000}}
	project {name: 1, number_of_employees: 1}


09_ Ordene todas as empresas pelo preço de ipo de forma descendente.	
	sort { "ipo.valuation_amount": -1 }


10_ Recupere as 10 empresas com mais funcionários, ordenado pelo number of employees.	
	sort { number_of_employees: -1 }
	limit 10


11_ Todas as empresas constituídas no segundo semestre do ano. Limite sua pesquisa a 1000 empresas.	
	filter {founded_month: { $gte: 6 } }
	limit 1000


12_ Todas as empresas fundadas antes de 2000 que tenham um valor de aquisição superior a 10.000.000.	
	filter { $and: [ { "acquisition.price_amount": { $gt: 10000000 } }, {founded_year: {$lt: 2000} } ] }


13_ Todas as empresas adquiridas após 2015, ordenam pelo valor de aquisição e recuperam apenas os campos name e acquisition.	
	filter {"acquisition.acquired_year": {$gt: 2015} }
	project {name: 1, acquisition: 1}
	sort { "acquisition.price_amount": -1 }

	
14_ Ordene as empresas por seu founded year, recuperando apenas seu name e founded year.	
	project {name: 1, founded_year: 1}
	sort { founded_year: -1 }


15_ Todas as empresas constituídas nos primeiros sete dias do mês, incluindo o sétimo. Classifique-os por seu acquisition price de forma descendente. Limite a pesquisa a 10 documentos.	
	filter {founded_day: { $lte: 7 } }
	sort { "acquisition.price_amount": -1 }
	limit 10


16_ Todas as empresas da «web» category com mais de 4000 empregados. Classifique-os pela quantidade de funcionários em ordem crescente.	
	filter { $and: [ { category_code: "web" }, {number_of_employees: { $gt: 4000 } } ] }
	sort {number_of_employees: 1 }


17_ Todas as empresas cujo valor de aquisição seja superior a 10.000.000 e a moeda seja 'EUR'.	
	filter { $and: [ { "acquisition.price_amount": { $gt: 10000000 } }, {"acquisition.price_currency_code": "EUR" } ] }


18_ Todas as empresas adquiridas no primeiro trimestre do ano. Limite a pesquisa a 10 empresas e recupere apenas os campos name e acquisition.	
	filter {"acquisition.acquired_month": { $lte: 3 } }
	project {name: 1, acquisition: 1}
	limit 10


19_ Todas as empresas que foram fundadas entre 2000 e 2010, mas não foram adquiridas antes de 2011.	
	filter { $and: [ {founded_year: { $gte: 2000, $lte: 2010}}, {"acquisition.acquired_year": { $gte: 2011}} ] }

