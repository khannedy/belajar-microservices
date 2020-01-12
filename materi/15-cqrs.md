# Command Query Responsibility Segregation

```puml

actor "Client" as client
node "Product Service" as product {
    component "Create, Read, Update Delete" as crud
}
database "MySQL" as mysql

client <--> crud
crud <--> mysql

```

```puml

actor "Client" as client
node "Product Service" as product {
    component "Command" as command
    component "Query" as query
}
database "MySQL" as mysql
database "Elasticsearch" as elasticsearch

client --> command
client <-- query
command --> mysql
command --> elasticsearch
query <-- elasticsearch

```

```puml

actor "Client" as client
node "Product Service" as product {
    component "Command" as command
}
node "Product Search Service" as search {
    component "Query" as query
    component "Consumer" as consumer
}
database "MySQL" as mysql
database "Elasticsearch" as elasticsearch
queue "Message Broker" as messagebroker {
    file "Product Event" as productEvent
}

client --> command
client <-- query
command --> mysql
command --> productEvent
consumer <-- productEvent
consumer --> elasticsearch
query <-- elasticsearch

```
