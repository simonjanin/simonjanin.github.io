---
layout: post
title:  "Lessons from Nassim Taleb's book Antifragile"
date:   2015-09-12 12:39:05
categories: lessons Antifragile
---
I just finished reading Nassim Taleb's book _Antifragile_, I'll try to distill some of the lessons we can derive from it, from the theoretical to the practical.
My goal is to clarify the concepts used in the book as well as to apply them broadly.

*Essentially, we are interested in systems and their responses to stressors and volatility: be it financial systems (i.e. the stock market), supply chains, biological systems (ecosystems, societies), physical systems (machinery, chemical systems, etc) and so forth.*


We are already familiar with the notions of fragility and robustness, but let us define them rigorously:

* a system is **fragile** when the response to stress gets _super-linearly_ `worse` as stress `increases` (up to a certain point). 
* a system is **robust** when the response to stress is _linear_ (up to a certain point).

In fact, there is a third possibility: antifragility.

* a system is **antifragile** when the response to stress gets **at most** _sub-linearly_ `worse` as stress `increases` and potentially better (up to a certain point).

In the third case, the system somehow **gains from disorder**.

### Examples of fragile, robust and antifragile systems - and definitions

We will give a few examples of real-world systems and classify them.
Note, though, that those notions only apply `up to a certain point`; 
that is, a completely destroyed system doesn't get any worse (because it doesn't exist anymore), 
and a robust or an antifragile system eventually breaks down under a certain level of stress as well (to convince ourselves that this is true, we go back to the laws of physics: any physical system exposed to a high enough energy will collapse).
We are therefore talking about the `expected real-world behavior of a system within a given range`.

#### Peer-to-peer systems

In their seminal paper on [peer-to-peer Botnets, Wang et al. (2007)](https://www.usenix.org/legacy/event/hotbots07/tech/full_papers/wang/wang_html/) showed that their botnet was very resistant to outside attackers trying to take it down (i.e law enforcement).
The following figure is directly taken from the paper. We notice that `taking down less than 80% of the bots in the network has virtually no effect on connectivity` - a striking manifestion of robustness.

![Antifragile Botnet]({{ site.baseurl }}/downloads/antifragileBotnet.png)

* the network gets stronger (more resilient) as more bots join the network (**antifragile**)
* the network isn't affected by partial take-down attemps (**robust**)
* the network has a single point of failure, namely the private key of the bot master (**fragile**)

This clearly shows that `a given system can simultaneously have parts which are fragile, robust and/or antifragile` : 
**those notions are therefore entirely context-specific**.

On the figure we see that the botnet is robust (has a linear response to stress) until about 80% of bots are taken down, at which point the botnet becomes fragile (has an exponentially worse response to stress) and collapses.

A good heuristic to judge the (anti)-fragility of a system is to `ask whether it is accelerating towards harm or benefit`.

#### A note on convexity, concavity and linearity

Let $$f(x)$$ be a function describing the stress to response relationship of a system. Typically (but not necessarily), the function will be of one of the following types:


Linear functions  | Convex (concave down) or Concave
-----------------------------|--------------------------------------------------
![linear functions]({{ site.baseurl }}/downloads/linear-relationship.jpg) | ![convex and concave functions]({{ site.baseurl }}/downloads/convex-concave.gif)

* (a) and (b) are equivalent, but in one case the function is increasing and the other decreasing.
* (a) could be the damage done over time
* (b) could be the health of the system over time
* (c) is typically the graph of a robust system (up to a certain point) - compare with the figure of the botnet above.
* Concave up increasing could represent a fragile system (super-linear damage over time)
* Concave down (convex) increasing could represent an antifragile system (takes proportionally less damage over time)

*Note that by changing our axis we change the concavity of the function, so it's important to know the quantities we are dealing with to distinguish fragility from anti-fragility*

#### Taleb's definition

We are now ready to understand Taleb's own definition of the concept of antifragility:

> Simply, antifragility is defined as a convex response to a stressor or source of harm (for some range of variation), leading to a positive sensitivity to increase in volatility (or variability, stress, dispersion of outcomes, or uncertainty, what is grouped under the designation "disorder cluster"). Likewise fragility is defined as a concave sensitivity to stressors, leading a negative sensitivity to increase in volatility. The relation between fragility, convexity, and sensitivity to disorder is mathematical, obtained by theorem, not derived from empirical data mining or some historical narrative. It is a priori". --- Nassem Taleb

#### The anti-fragility of Evolution

If we take a look at the multiple iterations that a given species has gone during its Evolution, we notice that `the genetic information is antifragile`.

Animal die, but the species get better and fitter with time - the good genetic information gets passed along (on average), and the bad one is weeded out.

#### The anti-fragility of Cryptography

Cryptography is the art and science of using mathematical objects to secure and hide information.

I believe that cryptography is antifragile since it gets better every time it is attacked.
In Cesar's time, trivial ciphers were used to transmit information securely; now, we can arbitrarily increase the size of keys (in public-key cryptography) and use larger hash functions (as well as more iterations) to secure data - so that Moore's law cannot catch up.
The cryptographic systems themselves are at most robust, but the methods that are being developped to build stronger systems and analyse them are constantly refined. And each successful attack on a cipher or any cryptographic function makes the process better.

`For cryptography to be antifragile, it has to get better at faster rate than cryptanalysis gets better` - it seems to be the case. Especially when we consider that problems such as factoring large numbers get increasingly hard with an increase in key size; while generating two (increasingly) large primes number doesn't get much harder with an increase in key size.
That means that even if we were to have a practical polynomial factoring algorithm (be it with Shor's algorithm using a quantum computer, or a classical computer algorithm): as long as it is comparatively easier to generate two (very) large prime numbers than to factor their product, public key cryptography is antifragile (an increase in key-size as well as computational power makes the system more robust/secure).

#### Open-source and anti-fragility

Open-source collaboration, be it Wikipedia or Linux, is inherently anti-fragile:

* decentralized
* produces reversible, small errors
* gains from a larger number of contributors
* empirical and grounded in reality
