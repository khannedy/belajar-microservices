# Monolith

```puml

node "Browser" as browser
node "Nginx" as nginx
node "Web Server" as webserver {
    node "Web Application" as webapplication {
        component "Customer"
        component "Accounting"
        component "Product"
        component "... Service"
    }
}
database "MySQL" as mysql

browser <-right-> nginx
nginx <--> webapplication
webapplication <--> mysql

```
