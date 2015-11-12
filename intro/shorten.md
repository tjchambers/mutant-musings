# Keep your methods short, and your code shorter

Mutant works best when you follow best practices in software development. How can mutation testing be *helped* by following good dev practice?

Mutant mutates code. So less code, less potential mutations. And less code to read, write, maintain etc. They go hand-in-hand.

Mutant (*currently*) mutates instance and class methods only. All other code outside defined methods (requires, DSL, extends, includes, etc.) are NOT mutated. So taking advantage of DSL replacement for inline methods avoids mutations, and in most cases makes intent clear in a much more succint manner.

And because of the quadratic effect of mutating multiple code lines within a single method it pays to reduce the LOC of your methods. This is good practice anyway, and can significantly drop the number of potential mutation combinations for a given class/module.

So split your long methods into shorter ones (where it makes sense) and benefit from the more targetted mutations.
