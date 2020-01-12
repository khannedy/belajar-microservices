# Messaging

```puml

node "Order Service" as order
node "Email Service" as email
node "SMS Service" as sms
node "Finance Service" as finance
node "Report Service" as report
database "Postgresql" as postgresql

note left of order
Butuh Ngirim ke
Email, SMS, FInance
dan Report
end note

order --> postgresql

```

```puml

node "Order Service" as order
node "Email Service" as email
node "SMS Service" as sms
node "Finance Service" as finance
node "Report Service" as report
database "Postgresql" as postgresql

note left of order
Butuh Ngirim ke
Email, SMS, FInance
dan Report
end note

order -> postgresql
order --> sms
order --> email
order --> finance
order --> report

```

```puml

node "Order Service" as order
node "Email Service" as email
node "SMS Service" as sms
node "Finance Service" as finance
node "Report Service" as report
database "Postgresql" as postgresql
queue "Message Broker" {
    file "Email" as emailEvent 
    file "SMS" as smsEvent 
    file "Order" as orderEvent 
}

note left of order
Butuh Ngirim ke
Email, SMS, FInance
dan Report
end note

order -> postgresql
order --> smsEvent
order --> emailEvent
order --> orderEvent

smsEvent --> sms
emailEvent --> email
orderEvent --> finance
orderEvent --> report

```
