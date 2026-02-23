---
usemathjax: true
use_math: true

layout: post
title: Answering questions left open in the previous post on geodesic circles 
categories: 
---

Does invariance over all geodesic balls or circles of the same radius of integrals of the form $\int\_B K^a dM$ or $\int\_{\partial B} \kappa^a ds$ characterize constant curvature surfaces?
These questions were left open in the previous post, and I answer them, and more, in today's post. 

The facts we use were derived in the
[previous post](/Geodesic-Circles1). Briefly, we consider a geodesic ball $B$ which is parameterized by a geodesic polar coordinate parameterization $x$.
We consider the curvature $K = K(\rho, \theta)$ and geodesic curvature $\kappa = \kappa(\rho, \theta)$ of the geodesic circles centered at the pole.
These are given in terms of the metric coefficient $G = g(x\_\ast \frac{\partial}{\partial \theta}, x\_\ast \frac{\partial}{\partial \theta})$ by
\begin{align\*}
	\kappa &= \frac{(\sqrt{G})\_\rho}{\sqrt{G}}, \\\\\\
	K &= -\frac{(\sqrt{G})\_{\rho\rho}}{\sqrt{G}}.
\end{align\*}
We also derived the following
Taylor series expression for $\sqrt{G}$
\begin{align\*}
\sqrt{G}(\rho, \theta) =  \rho - \frac{K(p)}{6}\rho^3 + r(\rho, \theta) \rho^3.
\end{align\*} 
These are all standard facts; see previous post for sources.

## $\int\_B K^a dM$ 

The integrals involving $K$ are easier to work with, because $\kappa$ is infinite at $\rho = 0$ and $K$ is smooth on $B$.

Consider a Riemannian two-dimensional manifold with a geodesic ball $B$ of radius $\rho_0$.


Let's save some space by introducing notation.
\begin{align\*}
	SK^a := \int_{B} K^a dM = \int_0^{2\pi} \int_0^{\rho_0} K^a \sqrt{G} d\rho d\theta
\end{align\*}
This generalizes the total curvature on $B$. We should be able to write $K(p)$ as an expression involving derivatives of this. 
We can work more generally, for any function $F = F(\rho, \theta, p)$ which is smooth at $\rho$, is defined everywhere on the surface, and is constant with respect to $\theta$ when $\rho = 0$ and $p$ is fixed; note that this excludes $\kappa$ because $\kappa$ is not smooth at $\rho$.

Consider
\begin{align\*}
\frac{d}{d\rho} \int\_{B(\rho)} F dM \bigg\|\_{\rho = \rho_0} = \frac{d}{d\rho} \int_0^{\rho} \int_0^{2\pi} F \sqrt{G} d\theta d\rho \bigg\|\_{\rho = \rho_0} =  \int_0^{2\pi} F \sqrt{G} d\theta = \int\_{\partial B} F ds.
\end{align\*}
Denote integrals of the latter form by $TF$. This shows that if $SF$ is invariant over all geodesic balls of the same radius, then $TF$ is as well.
Since $SF= \int_0^{\rho_0} \int\_{\partial B(\rho)} F ds d\rho$, the converse holds. Let's work with $TF$ then, and of course 
$\frac{\partial}{\partial \rho} TF \bigg\|\_{\rho = 0} = 2\pi F(p)$, which I demonstrate.

Since $\frac{\partial}{\partial \rho} F\sqrt{G} = F\_\rho \sqrt{G} + F \sqrt{G}\_\rho$, and $F$ is smooth at $\rho = 0$,
we see $\frac{\partial}{\partial \rho} F\sqrt{G} \bigg\|\_{\rho = 0} = F(0, \theta).$
The Leibniz rule implies
\begin{align\*}
\frac{\partial}{\partial \rho} TF \bigg\|\_{\rho = 0} = \int_0^{2\pi} \frac{\partial}{\partial \rho} F \sqrt{G} \bigg\|\_{\rho = 0} d\theta = \int_0^{2\pi} F(0, \theta) d\theta =  2\pi F(p).
\end{align\*}
Consider the case $F = f(K)$ factors as a function of $K$. Summarizing what we've done above, we have 
\begin{align\*}
\frac{\partial^2}{\partial\rho^2} Sf(K) \bigg\|\_{\rho = 0} = \frac{\partial}{\partial \rho} Tf(K) \bigg\|\_{\rho = 0} = 2\pi f(K(p)).
\end{align\*}



Therefore if $Tf(K)$ is invariant for all geodesic circles of the same radius, which is the same as saying $Sf(K)$ is invariant for all geodesic balls of the 
same radius, then $2\pi f(K(p))$ is constant. If $f'$ is nonzero except possibly on a measure $0$ subset of the image of $K$, then $0 = d(f \circ K) = f' dK$ implies $dK = 0$ by smoothness, so that $K$ is constant; Sard's theorem implies this is the most general condition on $f$ to conclude that $K$ is constant if $f(K(p))$ is. 

And so 
we have a fairly general characterization of when integrals over $f(K)$ characterize constant curvature
surfaces (in the relevant sense). In particular, we can answer the question we started with. if $F$ is any non-constant polynomial of $K$, then the invariance of
$TF$ or $SF$ on all geodesic balls or circles of a given radius implies the surface is constant. However, we have also already proved that this holds in the case that $F$ is a constant polynomial, because this is the case that the property being preserved is area of geodesic ball with given radius, or length of geodesic circle. So we must not yet have the most general possible statement. Let's leave that question to the side, for now at least, and think about $\kappa$.


## $\int\_{\partial B} \kappa^a ds$ 


For $a \in \mathbb{R}$, define \\[T\kappa^a := \int\_{\partial B} \kappa^a ds = \int_0^{2\pi} \kappa^a \sqrt{G} d\theta.\\]

Suppose that $T\kappa^a$ is independent of $p$, meaning all geodesic circles of the same radius
have the same value of $T\kappa^a$. The factors of $\kappa$ are a difficulty because $\kappa$ is infinite at $\rho = 0$.
 
Determining the first few coefficients of a series representation of $\kappa$ would make it easier to figure out how to come up with the relevant limit
expressions. First, let's show that $\kappa \rho$ extends to a smooth function at the origin. Recall $\sqrt{G} = \rho - \frac{K(p)}{6}\rho^3 + r(\rho, \theta)\rho^3$.
This implies

\begin{align\*}
\kappa \rho = \frac{(\sqrt{G})\_\rho \rho}{\sqrt{G}} =  \frac{(\sqrt{G})\_\rho }{1 - \frac{K(p)}{6}\rho^2 + r(\rho, \theta)\rho^2}.
\end{align\*}
Since the latter expression is smooth and defined everywhere, we conclude that $\kappa \rho$ extends to a smooth function on $B$. Therefore
$\kappa$ has a pole of order $1$ at $\rho = 0$.

We can determine the desired series representation of $\kappa$ by expanding the above expression for $\kappa \rho$ into a series. 
Note that Taylor's theorem implies there exists a smooth function $g(x)$ such that $\lim\_{x \to 0} g(x) = 0$ and $\frac{1}{1 - x} = 1 + x + g(x)x$. 
Hence it is not hard to see that there exists $\tilde{g}$ such that $\lim\_{\rho \to 0} \tilde{g}(\rho, \theta) = 0$ and
\begin{align\*}
\kappa \rho &=  \frac{(\sqrt{G})\_\rho }{1 - \frac{K(p)}{6}\rho^2 + r(\rho, \theta)\rho^2} \\\\\\
&= (1 - \frac{K(p)}{2}\rho^2 + r_2(\rho, \theta) \rho^2)(1 + \frac{K(p)}{6}\rho^2 + \tilde{g}(\rho, \theta) \rho^2) \\\\\\
&= 1 - \frac{K(p)}{3} \rho^2 + o(\rho, \theta) \rho^2,
\end{align\*}
where $o(\rho, \theta)$ is some smooth function such that $\lim\_{\rho \to 0} o(\rho, \theta) = 0$.

And so we find 
\begin{align\*}
	\kappa = \frac{1}{\rho} - \frac{K(p)}{3} \rho + o(\rho, \theta) \rho.
\end{align\*}

Notice that this agrees with the formulas we have given in the previous post for the geodesic curvature of geodesic circles on constant curvature surfaces; expand $\cot(\rho)$ when $K = 1$ and $\coth(\rho)$ when $K = -1$. Luckily $K(p)$ appears as (a constant multiple of) one of the first coefficients of this series. Using this we can answer the question about characterization of constant curvature
surfaces in the case of $\kappa^a$. Note that we can use the coefficients of $\kappa \rho$ to help us compute the coefficients of $(\kappa \rho)^a$. The computation is not too involved because $\frac{\partial}{\partial\rho}(\kappa \rho) \bigg\|\_{\rho = 0} = 0.$ Computing the Taylor series coefficients of $(\kappa\rho)^a$, for any $a \in \mathbb{R}$, shows
\begin{align\*}
\kappa^a = \frac{1}{\rho^a} - \frac{aK(p)}{3}\frac{1}{\rho^{a-2}} + \tilde{o_a}(\rho, \theta)\frac{1}{\rho^{a-2}},
\end{align\*}
for some smooth function $\tilde{o_a}$ such that $\lim\_{\rho \to 0} \tilde{o_a} = 0$.

