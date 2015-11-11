# Lock it like you mean it

Mutant runs fastest when you give it all your processor cores. However because it is running your tests in parallel - potentially against the same database using the same method (i.e. DB requests) at the same time, you may experience lock conflicts.

When you get a non-deterministic database lock conflict, it fails your test in a way that mutant misinterprets as a potential bug. In any case your mutant run is not usable at that point, because you didn't get a legitimate pass-or-fail on the spec.

## Example

```
Insert example here

```
## Remedy/Action

I was not able in MySQL to *totally* eliminate lock conflicts, but I was able to get them down to about 1% of my overall suite. I use InnoDB as my engine and changed the tx_isolation setting to `READ-COMMITTED`. This permitted my tests to read any data without being locked by a potential write trying to maintain a consistent database perspective, and it also greatly reduces the real estate locked by MySQL on a pending update.

## TakeAway

- Plan for potential lock conflicts if you are updating the database in your tests
- If you are running with multiple cores and find lock conflicts, slow down and run with just one worker (-j1) [I do that as a fallback only when it happens].
- Consider changing your transaction isolation settings to minimize lock conflicts if that works for your environment
