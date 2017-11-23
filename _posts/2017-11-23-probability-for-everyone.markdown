---
layout: post
title:  "Probability for Everyone, a.s."
date:   2017-11-23
categories: jekyll update
tags: ['featured', 'probability', 'mathematics']
image: /assets/article_images/2017-11-23-probability-for-everyone/patrick-fore-389428.jpg
use_math : true
---

*Inspired by a course which I am taking in probability theory, this blogpost is an attempt to explain the fundamentals of the mathematical theory of probability at an intuitive level. As the title suggests, this post is pretty much intended for everyone, regardless of mathematical level or ability. There will be some mathematics, but feel free to skip through these sections. The important stuff comes in between the mathematics.*

# Chance and Nature
<br/>

If you're reading this post, then at some point you've encountered chance. Chance is intertwined with nature, just as the planets revolve around the sun. But unlike the laws of motion of the universe, chance is uncertain. Every time you've played a game involving the roll of dice, or forgot to check the weather before stepping outside, or clicked next on your Spotify playlist, you've taken a bet against chance, without knowing with certainty what hand the universe will play. 

Chance, as we know it, is the possibility that something will happen - say that you roll 6 or that the sun will be shining on your way home\*. Probability is the measure of the likelihood that something will happen - i.e. the probability that you roll a 6 is 1 in 6 (assuming of course that the dice is as you would expect). 

In everyday terms, probability is our best guess at trying to predict what nature, and let's face it, what humanity has in store. For example, you might be wondering what the probability is that you will have three glorious looking donuts, coated in sprinkles (like the ones above) this evening. More so,

> probability theory is our attempt to measure uncertainty in the universe.

\* <small> This is a perfect example of how the universe plays its hand. When I started this post this morning, the sun was shining as bright as can be. The whole day was like this, except on my way home when lo and behold a runaway cloud let loose. Unexpected! <small/>

# Measuring the Universe
<br/>

Mathematical studies of chance and probability date back to the 16th century Italy and France, where the Renaissance mathematicians Geralamo Cardano, Pierre de Fermat and Blaise Pascal were mostly concerned with calculating their odds of winning games of dice. However, the modern theory of probability as we know it, was advanced during the 20th century following the development of *measure theory*. 

The goal of measure theory was to construct a systematic method in which to compare the relative sizes of sets in mathematics. Since the probability of an event occuring is precisely a *measure of the likelihood* of that event occuring, measure theory became a natural framework for studying probability. The problem with measure theory (for our purposes) is that it becomes gloriously abstract very quickly. Nonetheless, I will try and introduce the mathematical framework under which probability is studied, without going to deep into the measure theory. Let's see how far we can get:

### A Motivating Example
<br/>

Consider a game of throwing two fair dice. We would like to measure the likelihood that any roll of the dice will add up to a given number. For example, if we roll a \\(3\\) and \\(6\\), we get \\(9\\). Mathematically we can represent this as a function, \\(X\\), taking the pair \\((3,6)\\) to \\(9\\):

\\[   
    X(3,6) \to 9
\\]

We would like to consider the set of all such possible combinations of dice throws. We call this set \\(\Omega\\), which we can enumerate compactly as

\\[
\Omega = \big\\{(i,j): 1\leq i,j \leq6\big\\}
\\]

> The pair \\((3,6)\\) is then a member of \\(\Omega\\), which we write: \\((3,6) \in \Omega\\). 

However, if we consider the event that a given dice throw sums to \\(9\\), then we can see that there is more than one possible combination, i.e. the pairs:

\\[
A = \big\\{(3,6), (4,5), (5,4), (6,3) \big\\}
\\]

Evaluating \\(X\\) (sampling) on any of the pairs in the above set will give us \\(9\\). Notice that the set A is not an element (member) of \\(\Omega\\), but it clearly contains elements of \\(\Omega\\)! So we need something based on \\(\Omega\\), only more expansive. 

This motivates the concept of a *family of events\**, \\(\mathscr{F}\\), which contains all possible combinations of elements from \\(\Omega\\), including the whole of \\(\Omega\\) itself, and the empty set, denoted \\(\emptyset\\). In essence, \\(\mathscr{F}\\) is a set of sets, so that for consistency, a single roll takes the form: \\(\\{(3,6)\\}\\). 

