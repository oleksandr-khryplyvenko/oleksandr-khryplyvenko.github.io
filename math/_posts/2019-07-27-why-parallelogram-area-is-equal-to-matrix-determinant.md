---
layout: post
title: Why parallelogram area is equal to matrix determinant
category: math
date:   2019-07-27  +0200
mathjax: true
---

{% include mathjax.html %}

&nbsp; &nbsp; &nbsp; &nbsp;I've been reading through [Determinant wikipedia page](https://en.wikipedia.org/wiki/Determinant) and I didn't see justification for 'determinant of 2x2 linear mapping matrix A is equal to the area of a parallelogram with AU vertices, where U is vertices of a unit square'<br>
<br>
So let's justify this.

$$A = \begin{pmatrix}a & b\\\ c & d\end{pmatrix}, U = \begin{pmatrix}0 & 1 & 0 & 1\\\ 0 & 0 & 1 & 1\end{pmatrix}$$<br><br>
Each column of $U$ represents a unit cube vertex.<br><br>
$AU = \begin{pmatrix}0 & a & b & a+b\\\ 0 & c & d & c + d\end{pmatrix}$<br><br>
And each column of $AU$ represents a parallelogram vertex<br><br>
Let's display $AU$

<img src="{{ site.baseurl }}/public/matrix_det.png" style="width:60%;height:60%;">

Given<br><br>
$$BG = a+b - b = a$$<br>
$$CG = c+d - d = c$$<br>
$$DN = d - c$$<br>
(0)$$S_{ABCD} =  (ad - \frac{bd}{2} - \frac{ac}{2})_{ABND} + (\frac{ac}{2} - \frac{cFG}{2})_{BCF} + (\frac{(d-c)NF}{2})_{DNF}$$<br><br>
Now<br><br>
(1) $$NF + FG = NG = a+b - a = b$$<br>
(2) $$\triangle NDF \sim \triangle FCG$$ (by 3 angles) so $$\frac{NF}{FG} = \frac{d-c}{c}$$<br><br>
$$FG = b - NF\ $$ to $$\ NFc = FG(d-c)$$ gives <br>
$$NF = \frac{(b-NF)(d-c)}{c}$$<br><br>
solving, we get<br><br>
$$NF=b - \frac{cb}{d}$$<br>
$$FG=\frac{cb}{d}$$<br><br>
Now substitute $$NF$$ and $$FG$$ values to (0) gives<br><br>
$$S_{ABCD} = ad - cb$$
