1. Filter = { name: "Babelgum"}
2. Filter = {number_of_employees:{$gt: 5000}} e Limit = 20
3. Filter = {founded_year:{$gt:2000, $lte:2005}} e Project: {name: 1, founded_year:1}
4. Filter = {$and:[{"acquisition.price_amount": {$gt:1000000000}},{founded_year:{$lt:2010}}]} e Project = {name: 1, ipo:1}
5. Filter = {$and:[{number_of_employees:{$lt:1000}},{founded_year:{$lt:2005}}]} e Project = {name: 1, founded_year:1}
6. Filter = {name: {$eq:"Partners"}} (obs.: não havia empresa com o nome partners ou Partners)
7. Filter = {category_code: {$eq: null}}
8. Filter = {number_of_employees:{$gte:100, $lt:1000}} e Project = {name: 1, number_of_employees:1}
9. Sort = {ipo: -1}
10. Filter = {number_of_employees: {$ne: null, $gt: 0}} e Sort = {number_of_employees: -1} e Limit = 10
11. Filter = {founded_month: {$ne: null, $gte: 7 }} e Limit = 1000
12. Filter = {$and:[{"acquisitions.price_amount":{$gt:10000000}},{founded_year:{$ne: null, $lt: 2000}}]}
13. Filter = {"acquisitions.acquired_year": {$lt: 2015}} e Project = {name: 1, acquisitions:1} e Sort = {"acquisitions.price_amount": -1} (professora não há maior só menor que 2015)
14. Filter = em branco e Project = {name: 1, founded_year:1} e Sort = {founded_year: 1}
15. Filter = {founded_day: {$ne: null, $lte:10}} e Sort = {"acquisitions.price_amount": -1} e Limit = 10 (professora não havia na base menor ou igual aos primeiros 7 dias e por isso coloquei 10)
16. Filter = {$and:[{number_of_employees:{$gt:4000}},{category_code:{$eq:"web"}}]} e Sort = {number_of_employees: 1}
17. Filter = {$and:[{"acquisitions.acquired_month":{$lt:10000000}},{"acquisitions.price_currency_code":{$eq:"EUR"}}]} (Alterei para que seja inferior a 10.000.000 porque na base não tinha superior com a moeda EUR)
18. Filter = {"acquisitions.acquired_month":{$gte:1, $lte:3}} e Project = {name: 1, acquisitions:1}
19. {$and:[{founded_year:{$gte:2000, $lt: 2010}},{"acquisitions.acquired_year":{$gte:2011}}]}