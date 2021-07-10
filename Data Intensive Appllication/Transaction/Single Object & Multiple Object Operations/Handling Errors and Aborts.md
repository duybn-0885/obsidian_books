##### Key Feature
- Need to aborted and safely retry

Some thing need to consider when retry:

- Write 2 times
- Overload and retry -> more overload 
- Side effects(send email , notifications) -> retry -> send 2 times, will be disscused more in [[Two Phase Commit]]
