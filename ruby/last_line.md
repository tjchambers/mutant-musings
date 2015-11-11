# This is the last line I am going to tell you this

Everyone who has done any Ruby knows that the final line in a method determines the return value of the method. Of course you may have return statements elsewhere in a method, but the default is clear.

With mutant in place substituting values like `self` and `nil`, `false` and `true`, your methods may (will?) end up returning something unexpected. If the method is part of a Public API it's pretty easy to test for the return value (you did that right?).

But if the method is a private method, you should be prepared for some strange return values to the calling methods.

## Example

```
Insert Example Here
```


## Remedy/Action

Even if you do not care about the return value from a public method, you may want to explicitly test for it. If you are in the camp that returns `self` to support method chaining, or have a clear expectation of the type and range of the expected returns, just test for it. Even if you anticipate the return value of `nil`, just test for it. You'll be glad you did 'cause it will kill some mutations.


## Takeaway

- Test returned values from Public API's (IMO you should be doing that anyway)
- Be aware of range of mutated return values for private methods.
- If you return nil, you may find it hard to kill mutations that also return ... _nil_