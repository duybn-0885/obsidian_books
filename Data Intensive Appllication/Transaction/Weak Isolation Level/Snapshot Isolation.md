- Nonrepeatable read

Alice has $1000 saving split into 2 accounts. She transfer $100 from first account -> second account

Some situations cannot tolerate such temporary inconsistency

- Backup
- Analytic queris

-> Snapshot isolation

Like [[Read Committed]], snapshot isolation use write locks to prevent dirty writes.

To implement, database must potentially keep several different commited versions of and object. This technique is know as multi-version concurrency control (MVCC)
