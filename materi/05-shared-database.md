# Shared Database

```puml

node "ECommerce" as ecommerce
node "Order Service" as order
node "Merchant Dashboard" as merchant
database "MySQL" as mysql

ecommerce -right-> order
order --> mysql
merchant --> mysql

```