> The set \\(A\\) is then an element of \\(\mathscr{F}\\), i.e. \\(A \in \mathscr{F}\\).

Now that we have a set of events, we can proceed to our goal of measuring the likelihood of these events. The mathematically precise manner in which we do this is fairly involved, but intuitively (and perhaps even realistically), we can think of the probability of an event as the likelihood of that event *relative* to the overall possibility of something happening. To this end, if \\(F \in \mathscr{F}\\) is *any event*, then one way of calculating its probability is:

\\[
\mathbb{P}(F) = \frac{size(F)}{size(\Omega)}
\\]

The ambiguity of course lies in what we mean precisely by the *size* of \\(F\\) or \\(\Omega\\), but this is a debate for another day! In our simple example, this is fairly easy:

* In the case of *one* die, there are 6 outcomes of a roll, i.e. \\(\Omega_1 = \\{1,2,3,4,5,6\\}\\). There is only one way of rolling a \\(1\\), so 
\\[
    \mathbb{P}(1) = \frac{size\big(\\{1\\}\big)}{size(\Omega_1)} = \frac{1}{6}
\\]
 On \\(\Omega_1\\), an example of an element of the *family of events* is \\(\\{1,2\\}\\), which we can interpret as rolling \\(1\\) *or* \\(\ 2\\), which has probability
\\[
    \mathbb{P}\big(\\{1,2\\}\big) = \frac{size\big(\\{1,2\\}\big)}{size(\Omega_1)} = \frac{2}{6} = \frac{1}{3}
\\]
* In the case of *two* dice, there are \\(6^{2} = 36\\) possible outcomes, with \\(\Omega\\) defined compactly as above. Then
\\[
    \mathbb{P}\big((1,2)\big) = \frac{size\big(\\{(1,2)\\}\big)}{size(\Omega)} = \frac{1}{36}
\\]
and taking \\(A\\) as above:
\\[
    \mathbb{P}(A) = \frac{size(A)}{size(\Omega)} = \frac{4}{36} = \frac{1}{9}
\\]

Equipped with a set of outcomes, \\(\Omega\\), a family of events, \\(\mathscr{F}\\) and a measure of probability, \\(\mathbb{P}\\), we have almost everything we need to lay out the foundamental ideas of probability theory. The missing ingredient is the function we defined at the beginning of this section: \\(X\\). This function is a tricky object and handling it requires some care. In other words a bit more math, which we will cover shortly. For now, I will claim that we can use \\(X\\) to *encode the randomness* of the example game.

\* <small> Technically \\(\mathscr{F}\\) is what we call a *\\(\sigma\\)-algebra* on \\(\\Omega\\).
<small/``>

## The Setting
<br/>

The motivating example has given enough to set the scence more generally. In summary:

The triple \\(\big(\Omega, \mathscr{F}, \mathbb{P}\big)\\) is known as a **probability space** if \\(\ \mathbb{P}(\Omega) = 1\\). In which case the map which sends elements of \\(\mathscr{F}\\) to numbers in the interval \\([0,1]\\),

\\[
\mathbb{P}:\mathscr{F} \to [0,1]    
\\]

is known as a *probability measure*.

The elements \\(A \in \mathscr{F}\\) are known as **events**, while the elements \\(\omega \in \Omega\\) (equivalently \\(\\{\omega\\} \in \mathscr{F}\\)) are called **elementary events** (or **realisations**).

The next step is define the notion of a *random variable*. Our intuition says that this must be some kind of variable that takes its values at random. Mathematically, this isn't as obvious to define. We'll proceed by getting the construction out of the way, then relating it back to our intuition.

Let \\(X:\Omega \to \mathbb{R}\\) be a function which sends the elementary events from \\(\Omega\\) to the *real line* (i.e. the dense numbers as we know them). Then the function \\(X\\) will be a **random variable** if the *inverse image* of any subset \\(B \subset \mathbb{R}\\) (the symbol \\(\subset\\) is used to indicate that \\(B\\) is a subset of \\(\mathbb{R}\\)) is contained in \\(\mathscr{F}\\). 

