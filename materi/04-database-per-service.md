# Database per Service

```puml

node "ECommerce" as ecommerce
node "Product Service" as product
node "Merchant Service" as merchant
database "PostgreSQL" as postgresql
database "MySQL" as mysql

ecommerce --> product
ecommerce --> merchant
merchant --> postgresql
product --> mysql

```
