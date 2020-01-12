# Backend for Frontend

```puml

actor "Website" as website
actor "Mobile" as mobile
actor "Third Party" as thirdparty

rectangle <<ECommerce>> {
    node "Backend API Gateway" as api
    rectangle <<Internal Microservices>> {
        node "Member Service" as member
        node "Product Service" as product
        node "Cart Service" as cart
        node "Order Service" as order
    }
}

website --> api
mobile --> api
thirdparty --> api
api --> member
api --> product
api --> cart
api --> order

```

```puml

actor "Website" as website
actor "Mobile" as mobile
actor "Third Party" as thirdparty

rectangle <<ECommerce>> {
    node "Website API Gateway" as webapi
    node "Mobile API Gateway" as mobileapi
    node "Third Party API Gateway" as thirdpartyapi
    rectangle <<Internal Microservices>> {
        node "Member Service" as member
        node "Product Service" as product
        node "Cart Service" as cart
        node "Order Service" as order
    }
}

website --> webapi
mobile --> mobileapi
thirdparty --> thirdpartyapi

webapi --> member
webapi --> product
webapi --> cart
webapi --> order

mobileapi --> member #green
mobileapi --> product #green
mobileapi --> cart #green
mobileapi --> order #green

thirdpartyapi --> member #blue
thirdpartyapi --> product #blue
thirdpartyapi --> cart #blue
thirdpartyapi --> order #blue

```