> A function's **inverse image** of a given set, \\(B\\), is the set of elements which it sends to \\(B\\). So for \\(X:\Omega \to \mathbb{R}\\), this is defined as:
> \\[
X^{-1}(B) = \\{\omega \in \Omega : X(\omega) \subset B\\}
\\]
> where \\(B\\) contains real numbers from \\(\mathbb{R}\\).

***

For instance, consider the function \\(X\\) from our working example of a game of two dice. Then the inverse image of \\(9\\) (taking \\(\\{9\\}\\) as a subset of \\(\mathbb{R}\\)) is

\\[\begin{align}
X^{-1}\big(\\{9\\}\big) & = \big\\{(i,j) \in \Omega : X\big((i,j)\big) = 9\big\\} \\\
                & = \big\\{(i,j) \in \Omega : i + j = 9\big\\} \\\
                & = \big\\{(3,6), (4,5), (5,4), (6,3) \big\\} \\\
                & = A
\end{align}\\]

We know that \\(A \in \mathscr{F}\\). So far, so good. In fact, since we include the empty set, \\(\emptyset\\), as part of \\(\mathscr{F}\\), it turns out that the inverse image of *any* subset of \\(\mathbb{R}\\) is in \\(\mathscr{F}\\). So \\(X\\) satisfies the condition\* for it to be a random variable.


\* <small>In reality this condition is a technical requirement which we don't have to worry about in most (computational) settings. Rather we will be more concerned if the setting we use makes sense.<small/>

## Random Variables and Randomness
<br/>

The condition that \\(X:\Omega \to \mathbb{R}\\) is a **random variable** if \\(X^{-1}(B) \in \mathscr{F}\\) for any subset \\(B \subset \mathbb{R}\\) of real numbers, can be interpreted in the following way:

> If we make some observation, \\(B\\), which is *quantifiable* in \\(\mathbb{R}\\), then \\(X^{-1}(B)\\) tells us the **mechanism which generated \\(B\\)**. In other words, the **chance** of \\(B\\) happening as governed by the randomness of \\(X\\).

In fact, we can *measure* the likelihood of \\(B\\) happening by taking the following:

\\[
\mathbb{P}\big(X^{-1}(B)\big) = \mathbb{P}\big(\\{\omega \in \Omega : X(\omega) \subset B\\}\big)
\\]

Motivated by this equivalence, as well as the desire for coherence (usually we don't think of events in terms of inverse images!), we can simply write

\\[
\mathbb{P}\big(X \subset B\big) \ \ \text{in place of} \ \ \mathbb{P}\big(X^{-1}(B)\big)
\\]

> We can read this representation as the **probability that the random variable \\(X\\) lands in \\(B\\)**.

However, the set containment symbol looks a little unwieldy and is just there for technical completeness. We can make things easier to read by writing

\\[
\mathbb{P}\big(X = B\big) \ \ \text{in place of} \ \ \mathbb{P}\big(X \subset B\big)
\\]

> This simply reads as the **probability that \\(X\\) equals \\(B\\)**.

Returning to our example, if we take \\(B = \\{9\\}\\), and then thinking of \\(\\{9\\}\\) as being exactly the same as \\(9\\), we can recover the usual notation for the probability of rolling two numbers which sum to \\(9\\):

\\[
\mathbb{P}\big(X = 9\big) = \frac{1}{9}
\\]

We can also take a more direct approach and begin in terms of the event of an interest, say some \\(A \in \mathscr{F}\\) which generates some observation. Then we take

\\[
B = X(A) = \\{X(\omega): \omega \in A\\}
\\]

And then finally, we can simpy write

\\[
\mathbb{P}(A) \ \ \text{or} \ \ \mathbb{P}\big(X(A) = B\big) \ \ \text{or} \ \ \mathbb{P}(X = B) \ \ \text{or} \ \ \mathbb{P}(B)
\\]

depending on the clarity of the context.

***

*Photo by Patrick Fore on Unsplash*