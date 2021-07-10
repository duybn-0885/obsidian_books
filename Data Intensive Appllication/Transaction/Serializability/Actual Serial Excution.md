- Execute only one transaction at a time, on a single thread
- Throughput is limited to single CPU core

-> Need a store procedures or by using interactive transaction to do the job
- If use interactive transaction, a lot of time is spent in network communication -> throughput would be dreadful.

Pros and cons of store procedures:
- Pros
	+ Each database has its own language for stored procedure.
	+ Code running in a database is difficult to manage: compared to an application server, it's hard to debug, more awkward to keep in version
	+ A database is often much more performance-sensitive then application server



Summary:
- Query need fast
- Query write must low
- Active data set can fit in memory