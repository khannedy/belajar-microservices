# Microservices

```puml

node "Browser" as browser
node "Nginx" as nginx
node "Customer Service" as customer
node "Accounting Service" as accounting
node "Product Service" as product
node "... Service" as other
database "Postgresql" as postgresql
database "Mysql" as mysql
database "Oracle" as oracle
database "Mongodb" as mongodb

browser --> nginx
nginx --> customer
nginx --> accounting
nginx --> product
nginx --> other
customer --> postgresql
accounting --> mysql
product --> oracle
other --> mongodb

```
