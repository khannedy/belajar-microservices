# Remote Procedure Invocation

```puml

node "Order Service" as order
node "Product Service" as product
database "Posgresql" as postgresql 
database "Mongodb" as mongodb

note left of order
Butuh Data
Product
end note 

order --> postgresql
product --> mongodb
order -right-> product : RESTful API

```
