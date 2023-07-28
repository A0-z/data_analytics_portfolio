## Analysis using SQL

1. Show all customer records<br>
`SELECT * FROM customers;`

    

2. Show total number of customers<br>
`SELECT COUNT(*) FROM customers;`

3. Show transactions for Chennai market (market code for chennai is Mark001)<br>
`SELECT * FROM transactions WHERE market_code='Mark001'; `

 

4. Show distinct product codes that were sold in Chennai<br>

   ` SELECT DISTINCT(product_code) FROM transactions WHERE market_code='Mark001'; `

5. Show transactions where currency is US dollars<br>

    `SELECT * FROM transactions WHERE currency='USD'; `

6. Show transactions in 2020<br>

   `SELECT t.* FROM transactions t JOIN date d 
    ON t.order_date=d.date WHERE d.year='2020'; `

7. Show total revenue in year 2020,<br>
`SELECT SUM(t.sales_amount) FROM transactions t JOIN date d 
ON t.order_date=d.date WHERE d.year='2020'; `
  
8. Show total revenue in year 2020, January Month<br>
`SELECT SUM(t.sales_amount) FROM transactions t JOIN date d 
ON t.order_date=d.date WHERE d.year='2020' AND d.month_name='January'; `


9. Show total revenue in year 2020 in Chennai<br>
`SELECT SUM(t.sales_amount) FROM transactions t JOIN date d 
ON t.order_date=d.date WHERE d.year='2020' AND t.market_code='Mark001';`
10. Find garbage values(sales record with no or negative revenue)<br>
`SELECT * FROM transactions WHERE sales_amount<=0;`



