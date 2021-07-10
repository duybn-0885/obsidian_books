- When read from database, you only read data has been committed
- When write to database, you only write to data has been committed

- No [[Dirty Read]]
- No [[Dirty Write]]


- Usually, database prevents dirty writes by using row-level locks: when a transaction wants to modify a particular object, it must acquire a lock on that object.
- Database prevents dirty read by holding both new value and old value. Only transaction committed, database switch to new value.

