---
layout: post
title:  "Bayesians vs frequentists"
date:   2017-07-23 02:25:02 +0200
categories: data science, bayes
---

During the last few monthes my interet for the interplay between science and society grew at a steady rate.
Data analysis is a branch of science that is directly applicable to social and societal issues, hence my growing interest for it. 
Now that I submitted my PhD dissertation \[insert party gif here\], I finally have time to really start learning data science, and I figured out bayesian techniques for statistics was a good place to start.
My awesome flatmate recommended me [Jake VanderPlas' excellent series of blogposts][jake-vdp-series] about the differences between bayesian and frequentist approaches.


# The billiard game
This problem was actually introduced by [Bayes himself][bayes]. It can be stated as follows. Alice and Bob and Carol are in a room. The room is separated into two parts (say by a curtain), so that Alice and Bob -- standing on one side of the curtain, cannot see what Carol -- standing on the other side of the curtain, does, but can hear her.
Carol makes a billard ball rol until it hits a wall. She marks the place where the wall was hit. Alice and Bob cannot see this operation, as it happens behind the curtain. 
Carol then plays the following game: she rolls again the ball, and if it hits on the left of the mark, gives a point to Alice, whereas she gives a point to Bob if it hits on the right of the mark.
Whoever reaches 6 points first wins the game. The problem is now the following: *we know that so far Alice has 5 points, and Bob has 3. What is the probability that Bob wins?*

In [his blogpost][jake-vdp], Jake presents first a ''naive'' frequentist approach that leads to an incorrect result, and then presents a Bayesian approach, which yields the correct result.
I am a bit annoyed by this blatant unfairness: frequentists deserve better than a naive and incorrect appproach!
Is it not possible to find a frequentist reasoning that yields the correct result?
I was happy to discover that someone had thought the same, and presented such a correct frequentist approach in [the comments section of the article][jake-vdp-comment-nabor].
Let's first expose the bayesian solution to the problem, as presented by Jake in his blogpost.

# Bayesian reasoning
Call \\(B\\) the probability that Bob wins, \\(D\\) the observed data (in this case, 5 points for Alice, 3 for Bob), and \\(p\\) the probability that the ball lands on Alice side.
What we want to compute the probability that Bob wins given the observed data, $$P(B|D)$$. What is easy to compute is the probability that Bob wins, given the data **and** the knowledge of the value of $$p$$: $$P(B|D,p)$$.
\\(p\\) is an unknown *nuisance parameter* we wish to get rid of. 
To do so, let us write the probability we wish to compute as an integral over the possible values of \\(p\\):
\\[
P(B|D) = \int_0^1 P(B,p|D) d p
\\]
Using Bayes' theorem, we can recast the formula as
\\[
P(B|D) = \frac{1}{P(D)} \int_0^1 P(B|D,p) P(D|p) P(p) d p
\\]
(Almost) every term on the left hand side can be computed:
* $$P(B|D,p) = (1-p)^3$$
since Bob needs to win three times in a row,
* $$P(D|p) \propto p^5(1-p)^3$$
since the data follows a binomial law,
* $$P(D) = \int_0^1 P(D|p) d p$$
.

The only remaining unknown is the distribution of $$p$$, the probability that the ball lands on Alice side. This distribution depends on the way Carol has thrown the first ball, a parameter we have absolutely no knowledge about! 

<!---
References
--->
[bayes]: https://philpapers.org/rec/BAYAET
[jake-vdp-series]: http://jakevdp.github.io/blog/2014/03/11/frequentism-and-bayesianism-a-practical-intro/
[jake-vdp]: http://jakevdp.github.io/blog/2014/06/06/frequentism-and-bayesianism-2-when-results-differ/
[jake-vdp-comment-nabor]: http://disq.us/p/rfoztw
