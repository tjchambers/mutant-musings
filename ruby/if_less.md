# IfLess Coverage

Ruby gives us a wonderful shorthand for if or unless that allows us to put the code all on one line. And
if you are looking to have 100% test coverage by line you may be fooled into thinking that
your code is covered because the line is traversed by your specs.

Don't be fooled.

Adding an if or unless on the end of the line can make the beginning of the line NOT be processed at all by your specifications. But that won't be easily evident in your IDE, or on CodeClimate. All it means is that at least a portion of your if statement was processed.

## Example

Real Code
```
@cminfact[col_indx] = AceFitness::CLASSFACTOR * minimum if minimum >= SLIGHTLY_AGREE
```

Mutant (unparsed then reparsed) View of that line
```
    if minimum >= SLIGHTLY_AGREE
        @cminfact[col_indx] = AceFitness::CLASSFACTOR * minimum
      end
```

Mutation (one of many):
```
   if (minimum >= SLIGHTLY_AGREE)
-    @cminfact[col_indx] = (AceFitness::CLASSFACTOR * minimum)
+    @cminfact[nil] = (AceFitness::CLASSFACTOR * minimum)
   end
```

## Remedy

In the above example my specs always made the if result == FALSE, therefore the early part of my line was never executed. And mutant played havoc with various mutations, of a line I *believed* was executed. The fact that my array could NEVER have a `[nil]` was for me a  giveaway that the line was not executed. Rearranging it into the *mutant view* and running my RSpec specs with coverage PROVED that I did not ever have a path that resulted in traversing that statement.


## Takeaway

- Using If or unless in a one-liner shorthand is fine in Ruby, but be prepared for Mutant to surface the fact that only some of that line is ever covered by your tests
