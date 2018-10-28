# binomial-coefficient
Review of the importance of the binomial coefficient in combinatorics, polynomial expansions, and probability

Definition
---
"Binomial" is so named as it refers to a two-state entity or process. For example,
- Binomial: Linear combination of two polynomials (e.g. x<sup>2</sup>-1)
- Binomial Distribution: Discrete probability distribution <i>P</i>(<i>n</i>|<i>N</i>)
of obtaining <i>n</i> successes given <i>N</i> Bernoulli trials (e.g. flipping a coin)

Permutations and Combinations
---


![](binomial_coefficient.svg)

Binomial Expansion
---
Despite its innocent looks, Pascal's triangle is a powerful tool for visualizing binomial
expansions and distributions. It is also one of the earliest mathematical recurrence
relations learned in school, although this is hardly appreciated:

![](pascals_triangle.png)

By defining each element as the sum of its upper-left and upper-right elements,
each row describes the solution to the binomial expansion of (x+1)<sup>n</sup>:
- n = 0: <b>1</b>
- n = 1: <b>1</b>x + <b>1</b>
- n = 2: <b>1</b>x<sup>2</sup> + <b>2</b>x + <b>1</b>
- n = 3: <b>1</b>x<sup>3</sup> + <b>3</b>x<sup>2</sup> + <b>3</b>x + <b>1</b>
- n = 4: <b>1</b>x<sup>4</sup> + <b>4</b>x<sup>3</sup> + <b>6</b>x<sup>2</sup> + <b>4</b>x + <b>1</b>

These coefficients are in fact the same binomial coefficients used before for calculating
the number of combinations:

![](binomial_expansion.svg)

where in this case n is the power of n in (x+1)<sup>n</sup>, and k is the power of the
corresponding term in the polynomial expansion.

Having established the relationship (and equivalence) of Pascal's triangle and the
binomial coefficient formula, Pascal's triangle is therefore the act of counting up all
possible combinations of a subgroup k from the total n. Consequently, the solution to
the binomial expansion is to count up all combinations of power terms k (x<sup>0</sup>,
x<sup>1</sup>, ..., x<sup>n-1</sup>, x<sup>n</sup>) for a given power of n in
(x+1)<sup>n</sup>.

Pascal's triangle and the binomial coefficient are unified by the following recurrence
relation:

![](recurrence_relation.svg)

Binomial Distribution
---
The binomial coefficient describes the number of possible combinations that result from
n choose k, and can therefore be used to construct a full binomial distribution as a
function of k. For example, what is the probability of flipping heads 3 times and tails
7 times, regardless of the order of the events? We need to count up all the possible
combinations of events to get 3 heads and 7 tails:


and then we have to divide this by the total number of possible combinations for all
possible values of k. Thankfully, this can be computed simply as 2<sup>10</sup>,
leading to another import combinatorics equation:


This leads us to the following equation to describe this discrete probability distribution:

Plot of the discrete binomial probability distribution for 10 coin flips:

But what if the coin is unfair? This only requires a small tweak, finally leading us to the binomial distribution formula:

Plot of the binomial distribution for  flipping an unfair coin 10 times with only a 45% chance of landing heads: