---
layout: post
title: "Prof. Jin comes"
description: "Learning seminars"
category: Learning
tags: []
---
{% include JB/setup %}
	
	警告：为了更好的显示blog中的数学公式，也许你需要开启GreaseMonkey（Safari下是NijiaKit），并且载入MathJax in Github.
	
临近春季学期期末，和往年一样MSU的金老师又来LAMDA访问了。从2008年开始，算起来5年了，每逢期末金老师都来所里访问一次，当然每次都带来很不错的学术报告，我记得不太清楚了，08年金老师做了一个偏vision的报告，10年是approximate k-means的，11年两个报告，其中一个是online learning的tutourial，今年金老师带来的是Recovering the Optimal Solution by Dual Random Projection，是发表在COLT'13上面的工作。

Random Projection是一种常用的技术，经常用于处理高维数据，比如降维、Hasing等等。在降维中使用Random Projection，即
$$
x\in \mathbb{R}^d \rightarrow \frac{1}{\sqrt{m}}R^\top x\in \mathbb{R}^m,
$$
where $R\in\mathbb{R}^{d\times m}$ is a Gaussian Random matrix. Johnson Lindenstrauss Lemma指出，Gaussian Random Projection后的samples之间的距离相对的得到了保持，即Random Projection具有保距性。
于是在将 
$$
\hat x_i = \frac{1}{\sqrt{m}}R^\top x
$$之后，我们可以在新的低维空间中，训练分类器
$$
\min\limits_{z\in \mathbb{R}^m}\frac{\lambda}{2}\|z\|^2 + \sum\limits_{i=1}^{n}\ell(y_i z^\top \hat x_i).
$$
在得到分类器系数$z$之后，可以通过$\frac{1}{\sqrt{m}}Rz^*$来重构得到原空间的分类器系数。有大量的工作表明如此重构的分类器能够获取和原空间训练的分类器相当的分类效果。

然而问题是如此重构的分类器$\hat w$和原空间的训练得到的分类器$w_*$存在着较大的差异。该工作的重心在于探讨是否存在一种从Random Projection空间下训练的分类器$z_*$来重构$w_*$的方法？

答案明显是positive的，不然就没法讲下去了。考虑如下形式的primal问题（P1）
$$
\min\limits_{w\in \mathcal{R}^d}\frac{\lambda}{2}\|w\|^2+\sum\limits_{i=1}^n\ell (y_ix_i^\topw),
$$
where $\ell (z)$ can be written as 
$$
\ell(z) =\max\limits_{\alpha \in \Omega}\alpha z- \ell_* (\alpha),
$$
$\ell_*(\alpha)$ is the convex conjugate of $\ell(z)$.
Then the dual problem can be rewritten as （P2）:
$$
\max\limits_{\alpha \in \Omega} - \sum\limits_{i=1}^{n}\ell_*(\alpha_i) - \frac{1}{2\lambda}\alpha^\top G\alpha,
$$
where $G=D(y)X^\topXD(y)$, $D(y)$ is the $Diag(y)$ and we have 
$$
w_*=-\frac{1}{\lambda}XD(y)\alpha_*,
$$
and
$$
\alpha_{*i} = \nabla \ell(y_ix_i^\top w_*).
$$
同样的，我们也可以在Random Projected空间中写下相似的和Primal问题（P3）相对的dual问题（P4）：
$$
\max\limits_{\alpha \in \Omega} - \sum\limits_{i=1}^{n}\ell_*(\alpha_i) - \frac{1}{2\lambda}\alpha^\top {\hat G}\alpha,
$$
where $\hat G=D(y)X^\top \frac{RR^\top}{m} XD(y)$.
进一步的，$z_*$和$\hat \alpha_{*i}$可以得到类似的表达。

考虑到对于Gaussian Random Projection, the expectation of $\frac{RR^\top}{m}$是$I$，所以当$m$足够大的时候，我们有足够的理由使用$\hat G$来近似$G$，也就可以用$\hat \alpha$来近似表达$\alpha$.

所以这个工作的流程来了，
- 首先利用Gaussian Random Projection降维；
- 然后在低维空间中解决P3，得到$z_*$;
- 通过$z_*$来重构$\hat \alpha_*$;
- 令$\alpha_* = \hat \alpha_*$, 并通过$\alpha_*$重构$\w_*$。

然后这个工作的Extension就是金老师的长处了，各种理论分析，证明了重构得到的$w$和原来的最优$w_*$之间的gap是bounded的。整个报告听下来，感觉该工作的思路很清楚。

