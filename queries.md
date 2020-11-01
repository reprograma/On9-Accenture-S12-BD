1 - query: {name: "Babelgum"}
    project: {name: 1}

2 - query:{number_of_employees: {$gte: 5000}}
    sort: {number_of_employees: 1}
    limit:20

3 - query: {founded_year:{$gte:2000, $lte:2005}}
    project: {name:1, founded_year:1}

4 - query: {$and: [{"ipo.valuation_amount": {$gt: 100000000}}, {founded_year: {$lt: 2010}}]}
    project: {name: 1, ipo: 1}

5 - query:{$and: [{number_of_employees: {$lt: 1000}}, {founded_year: {$lt: 2005}}]}
    sort: {number_of_employees:1}
    limit:10

6 - query: {$ne:[partners]}

7 - query: {category_code : null}

8 - query: {number_of_employees: {$gt:100,$lt:1000}}
    project: {name:1, number_of_employees:1}

9 - sort:{"ipo.valuation_amount": -1}

10 - sort: {"number_of_employees": -1}
     limit: 10

11 - query: {founded_month: {$gt:6}}
     limit: 1000

12 - query: {$and: [{founded_year: {$lt: 2000}}, {"ipo.valuation_amount": {$gt: 10000000}}]}

13 - query: { "acquisition.acquired_year": { $gt: 2015 } }
     project: {name:1 , acquisition: 1}
     sort: {"acquisition.price_amount": -1}
Ps: Nenhuma empresa com essas caracteristicas. 

14 - project: {name:1 , founded_year:1}
     sort: {founded_year:-1}

15 - query: {founded_day:{$lte:7}}
     sort: {"acquisition.price_amount": -1}
     limit:10

16 - query: {$and: [{category_code:"web"}, {number_of_employees:{$gt:4000}}]}
     sort: {number_of_employees:1}

17 - query: { $and: [ { "acquisition.price_amount": { $gt: 10000000 } }, { "acquisition.
     price_currency_code": "EUR" } ] 

18 - query: {"acquisition.acquired_month": {$lte:4}}
     project : {name: 1, acquisition: 1}
     limit: 10

19 - query: {$and:[{founded_year:{$gte:2000, $lte:2010}}, {"acquisition.acquired_year":
     {$gte:2011}}]}
