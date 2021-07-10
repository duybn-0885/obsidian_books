- Several transactions are allowed to concurrently read the same object as long as nobody is writing to it. But as soon as anyone wants to write an object, exclusive access is required.

In 2PL, write don't just block other writes, they also block readers and vice versa. It is difference from [[Snapshot Isolation]]]

- Having a lock each object. The lock can either be in shared mode or exclusive mode. The lock is used as follows:
	+ If a transaction wants to read an object, it must acquire the lock in shared mode
	+ If a transaction want to write an object, it must acquire the lock in exclusive mode

Why 2 phases?
- After transaction has acquired the lock, it must continue to hold the lock until the end of the transaction => maybe deadlock

Performance
- Slow

[[Predicate lock]]
[[Index Range Lock]]