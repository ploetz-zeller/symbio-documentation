# Configuration
## Before start
After successful installation and connection of the ID Provider Service,
a table with 2 columns is created in the ID Provider database. In this
table, a new entry should be added for each consuming symbio instance.

Simply use the following statement and replace the colored fields with
your data:
```sql
insert into `enter ID Provider Name`.Subscribers (subscriber, token)
values (NEWID (),`enter desired token name`)
```
Now note the name of your token from the database and the URL to your ID
provider services. For example, if you install the service under
``"IDProvider"`` and create the token named ``"myToken"``, the script would look
like this:

```sql
insert into IDProvider.Subscribers (subscriber, token) values (NEWID
(),'myToken')
```
URL = ``Url of deployed app service``

Token = `myToken`
