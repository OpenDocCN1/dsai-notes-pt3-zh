

## An example: a joint distribution over two variables

Figure 1.11 An illustration of a distribution over two variables, X, which takes 9 possible values, and Y, which takes two possible values. The top left figure shows a sample of 60 points drawn from a joint probability distribution over these variables. The remaining figures show histogram estimates of the marginal distributions p(X) and p(Y), as well as the conditional distribution p(X|Y = 1) corresponding to the bottom row in the top left figure.

## An example: boxes of fruit

\(p(B=r)=4/10\) (1.14)

\(p(B=b)=6/10\) (1.15)

respectively. Note that these satisfy \(p(B=r)+p(B=b)=1\).

Now suppose that we pick a box at random, and it turns out to be the blue box. Then the probability of selecting an apple is just the fraction of apples in the blue box which is 3/4, and so \(p(F=a|B=b)=3/4\). In fact, we can write out all four conditional probabilities for the type of fruit, given the selected box

\(p(F=a|B=r)=1/4\) (1.16)

\(p(F=o|B=r)=3/4\) (1.17)

\(p(F=a|B=b)=3/4\) (1.18)

\(p(F=o|B=b)=1/4.\) (1.19)

Again, note that these probabilities are normalized so that

\(p(F=a|B=r)+p(F=o|B=r)=1\) (1.20)

and similarly

\(p(F=a|B=b)+p(F=o|B=b)=1.\) (1.21)

We can now use the sum and product rules of probability to evaluate the overall probability of choosing an apple

\(p(F=a)=p(F=a|B=r)p(B=r)+p(F=a|B=b)p(B=b)\)

\(=\frac{1}{4}\times\frac{4}{10}+\frac{3}{4}\times\frac{6}{10}=\frac{11}{20}\) (1.22)

from which it follows, using the sum rule, that \(p(F=o)=1-11/20=9/20\).

Suppose instead we are told that a piece of fruit has been selected and it is an orange, and we would like to know which box it came from. This requires that we evaluate the probability distribution over boxes conditioned on the identity of the fruit, whereas the probabilities in (1.16)-(1.19) give the probability distribution over the fruit conditioned on the identity of the box. We can solve the problem of reversing the conditional probability by using Bayes’ theorem to give

\(p(B=r|F=o)=\frac{p(F=o|B=r)p(B=r)}{p(F=o)}=\frac{3}{4}\times\frac{4}{10}\times\frac{20}{9}\times\frac{2}{3}.\) (1.23)

From the sum rule, it then follows that \(p(B=b|F=o)=1-2/3=1/3\).

## Intuitive interpretation of Bayes’ theorem

We can provide an important interpretation of Bayes’ theorem as follows. If we had been asked which box had been chosen before being told the identity of the selected item of fruit, then the most complete information we have available is provided by the probability _p_(_B_). We call this the _prior probability_ because it is the probability available _before_ we observe the identity of the fruit. Once we are told that the fruit is an orange, we can then use Bayes’ theorem to compute the probability _p_(_B_|_F_), which we shall call the _posterior probability_ because it is the probability obtained _after_ we have observed _F_. Note that in this example, the prior probability of selecting the red box was 4/10, so that we were more likely to select the blue box than the red one. However, once we have observed that the piece of selected fruit is an orange, we find that the posterior probability of the red box is now 2/3, so that it is now more likely that the box we selected was in fact the red one. This result accords with our intuition, as the proportion of oranges is much higher in the red box than it is in the blue box, and so the observation that the fruit was an orange provides significant evidence favouring the red box. In fact, the evidence is sufficiently strong that it outweighs the prior and makes it more likely that the red box was chosen rather than the blue one.

Finally, we note that if the joint distribution of two variables factorizes into the product of the marginals, so that _p_(_X,Y_)=_p_(_X_)_p_(_Y_), then _X_ and _Y_ are said to be _independent_. From the product rule, we see that _p_(_Y_|_X_)=_p_(_Y_), and so the conditional distribution of _Y_ given _X_ is indeed independent of the value of _X_. For instance, in our boxes of fruit example, if each box contained the same fraction of apples and oranges, then _p_(_F_|_B_)=_P_(_F_), so that the probability of selecting, say, an apple is independent of which box is chosen.

