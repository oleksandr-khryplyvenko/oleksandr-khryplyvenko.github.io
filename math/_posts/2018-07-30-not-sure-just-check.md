---
layout: post
title: Not sure? - Just check!
category: math
date:   2018-07-30  +0200
mathjax: true
---

{% include mathjax.html %}

Remember your boring math classes at school.
You were learning some rules, etc.

In fact, math is a formal discipline. And if you're not sure about some rule or law,
you can try to derive it from known ones(both laws and axioms).

You may remember, that if a < b and c < d (where $a,b,c,d \in \mathbb R$),
then you can add these 2 inequalities 'position-wise', e.g.

(a < b) + (c < d) $\rightarrow$ a + c < b + d

But can you subtract them using the same rule?

As I do some programming for life, i can share a 'well-known' rule:
if you're not sure about how some piece of code would run, just check it!
Don't be too lazy, and put few lines in vim, them compile it.
And observe 'bad' feedback from compiler (if any).
If you're more lucky and use interpretable languages like python or lua -
you can just run an interactive shell(like ipython) and place lines to be checked there.

The same thing works for math as well.
The only difference is that you are that interpreter or compiler.

So let's check it.

(a < b) - (c < d)<br>
a - c < b - d<br>
a - b < c - d<br>
The last line is our result to check for contradictions.
From the addition result(which is true):<br>
a + c < b + d<br>
a - b < d - c  '$\neq$' a - b < c - d<br>

So we can't use the same formal 'subtraction' rule for inequalities

