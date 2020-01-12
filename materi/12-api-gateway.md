# API Gateway

```puml

actor "User" as user
cloud "Internet" as internet

rectangle <<ECommerce>> {
    node "Member Service" as member
    node "Product Service" as product
    node "Cart Service" as cart
    node "Order Service" as order
}

user --> internet
internet --> member
internet --> product
internet --> cart
internet --> order

```

```puml

actor "User" as user
cloud "Internet" as internet

rectangle <<ECommerce>> {
    node "API Gateway" as api
    node "Member Service" as member
    node "Product Service" as product
    node "Cart Service" as cart
    node "Order Service" as order
}

user -right-> internet
internet --> api
api --> member
api --> product
api --> cart
api --> order

```
