1. 

filter : { name: "Babelgum"}
project : {name: 1, _id: 0}

2. 

filter : { number_of_employees : { $gt: 5000} }
sort : {number_of_employees : 1}
limit : 20

3. 

filter : { $and: [ {founded_year: { $gte: 2000} }, {founded_year: {$lte: 2005}} ]  }
project : {name: 1, founded_year: 1, _id: 0}

4. 

filter : { $and: [ {"ipo.valuation_amount": { $gt: 100000000} }, {founded_year: {$lt: 2010}} ]  }
project :  {name: 1, ipo: 1, _id: 0}

5. 

filter : { $and: [ { number_of_employees : { $lt: 1000} }, {founded_year: {$lt: 2005}} ]  }
sort : {number_of_employees: 1}
limit : 10

6. 

filter: {$ne : partners}

7. 

filter: {category_code: null}

8. 

filter : { $and: [ { number_of_employees : { $gte: 100} }, { number_of_employees : { $lt: 1000} } ]  }

project: {name: 1, number_of_employees: 1, _id: 0}

9. 

sort : { "ipo.valuation_amount": -1 }

10. 

sort : { number_of_employees: -1 }
limit : 10

11. 

filter : {founded_month: {$gte:7}}
limit : 1000

12. 

filter : {$and : [{founded_year: {$lt:2000}} , {"acquisition.price_amount": {$gt:10000000}}]}

13. 

filter : {$and : [{"acquisition.acquired_year": {$gt:2015}}]}
project : {name: 1, _id: 0, acquisition: 1}
sort : {"acquisition.price_amount": 1}

14. 

project : {name: 1, _id: 0, founded_year: 1}
sort : {founded_year: 1}

15. 

filter : {$and: [{founded_day: {$lte: 7}}]}
sort : {"acquisition.price_amount": -1}
limit : 10

16. 

filter : {$and: [{category_code: "web"}, {number_of_employees:{$gt:4000}}]}
sort : {number_of_employees: 1}

17. 

filter : {$and: [{"acquisition.price_currency_code": "EUR"}, {"acquisition.price_amount":{$gt:10000000}}]}

18. 

filter :  {"acquisition.acquired_month":{$lte: 4}}
project : {name: 1, _id: 0, acquisition:1}
limit : 10

19. 

filter : { $and: [ {founded_year: { $gt: 2000} }, {founded_year: {$lt: 2010}}, {"acquisition.acquired_year": {$gt:2011}} ] }