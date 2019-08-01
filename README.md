# sql-imp-queries
## create table 
```sql
create table GuestList(
[GueastId] int not null IDENTITY(1,1) PRIMARY KEY,
[Name] varchar (50) not null,
[Email] varchar (50) not null,
[Phone] int not null,
WillAttend bit

);

```
