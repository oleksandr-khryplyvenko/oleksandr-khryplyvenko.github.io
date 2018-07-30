---
layout: post
title: What happens in my head while proving a theorem
category: math
date:   2018-07-30  +0200
mathjax: true
---

{% include mathjax.html %}

&nbsp; &nbsp; &nbsp; &nbsp;I bet you're wondering: "how the heck these crazy guys do analytical proofs in ML articles?"
every time you're reading your next article on arxiv, or, maybe, in Nature.
To an ordinary person, it seems a complete mess or even magic obtained directly from outer space after few joints.

&nbsp; &nbsp; &nbsp; &nbsp;I did so. And I realised one thing: if you wanna do the same, you have to do some metalearning.
You have to understand how one's brain works.

&nbsp; &nbsp; &nbsp; &nbsp;When you read some proof, you see only one path that worked for this case.
You're not shown many others, non-working. In some (good) books, you can find comments
about 'why' one or other claim is done, or how a line is derived from previous.
It really helps. But when you start thinking: why they take this very exact value of epsilon,
or why they construct proof this way, you may find some patterns.

&nbsp; &nbsp; &nbsp; &nbsp;Hint. You may <b>solve</b> the proof itself.
Here I'll write how it works.

&nbsp; &nbsp; &nbsp; &nbsp;Imagine you wanna proof such a theorem:
"If a sequence converges, it converges to an unique limit"

Ok. Let's do it, step by step.

First, formalism.

"If a sequence converges". <br>
We're given a fact. A sequence converges. Formal definition of convergence for a sequence is:<br>
$\forall \varepsilon > 0 \exists N: \forall n \ge N \implies |x_n - \ell| < \varepsilon$ <br>

"it converges to an unique limit"<br>
The most important word here is 'unique'<br>
If the limit is not unique, then there should be some other limit $m \neq \ell$<br>
Okay.<br>
Now we have sequence converging to 2 limits, formally: <br>
$\forall \varepsilon > 0 \exists N_1: \forall n \ge N_1 \implies |x_n - \ell| < \varepsilon$<br>
$\forall \varepsilon > 0 \exists N_2: \forall n \ge N_2 \implies |x_n - m| < \varepsilon$<br><br>
Note, we changed variable notation (from $N$ to $N_1$ and $N_2$) only near '$\exists$' quantifier<br>
and we haven't touched variable notation for '$\forall$' quantifier.<br>
Why? because '$\forall$' statement is fair for any item we select. This simplifies notation a bit.

Formalism is done. Now we are to show that $m$ and $\ell$ is the same thing

To do this, we have to put $m$ and $\ell$ into same equasion\inequality\line somehow.<br>
(we're doing formal stuff, remember?;) )<br>

Where $m$ and $\ell$ occur in preceeding writings? Right after $\implies$ sign!<br>
Write it down here:<br>
       $|x_n - \ell| < \varepsilon$ and $|x_n - m| < \varepsilon$<br><br>
But first $x_n$ depends on $N_1$ and second $x_n$ depends on $N_2$<br>
We have to unify them somehow.
If we select $N = max(N_1, N_2)$, then both sequences will converge after this $N$<br>
(recall convergence definition: $\forall n \ge N$, so if we take maximum $N$ after which both converge, we're ok)<br>

Now we can write both inequalities in the same fair terms:<br>
$|x_n - \ell| < \varepsilon$ and $|x_n - m| < \varepsilon$<br>

They're still 2 inequalities. Not single. To make it single, we can add them!:<br>
$|x_n - \ell| + |x_n - m| < 2\varepsilon$ (1)

Now, to show that $m$ and $\ell$ is the same thing, we have to get $m - \ell$ somehow equal to 0.<br>
This means, that we have to make this very expression $m - \ell$ some how. $m$, then '-' sign, then $\ell$. Or vice versa<br>

Time to refer to 'outer space' and recall the triangle inequality:<br>
$|x_n - \ell + x_n - m| \le |x_n - \ell| + |x_n - m|$ (2)

Okay... Something bitter-sweet. Sweet, because  $\ell$ and $m$ are neighbours(left hand expr), bitter - there is no $\ell - m$ or something like that, and there's $2x_n$<br>
Now, we have to involve one of the best quality of a mathematician - being observant. Lets observe that<br>
$|x_n - m| = |m - x_n|$ - basic modulus property<br><br>
And rewrite (2) using this observation:<br>
$|x_n - \ell + m - x_n| \le |x_n - \ell| + |m - x_n|$

Magic happens, and we moved one step further - aligned $m$ along with $\ell$ and removed $x_n$!:<br>
$|m - \ell| \le |x_n - \ell| + |m - x_n|$<br><br>
Now we have to remove $|x_n - \ell| + |m - x_n|$ somehow. And we have (1) for this:<br>
$|m - \ell| \le |x_n - \ell| + |m - x_n| < 2\varepsilon$<br>
$|m - \ell| < 2\varepsilon$<br><br>
Now use imagination again, and if we take an ace from a pocket, which turns out to be an observation - if we set $\varepsilon = \frac{|m - \ell|}{2}$(we're free to take any $\varepsilon$, we'll get a contradiction:<br>
$|m - \ell| < |m - \ell|$

And all stuff we've just derived <b>should</b> work $\forall \varepsilon > 0$.<br>
Now, for any $m$ and $\ell$ we'll be able to take such $\varepsilon = \frac{|m - \ell|}{2}$, and we'll keep getting contradictions unless $m = \ell$<br><br>
In this case ($m = \ell$),  $m - \ell = 0$, and such a $\varepsilon = \frac{|m - \ell|}{2} = 0$, but we can't select $\varepsilon = 0$, because we're <b>allowed</b> to select only $\varepsilon > 0$

Thus, $m = \ell$, and we're done. The limit is unique.


