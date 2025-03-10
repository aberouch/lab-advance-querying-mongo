![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# Answers

### 1. All the companies that it's name match 'Babelgum'. Retrieve only their `name` field.
** FILTER **    {name: "Babelgum"}
** PROJECT **   {name:1,_id:0}
** SORT **  
** LIMIT **         

### 2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by **number of employees**.
** FILTER **    {number_of_employees:{$gte:5000}}
** PROJECT **   
** SORT **      {number_of_employees:1}
** LIMIT **     20

### 3. All the companies founded between 2000 and 2005, both years included. Retrieve only the `name` and `founded_year` fileds.
** FILTER **    {founded_year:{$gte:2000,$lte:2005}}
** PROJECT **   {name:1,founded_year:1,_id:0}
** SORT **      
** LIMIT **     

### 4. All the companies that had an IPO of more than 100.000.000 and have been founded before 2010. Retrieve only the `name` and `ipo` fields.
** FILTER **    {$and:[{'ipo.valuation_amount':{$gt:100000000}},{founded_year:{$lt:2010}}]}
** PROJECT **   {name:1,ipo:1,_id:0}
** SORT **      
** LIMIT ** 

### 5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.
** FILTER **    {$and:[{'number_of_employees':{$lt:1000}},{'founded_year':{$lt:2005}}]}
** PROJECT **   
** SORT **      {number_of_employees:1}
** LIMIT **     10


### 6. All the companies that don't include the `partners` field.
** FILTER **    {'partners':{$exists:false}}
** PROJECT **   
** SORT **      
** LIMIT **     

### 7. All the companies that have a null type of value on the `category_code` field.
** FILTER **    {'category_code':null}
** PROJECT **   
** SORT **      
** LIMIT **     


### 8. All the companies that have at least 100 employees but less than 1000. Retrieve only the `name` and `number of employees` fields.
** FILTER **    {'number_of_employees':{$lte:1000,$gte:100}}
** PROJECT **   {_id:0,name:1,number_of_employees:1}
** SORT **      
** LIMIT **

### 9. Order all the companies by their IPO price descendently.
** FILTER **    {'acquisition.price_amount':{$gte:0}}
** PROJECT **   
** SORT **      {'acquisition.price_amount': -1}
** LIMIT **


### 10. Retrieve the 10 companies with more employees, order by the `number of employees`
** FILTER **    {'number_of_employees':{$gte:0}}
** PROJECT **   {name: 1, _id:0, number_of_employees:1}
** SORT **      {'number_of_employees': -1}
** LIMIT **     10


### 11. All the companies founded on the second semester of the year. Limit your search to 1000 companies.
** FILTER **    {'founded_month':{$in:[7,8,9,10,11,12]}}
** PROJECT **   {name: 1, _id:0, founded_month:1}
** SORT **      
** LIMIT **     1000

### 12. All the companies that have been 'deadpooled' after the third year.
** FILTER **    
** PROJECT **   
** SORT **      
** LIMIT **     

### 13. All the companies founded before 2000 that have and acquisition amount of more than 10.000.000
** FILTER **    {$and:[{'founded_year':{$lt:2000}},{'acquisition.price_amount':{$gt:10000000}}]}
** PROJECT **   {name:1, acquisition:1, founded_year: 1}
** SORT **      
** LIMIT **  

### 14. All the companies that have been acquired after 2015, order by the acquisition amount, and retrieve only their `name` and `acquisiton` field.
** FILTER **    {'acquisition.acquired_year': {$gt: 2015}}
** PROJECT **   {name: 1,_id: 0,acquisition: 1}
** SORT **      {'acquisition.price_amount': -1}
** LIMIT ** 

### 15. Order the companies by their `founded year`, retrieving only their `name` and `founded year`.
** FILTER **    {founded_year: {$ne: null}}
** PROJECT **   {name: 1,_id: 0,founded_year: 1}
** SORT **      {founded_year: 1}
** LIMIT ** 

### 16. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `aquisition price` descendently. Limit the search to 10 documents.
** FILTER **    {founded_day: {$lte: 7}}
** PROJECT **   
** SORT **      {'acquisition.price_amount': -1}
** LIMIT **     10

### 17. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascendant order.
** FILTER **    {$and: [{ category_code: 'web'},{ number_of_employees: { $gt: 4000 }}]}
** PROJECT **   
** SORT **      {number_of_employees: 1}
** LIMIT **     


### 18. All the companies which their acquisition amount is more than 10.000.000, and currency are 'EUR'.
** FILTER **    {$and:[{'acquisition.price_currency_code':{$eq:"EUR"}},{'acquisition.price_amount':{$gt:10000000}}]}
** PROJECT **   
** SORT **      
** LIMIT **   

### 19. All the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their `name` and `acquisition` fields.

** FILTER **    {'acquisition.acquired_month':{$in:[1,2,3]}}
** PROJECT **   {name:1, acquisition:1}
** SORT **      
** LIMIT **     10


### 20. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.

** FILTER **    {$and: [{ founded_year: { $gte: 2000 }},{ founded_year: { $lte: 2010 }},{ 'acquisition.acquired_year': { $gte: 2011 }}]}
** PROJECT **   
** SORT **      
** LIMIT **     