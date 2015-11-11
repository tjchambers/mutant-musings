# Saving your Points

If you are using database transactions and expect them to roll back at the end of a test, and you are taking advantage of mutant's multiple workers, then occasionally you can expect a SAVEPOINT rollback error.

## Example

```
Insert Example Here
```

## Remedy/Action

To totally eliminate this you must use a single worker (-j1 parameter) which will only create and therefore need to rollback in one concurrent process. I consider this a fail on Rails part, as the problem stems (I believe) from having only one savepoint name = SAVEPOINT1. If multiple savepoints could be designated by process id , then there should not be a name conflict with the savepoints.

Having said that, the rollback process should only roll back what was created by that process, and not touch or interfere with similar data created by a parallel worker. Without eliminating the savepoint name conflict, we won't know if the data would be isolated sufficiently, and this may be dependent on your use of factories and preset test data.

## Takeaway

- Expect savepoint conflicts if you are using transactions and doing default rollbacks after creatiing custom test data
- Fall back to running a single mutant worker to eliminate the issue (-j1)