Therefore,

\begin{align\*}
 \rho^{a-1} \int\_{\partial B} \kappa^a ds &= \int_0^{2\pi} \frac{\sqrt{G}}{\rho} d\theta - \rho\int_0^{2\pi} \frac{aK(p)}{3}\sqrt{G} d\theta + \rho\int_0^{2\pi} \tilde{o_a}(\rho, \theta) \sqrt{G}\ d\theta,
\end{align\*}
where $\tilde{o_a}(\rho, \theta)$ is a smooth function such that $\lim\_{\rho \to 0} \tilde{o_a}(\rho, \theta) = 0$. We can evaluate the middle integral: 
\begin{align\*}
\rho\int_0^{2\pi} \frac{aK(p)}{3}\sqrt{G} d\theta = \rho\int\_{\partial B} \frac{aK(p)}{3} ds = \rho^2\frac{2\pi aK(p)}{3}.
\end{align\*}
The first integral reduces to
\begin{align\*}
\int_0^{2\pi} \frac{\sqrt{G}}{\rho} d\theta = \int_0^{2\pi} \frac{ \rho - \frac{K(p)}{6}\rho^3 + r(\rho, \theta)\rho^3}{\rho} d\theta = 2\pi - 2\pi \frac{K(p)}{6} \rho^2 + \rho^2 \int_0^{2\pi} r(\rho, \theta)d\theta.
\end{align\*}

These calculations imply, noting that the remainder terms tend to $0$ faster than $\rho^2$,
\begin{align\*}
\frac{2\pi (1 + 2a)}{6} K(p) = \lim\_{\rho \to 0} \frac{1}{\rho^2}(2\pi -  \rho^{a-1} \int\_{\partial B} \kappa^a ds).
\end{align\*}

It is worth noting that this formula is the same as the one derived in the previous post, in the cases $a = 0$ and $a = 1$. When $a = 2$, $\int\_{\partial B} \kappa^a ds$ gives the *energy* of $\partial B$, so we can also calculate Gaussian curvature in terms of the energy of geodesic circles. 
We can finally conclude that, for $a \neq -\frac{1}{2}$, invariance of $\int\_{\partial B} \kappa^a ds$ on all geodesic circles of a given radius implies that the surface has constant curvature. 
It seems interesting to ask if in the case $a = -\frac{1}{2}$ invariance of $\int\_{\partial B} \kappa^a ds$ still
characterizes constant curvature surfaces. For this latter question to make sense we have to assume that the signed curvature of small enough geodesic circles is always positive. This condition isn't restrictive at all though because small enough geodesic balls centered at a point exhibit the qualitative behavior of geodesic balls of the same radius and with constant
curvature equal to the curvature at the point. In the previous post I calculated the geodesic curvature of geodesic balls on constant curvature surfaces, and for small $\rho$
it is always positive.

We can use this formula to get a somewhat general characterization, which also seems too arbitrary to be the final story. Consider a smooth function $p : \mathbb{R} \to \mathbb{R}$ such that there exists
a nonzero constant $c$ such that $p(\kappa) = c\kappa^a + \tilde{p}(\kappa)$, where $\tilde{p}$ is a smooth function such that $\lim\_{\rho \to 0} \rho^{a-3} \tilde{p}(\kappa) = 0$;
for example, if $a$ is a nonnegative integer than $p$ might be an order $a$ polynomial such that a few coefficients after the leading coefficient are zero. 
Then the previous formula implies \\[\frac{2\pi (1 + 2a)}{6} K(p) = \lim\_{\rho \to 0} \frac{1}{\rho^2}(2\pi -  \frac{\rho^{a-1}}{c} \int\_{\partial B} p(\kappa) ds).\\]
This is unsatisfying though, and more work needs to be done. But that can wait for another day.

# Another day
You are not in the house of Elrond. And it is 5 o'clock in the afternoon, on June the twenty-third, if you want to know.

I believe the question that was left unanswered pertaining to $a = -\frac{1}{2}$ can be answered simply by computing more coefficients in our series representation of $\kappa$. Recall that I mentioned
in the [original post](/Geodesic-Circles1) that $(\sqrt{G})\_{\rho\rho\rho\rho}(0, \theta) = -2K_\rho(0, \theta)$. Based on what we did above to get the Taylor series representation of $\kappa$, additional terms
will therefore probably involve $K_\rho(0, \theta)$. Let's see if we can write $K_\rho(0, \theta)$ as a limit involving $\int_{\partial B} \kappa^a ds$. Maybe if we can then this will 
inspire us to answer the question we have in the case $a = -\frac{1}{2}$.

