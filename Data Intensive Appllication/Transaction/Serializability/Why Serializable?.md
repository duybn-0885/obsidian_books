Sad situation:
- Isolation level is hard to understand, and inconsistently implemented in different databases
- When look at code, it is difficult to tell whether it is safe to run a particular isolation level
- No good tools to help us detect race condition

=> Serializable isolation

Three ways to implement it

- [[Actual Serial Excution]]
- [[Two Phase Locking]]
- [[Serilizable Snapshot Isolation]]