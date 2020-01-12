# Authentication and Authorization

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

```puml

actor "User" as user
cloud "Internet" as internet

rectangle <<ECommerce>> {
    node "API Gateway" as api
    node "Member Service" as member
    node "Product Service" as product
    node "Cart Service" as cart
    node "Order Service" as order
    node "Auth Service" as auth
}

user -right-> internet
internet --> api
api --> member
api --> product
api --> cart
api --> order
api -right-> auth

```

```puml

actor "User" as user
cloud "Internet" as internet

rectangle <<ECommerce>> {
    node "API Gateway" as api
    node "Member Service" as member {
        component "Middleware" as membermiddleware
    }
    node "Product Service" as product {
        component "Middleware" as productmiddleware
    }
    node "Cart Service" as cart {
        component "Middleware" as cartmiddleware
    }
    node "Order Service" as order {
        component "Middleware" as ordermiddleware
    }
    node "Auth Service" as auth
}

user -right-> internet
internet --> api
api --> member 
api --> product 
api --> cart 
api --> order
api -right-> auth

membermiddleware -up-> auth #blue
productmiddleware -up-> auth #blue
ordermiddleware -up-> auth #blue
cartmiddleware -up-> auth #blue

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
    node "Auth Service" as auth
}

user -right-> internet
internet --> api
api --> member #blue : Request + Auth Data 
api --> product #blue : Request + Auth Data
api --> cart #blue : Request + Auth Data
api --> order #blue : Request + Auth Data
api -right-> auth : Check Session

```