Assuming no mistakes were made (which is not impossible because this formula can't be checked against the series' in the constant curvature cases, because in such cases $K_\rho(0, \theta) = 0$), 
I found
\begin{align\*}
\kappa = \frac{1}{\rho} - \frac{K(p)}{3} \rho - \frac{K_\rho(0, \theta)}{4}\rho^2 + o(\rho, \theta) \rho.
\end{align\*}

I calculated
\begin{align\*}
\frac{\partial^3}{\partial \rho^3} (\kappa \rho)^a \bigg\|\_{\rho = 0} = -\frac{3a}{2}K_\rho(0, \theta).
\end{align\*}

And so
\begin{align\*}
\kappa^a = \frac{1}{\rho^a} - \frac{aK(p)}{3}\frac{1}{\rho^{a-2}} - \frac{aK_\rho(0, \theta)}{4} \frac{1}{\rho^{a-3}}  + \tilde{o_a}(\rho, \theta)\frac{1}{\rho^{a-3}},
\end{align\*}

Using this and previous work we find
\begin{align\*}
\rho^{a-1} \int_{\partial B} \kappa^a ds &= 2\pi - \rho^2 \frac{2\pi(1+2a)K(p)}{6} - \rho^2 \int_0^{2\pi} \frac{aK_\rho(0, \theta)}{4} \sqrt{G}(\rho, \theta) d\theta + \rho^2\int_0^{2\pi} \tilde{o_a}(\rho, \theta) \sqrt{G}(\rho, \theta)\ d\theta \\\\\\
&= 2\pi - \rho^2 \frac{2\pi(1+2a)K(p)}{6} - \rho^3 \int_0^{2\pi} \frac{aK_\rho(0, \theta)}{4} d\theta + \rho^3\int_0^{2\pi} \tilde{\tilde{o_a}}(\rho, \theta) \ d\theta
\end{align\*}

In the last line we used the fact that $\sqrt{G}$ equals $\rho$ plus higher order terms. This Taylor series representation implies
\begin{align\*}
-\frac{3a}{2} \int_0^{2\pi} K_\rho(0, \theta) d\theta = \frac{\partial^3}{\partial \rho^3} \rho^{a-1} \int_{\partial B} \kappa^a ds \bigg\|\_{\rho = 0}. 
\end{align\*}

Since $\int_{\partial B} \kappa^a ds \bigg\|\_{\rho = 0}$ is invariant on geodesic circles of the same radius, when $a \neq 0$ this implies that
$\int_0^{2\pi} K_\rho(0, \theta) d\theta$ is constant across $p$. We have already shown that when $a \neq -\frac{1}{2}$ invariance implies $K$ is constant, so we find this integral is
constant for any $a$ such that $\int_{\partial B} \kappa^a ds$ is invariant on all geodesic circles of the same radius; the only new information
we're getting here is in the $a = - \frac{1}{2}$ case.


It is clear that if we assume $K_\rho(0, \theta)$ is
constant at every point (but not necessarily across the points) then the answer is yes. Note that $K_\rho(0, \theta) = D_{\rho}K\bigg\|\_{(0, \theta)}$
and $D\_{\rho} K \bigg\|\_{(0, \theta)} = -D\_{\rho}K \bigg\|\_{(0, \theta + \pi)}$; these denote covariant differentiation along radial geodesics at the origin. Therefore
\\[K_\rho(0, \theta) = -K_\rho(0, \theta + \pi) = -K_\rho(0, \theta).\\]
So actually we find that $K_\rho(0, \theta) = 0$ everywhere. This means that at every point the directional derivative of $K$ is $0$ in any direction, and so $K$ is constant. 

But what about this weaker condition though? The weaker condition is actually not essentially different because the Leibniz integration rule implies

\begin{align\*}
\int_0^{2\pi} K_\rho(0, \theta) d\theta = \frac{\partial}{\partial \rho}\int_0^{2\pi} K(\rho, \theta) d\theta \bigg\|\_{\rho = 0}.
\end{align\*}
The previous argument implies $\frac{\partial}{\partial \rho}\int_0^{2\pi} K(\rho, \theta) d\theta \bigg\|\_{\rho = 0} = 0$ everywhere, and therefore that
$\int_0^{2\pi} K(\rho, \theta) d\theta$ is constant. Taking the limit as $\rho$ tends to $0$ implies $2\pi K(p)$ is constant. This finishes up the $a = -\frac{1}{2}$ case.


# Another nother day
I want to prove that only in constant curvature spaces does formula of the factored Gauss-Bonnet
formula hold. I also want to figure out how to ask the question that the Gauss-Bonnet formula 
is essentially the only invariant of all surfaces (up to differentiating / integrating / taking functions).
Not sure how though
