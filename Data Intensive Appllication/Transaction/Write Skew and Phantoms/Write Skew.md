- Alice and Bob are on-call doctors -> They all feel sick -> They request leave at same time -> Is snapshot isolation -> they are allowed for leaving

=> **Write Skew**

Write Skew can be thinked as a generalization of the lost update problem.


**Pattern**:
1. SELECT query checks whether some requirements is satisfied
2. Depending on the results of the first query, the application codes decide to continue
3. If the applications decide to go ahead, it make a writes to the database and commit the transaction


Write in one transaction change the results of search query in another transaction, is called a phantom.

[[Snapshot Isolation]] avoid phantoms in read-only queries, but in read-write transactions , phantoms can be happend.



