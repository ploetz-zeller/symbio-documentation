---
uid: uniqueid-install-create-token
---
# Create Connection Token

Navigate into your Provider Databse and run following SQL-Command

```sql
insert into symbioid._Subscribers (Subscriber, Token) 
values (NEWID(), [YourTokenName]) 
```    

To integrate the service in Symbio, you can refer to the following documents
- [Symbio Service UniqueId Admin](config-before-start.md)
- [Symbio Service UniqueId Manual](manual-how-to-use.md)