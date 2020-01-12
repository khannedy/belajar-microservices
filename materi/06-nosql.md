# NoSQL

```puml

node "Product Service" as product 
node "Catalog Service" as catalog
node "Order Service" as order
node "Member Service" as member
node "Activity Service" as activity

database "MongoDB" as mongodb
database "Elasticsearch" as elasticsearch
database "PostgreSQL" as postgresql
database "Neo4J" as neo4j
database "InfluxDB" as influxdb

product --> mongodb
catalog --> elasticsearch
order --> postgresql
member --> neo4j
activity --> influxdb

```
