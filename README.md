# Mutant Musings

In this repo I intend to capture many of the learnings I have accumulated in applying mutation testing and in particular
the gem [mutant](https://github.com/mbj/mutant), a mutation testing tool targeted at Ruby.

My current utilization is on a moderately sized Rails application in active production use. This application was developed over
the past decade and originally in PHP. It has been almost completely re-written and enhanced in Ruby and RoR. It consists
of over 4200+ RSpec tests and 320 ActiveRecord Models. There are over 125,000+ mutations generated for 800+ modules and classes in this code base as it stands today.

I myself have been in the software development arena for 45 years, and used mutation testing on other languages in the early 1980's.
So the concept was not new to me, but the implementation of a powerful tool, alongside a dynamic non-statically-typed language like Ruby, led to some significant
advantages, given I am a newcomer to the Ruby and Rails communities.

## Intent

My goal is to share in a semi-organized fashion my thoughts with examples. By doing so in this forum I invite feedback and questions from the rest of the community and
of course the originators of the tool. I learn something new about applying this tool to my code almost everyday, and
it has transformed both my tests AND more importantly my coding techniques. You do not have to change your techniques to use this tool to improve the quality of your software,
and the gentle suggestions it makes through mutating your code can be highly illustrative of gaps in your tests and
better, simpler, shorter, and more confident ways to achieve the purpose of your software.

Have a look at my examples, provide questions and critiques so we can all enjoy higher quality software. Keep in mind that my code may at times not be up to your standards, and the Ruby community is an opinionated one. Try to look past the quality of the code and grok the examples in the mutation testing context. And remember mutant the tool is evolving daily, and my examples may be become stale. I strive to retire and replace examples, as well as additions, as time permits.

## This is not...
... the place to recommend enhancements or additional mutations, nor to post issues with the mutant gem itself. Please go to [mutant](https://github.com/mbj/mutant) and open a new issue there. You will find a very open and supportive environment, no matter your level of experience.

## Introduction/General

- [How mutant works](intro/workings.md)
- [Keep your methods short, and your code shorter](intro/shorten.md)
- [Assert yourself!!](intro/assertions.md)
- [Truthy or not Truthy is never the question](intro/truthy_falsey.md)
- [Sequence matters](intro/sequence_matters.md)

## Using with Ruby

- [Setting Boundaries](ruby/setting_boundaries.md)
- [Files, Files, everywhere](ruby/files_files.md)
- [IfLess Coverage](ruby/if_less.md)

## Using with Rails

- [Saving your points](rails/saving_your_points.md)
- [Lock it like you mean it](rails/lock_it_like_you_mean_it.md)
- [A Fine Performance](rails/a_fine_performance.md)
- [Show me your ID](rails/show_me_your_id.md)
- [Do a bang up job](rails/bang_up_job.md)
- [Strict Love](rails/strict_love.md)


Credits
-------

It has been a pleasure to work with folks listed below to take advantage of the power of mutation testing in a language as dynamic as Ruby. Without them there would be no such tool.

* [Markus Schirp (mbj)](https://github.com/mbj)
* [Dan Kubb (dkubb)](https://github.com/dkubb)
* [John Backus (backus)](https://github.com/backus)

and so many others who have posed issues, contributed feedback and provided code.

