# How Mutant Works

Frankly, I don't know. And the beauty is I (and You), don't need to care. Because it just does.

So the real question is ... *what does it do?*

## What Mutant Does

The bottom-line is that the mutant gem does nothing you can't do yourself. It just does two things:

- Alters your code
- Runs the tests for the altered code

That's it. Pretty simple. You could do that yourself. Just not as fast or as well.

It's not my intent to tell you how to use mutant - there are other much better resources for that.

So I will dive a bit further into some of the critical things you need to appreciate to take advantage of mutant.

## Code MUTATION

I said mutant alters your code. Here is a bit more about that.

Kinds of mutations:

- Substitutions
	It swaps out pieces of your code, always adhering to valid Ruby syntax, with alternate values that just might surface a gap in your test suite, or an unnecessary piece of code.
- Eliminations
	Mutant also removes pieces of your code - again in a Ruby-valid manner - and then runs your tests to see that they break.

SO what is the purpose?

The purpose of mutation testing is to prove that EVERY SINGLE PIECE OF CODE you have is needed to satisfy the objective of your application. The way that is done is by altering and stripping away the pieces and noting if your tests fail. They should. Because if they *don't* fail then either a) your tests are not completely asserting the expected behavior of the code, or b) the code removed or changed is unnecessary.

I will tell you when I first started I thought I was going to have to add a lot of tests. Surprisingly NO! What I discovered was that I needed to be more strict about my expectations, and I also found lots of places where it turned out I had code I didn't need!

So when you are starting out on this mutation journey, be open to the fact that mutation testing will *suggest* both test adjustments AND possible unnecessary code. Ask yourself on each alive mutation - do I *NEED* this code, and if I do how do I make that snippet of code reflect in my tests.


