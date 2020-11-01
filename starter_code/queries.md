1. Filter = { name: "Babelgum"}
2. Filter = {number_of_employees:{$gt: 5000}} Limit 20
3. Filter = {founded_year:{$gt:2000, $lte:2005}} e Project: {name: 1, founded_year:1}
4. Filter = {$and:[{"acquisition.price_amount": {$gt:1000000000}},{founded_year:{$lt:2010}}]} e Project = {name: 1, ipo:1}
5. Filter = {$and:[{number_of_employees:{$lt:1000}},{founded_year:{$lt:2005}}]} e Project = {name: 1, founded_year:1}
6. Filter = {name: {$eq:"Partners"}} (obs.: não havia empresa com o nome partners ou Partners)
7. Filter = {category_code: {$eq: null}}
8. Filter = {number_of_employees:{$gte:100, $lt:1000}} e Project = {name: 1, number_of_employees:1}