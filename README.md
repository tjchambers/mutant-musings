# Mutant Musings

In this repo I intend to capture many of the learnings I have accumulated in applying mutation testing and in particular 
the gem [mutant](https://github.com/mbj/mutant), a mutation testing tool targeted at Ruby. 

My current utilization is on a moderately sized Rails application in active production use. This application was developed over 
the past decade and originally in PHP. It has been almost completely re-written and enhanced in Ruby and RoR. It consists
of over 4000+ RSpec tests and 300 ActiveRecord Models. There are over 120,000+ mutations generated for this code base as it stands today.

I myself have been in the software development arena for 45 years, and used mutation testing on other languages in the early 1980's. 
So the concept was not new to me, but the implementation of a powerful tool, alongside a dynamic non-statically-typed language like Ruby, led to some significant
advantages, given I am a newcomer to the Ruby and Rails communities.

## Intent

My goal is to share in a semi-organized fashion my thoughts with examples. By doing so in this forum I invite feedback and questions from the rest of the community and 
of course the originators of the tool. I learn something new about applying this tool to my code almost everyday, and
it has transformed both my tests AND more importantly my coding techniques. You do not have to change your techniques to use this tool to improve the quality of your software,
but the gentle suggestions it makes through mutating your code can be highly illustrative of gaps in your tests and 
better, simpler, shorter, and more confident ways to achieve the purpose of your software. 

Please take a look at my examples, and provide questions and feedback so we can all enjoy higher quality software. Keep in mind that my code may at times not be up to your standards, and the Ruby community is an opinionated one. Try to look past the qaulity of the code and grok the examples in the mutation testing context.

Credits
-------

* [Markus Schirp (mbj)](https://github.com/mbj)
* [Dan Kubb (dkubb)](https://github.com/dkubb)
* [John Backus (backus)](https://github.com/backus)

and so many others who have posed issues and contributed feedback. 
It has been a pleasure to work with them and take advantage of the power of mutation testing. Without them there would be no such tool.
