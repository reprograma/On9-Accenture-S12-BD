1-

    filter {name: 'Babelgum'}
    project {name: 1} 

2-
    filter {number_of_employees: { $gt: 5000}}
    sort {number_of_employees: 1}
    limit 20

3-
    filter  {founded_year: { $gte: 2000, $lte: 2005}}
    project {name:1, founded_year:1} 

4-
    filter { $and: [ {"ipo.valuation_amount": {$gt:100000000}}, {founded_year:  {$lt: 2010}} ] }
    project {name: 1, ipo: 1 }

5-
    filter { $and: [ {number_of_employees: {$lt: 1000}}, {founded_year:  {$lt: 2005}} ] }
    sort {number_of_employees: 1}
    limit 10

6 -
    filter {partners: {$exists: false}}

7-
    filter {category_code: null}

8-
    filter {number_of_employees: { $gte: 100, $lt: 1000}}
    project {name:1, number_of_employees: 1}

9-
    sort {"ipo.valuation_amount": -1}

10 - 
    sort {number_of_employees:-1}
    limit 10

11-
    filter {founded_month:{$gt: 6}}
    limit 1000

12- 
    filter {$and: [{founded_year:{$lt: 2000}},{"ipo.valuation_amount": {$gt: 10000000}}]}


13-
    filter {founded_year:{$gt: 2015}}
    project {name:1, acquisition:1}
    sort {"acquisition.price_amount": -1}
14-
    project {name: 1, founded_year: 1}
    sort {founded_year: -1}
    
15-
    filter {founded_day: {$lte: 7}}
    sort { {"acquisition.price_amount":-1}}

16-
    filter {$and: [{category_code: "web"}, {number_of_employees: {$gt: 4000}}]}
    sort {number_of_employees:1}

17-
    filter {$and: [{"acquisitions.price_amount":{ $gt: 10000000}}, { "ipo.valuation_currency_code": "EUR"}]}


18-
    filter: {founded_month:{$lte:3}}
    project: {name:1, acquisition:1}

19 - 
    filter: {$and:[{founded_year:{$gte:2000, $lte:2010}}, {"acquisition.acquired_year":{$gte:2011}}]}
