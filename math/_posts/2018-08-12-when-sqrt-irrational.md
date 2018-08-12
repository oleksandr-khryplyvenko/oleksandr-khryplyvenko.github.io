---
layout: post
title: When square root of rational is irrational[just careful analysis]
category: math
date:   2018-08-12  +0200
mathjax: true
---

{% include mathjax.html %}

&nbsp; &nbsp; &nbsp; &nbsp;Once I thought: how to easy prove when $\sqrt x\ is\ irrational\ where\ x\ \in \mathbb Q$?<br>
(1). Let's assume that $\forall\ coprime\ p, q \in \mathbb N\ and\ coprime\ a,b \in \mathbb N: a \neq p^2 \land b \neq q^2 \to \sqrt{\frac{a}{b}} \neq \frac{p}{q}$

What if opposite is ture?<br>
$\exists\ coprime\ p, q \in \mathbb N\ and\ coprime\ a,b \in \mathbb N:a \neq p^2 \land b \neq q^2 \land \sqrt{\frac{a}{b}} = \frac{p}{q}$<br>
then<br>
$\frac{a}{b} = \frac{p^2}{q^2}$<br>
And here comes twist. Just to make the proof easier, we rewrite this equasion:<br>
$\frac{aq^2}{bp^2} = 1$<br>
as $a \neq p^2, a > p^2\ or\ a < p^2$, in either case, also, with either $a$ and $p^2$ have or have not common factors,
we'll have some factors remained either in numerator or in denominator, because b have no common factors with a<br>
So there's no case to get 1! And our original claim (1) is true.<br>

And this is an example when just by careful formalization and analysis, we obtained a proof.


