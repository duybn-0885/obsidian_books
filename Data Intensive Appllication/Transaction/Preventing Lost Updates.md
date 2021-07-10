- We only discussed [[Dirty Write]] so far.
- 2 read-modify-write cycle can make on of them lost datas.

### Atomic Write Operation
Many databases provide atomic update operations, remove the need to implement read-modify-write cycles

`UPDATE counters SET value = value + 1 WHERE key = 'foo';`

### Explicit Locking
Need to lock row and check
```
BEGIN TRANSACTION;
SELECT * FROM figures
WHERE name = 'robot' AND game_id = 222
FOR UPDATE;
-- Check whether move is valid, then update the position
-- of the piece that was returned by the previous SELECT.
UPDATE figures SET position = 'c4' WHERE id = 1234;
COMMIT;
```

This works but to get it right, you need to carefully think about your  application logic. It's easy to forget add a necessary lock somewhere in the code -> introduce race condition.


### Automatically detecting lost updates
- Less error-prone
- Does not require force app

### Compare and set
```
UPDATE wiki_pages SET content = 'new content'
WHERE id = 1234 AND content = 'old content';
```

### Conflict resolutin and replication

- Allow concurrent writes to create several conflicting versions of a value  -> use application code to resolve and merge these versions after the fact.

- Two ways:
- Atomic operations
- Last write wins -> prone to lost updates -> but is default in many database.