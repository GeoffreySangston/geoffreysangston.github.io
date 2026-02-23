---
usemathjax: true
use_math: true

layout: post
title: If all circles have constant geodesic curvature, does the surface have constant curvature? 
categories: 
---

*This post began as an overlong <a href="https://math.stackexchange.com/questions/4176991/if-all-circles-have-constant-geodesic-curvature-does-the-surface-have-constant">Math Stack Exchange question/answer</a>. A moderator suggested it was too long for MSE, and to try to pare the answer down and save this work on a separate personal page. It may be more pleasant to read this work by first exporting it to pdf, using your browser's Print feature.*

# Question

Let $(S, g)$ be a connected two dimensional smooth manifold which is equipped with a smooth Riemannian metric. Let $\nabla$ be the associated Levi-Civita connection. 
Consider a smooth unit-speed curve $\gamma$ on $S$ which parameterizes the boundary of a compact simply connected set with smooth boundary, and denote by $J_{\gamma}$ the unique inward pointing vector field along $\gamma$ such that $\{ \dot{\gamma}, J_\gamma\}$ is an orthonormal frame. Let $D_t$ denote covariant differentiation along  $\gamma$. 
Since $g(\dot{\gamma}, \dot{\gamma}) = 1$, compatibility of the Levi-Civita connection shows $g(D_t \dot{\gamma}, \dot{\gamma}) = 0$. 
Hence orthonormal expansion shows $D_t \dot{\gamma} = g(D_t \dot{\gamma}, J_\gamma) J_\gamma$. 
And so the *signed geodesic curvature* at a point of the unit-speed curve $\gamma$ is defined to be the value of $g(D_t \dot{\gamma}, J_\gamma)$ at that point, and this expression shows the *unsigned geodesic curvature*, by definition $|D_t \dot{\gamma}|$, equals the absolute value of the signed geodesic curvature. Note that the sign of the geodesic curvature signifies whether the curve
is curving inwards or outwards with respect to the tangent line of the compact simply connected region. 
See [0] for background on these concepts and [this thread](https://hsm.stackexchange.com/questions/3003/how-was-curvature-originally-defined-and-calculated) for some interesting history on curvature of curves.

There are at least two distinct concepts in Riemannian geometry which generalize the concept of a circle in Euclidean geometry. Note that a *geodesic ball* is the diffeomorphic (!) image of a disk that is centered at the origin under an exponential map at a point. A *geodesic circle* is the boundary of a geodesic ball. The *Riemannian distance* between two points in $S$ is the infimum of lengths of piecewise regular curves connecting them.
A *metric circle* is a locus of points in a surface which have constant Riemannian distance from a given point. Proposition 6.11 of [0] shows that a geodesic circle is a metric circle. A set is *geodesically convex* if every pair of points is connected by a unique minimizing geodesic. Since minimizing curves are geodesics up to reparameterization (Theorem 6.4 of [0]), and Riemannian manifolds are locally geodesically convex (Theorem 6.17 of [0]), small enough metric circles are geodesic circles. Therefore these two concepts are locally the same.

Another concept which generalizes the Euclidean circle is that of a closed curve with constant geodesic curvature; I specify closed curve because the hyperbolic plane has constant geodesic curvature curves which are not closed curves. My question is about characterizing the case that this concept locally agrees with the previous two. There are several questions on this website asking to show that geodesic circles on constant curvature surfaces have constant geodesic curvature. So my specific question is a kind of converse to this.

\begin{align\*}
&\text{If every point in $S$ has a neighborhood such that all geodesic circles within the neighborhood } \\\\\\
&\text{and centered the point have constant geodesic curvature, does $S$ have constant curvature?}
\end{align\*}

<hr>
[0] <cite authors="Lee, John M.">_Lee, John M._, [**Introduction to Riemannian manifolds**](http://dx.doi.org/10.1007/978-3-319-91755-9), Graduate Texts in Mathematics 176. Cham: Springer (ISBN 978-3-319-91754-2/hbk; 978-3-319-91755-9/ebook). xiii, 437&nbsp;p. (2018). [ZBL1409.53001](https://zbmath.org/?q=an:1409.53001).</cite>
    



# Answering the specific question #
The answer to the specific question is yes. A good way to understand this question is to determine the metric under geodesic polar coordinates as explicitly as possible, and this is the course we end up pursuing. This will allow us to prove a host of other similar characterizations of constant curvature spaces, and a few other theorems along the way.

First let's show that for every point $p \in S$, if all concentric geodesic circles within a geodesic ball centered at $p$ have constant geodesic curvature, then the curvature is a function only of the distance to $p$. This can essentially be found in a 1901 paper <a href="#bibliography">[1]</a> by J. K. Whittemore, but he implicitly assumes a lot of knowledge and it is in the setting of embedded surfaces. Hopefully I can unpack the assumed knowledge here in a helpful fashion, and in the language of Riemannian geometry.

Consider an orthonormal basis $e_1, e_2$ of $T_pS$. \\[x(\rho, \theta) := \exp_p(\phi (\rho, \theta)) := \exp_p(\rho \cos(\theta)\ e_1 + \rho \sin(\theta)\ e_2)\\] is a *geodesic polar mapping*, where $\exp_p$ is the exponential map at $p$. Note that the pushforward $\phi_\ast \frac{\partial}{\partial \theta}$ of $\frac{\partial}{\partial \theta}$ is well-defined and equals $0$ when $\rho = 0$. $\phi_\ast \frac{\partial}{\partial \rho}$ is only well-defined when $\rho > 0$, however. Hence the same holds for $x_\ast \frac{\partial}{\partial \theta}$ and $x_\ast \frac{\partial}{\partial \rho}$ for small enough $\rho$, as $\exp_p$ is a diffeomorphism on some neighborhood of the origin. 
 
In the traditional notation for the first fundamental form (I assume starting with Gauss's 1827 paper on curvature, see page 18 <a href="#bibliography">[8]</a> where $A$, ..., $D$ are used up and then $E$, $F$, $G$ are defined as expected), we define metric coefficients $E = E(\rho, \theta)$, $F = F(\rho, \theta)$, $G = G(\rho, \theta)$ by

\begin{align\*}
\begin{bmatrix} 
    E & F \\\\\\ 
    F & G
\end{bmatrix} 
:= 
\begin{bmatrix} 
    g\left(x_\ast\frac{\partial}{\partial \rho}, x_\ast\frac{\partial}{\partial \rho}\right) & g\left(x_\ast\frac{\partial}{\partial \rho}, x_\ast\frac{\partial}{\partial \theta}\right) \\\\\\ 
    g\left(x_\ast\frac{\partial}{\partial \theta}, x_\ast\frac{\partial}{\partial \rho}\right) & g\left(x_\ast\frac{\partial}{\partial \theta}, x_\ast\frac{\partial}{\partial \theta}\right)
\end{bmatrix}. 
\end{align\*}

Lemma 8.1.6 of <a href="#bibliography">[2]</a> states $E = 1$, $F = 0$, and $G > 0$, except on $(0, \theta)$ for any $\theta$, where $G = 0$. <a href="#gauss_lemma">See the appendix below for proof.</a> Notably, $E = 1$ means that the radial geodesics are unit-speed curves, and
$F = 0$ means that the geodesic circles are orthogonal to the radial geodesics; this is called Gauss's Lemma. These facts show $J_{x(\theta, \rho_0)} = -x_{\ast} \frac{\partial}{\partial \rho}$. 

The velocity vector field $\nu$ of a unit-speed reparameterized $\theta$ curve is the restriction of $\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}$ to the curve, so $D_\theta\nu = \nabla_{\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}}\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}$ for fixed $\rho > 0$. Hence the signed geodesic curvature along the reparameterized $\theta$ curve is 
\begin{align\*}
\kappa &= g(\nabla_{\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}}\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}, -x_\ast \frac{\partial}{\partial \rho}) \\\\\\
&= g(\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}, \nabla_{\frac{x_{\ast} \frac{\partial}{\partial\theta}}{\sqrt{G}}} x_\ast \frac{\partial}{\partial\rho})
\qquad \qquad \mathrm{Differentiate\ } g(\frac{x_{\ast} \frac{\partial}{\partial \theta}}{\sqrt{G}}, -x_{\ast}\frac{\partial}{\partial \rho}) = 0. \\\\\\
&= \frac{1}{G} g(x_\ast \frac{\partial}{\partial \theta}, \nabla_{x_\ast \frac{\partial}{\partial \rho}} x_\ast \frac{\partial}{\partial \theta}) \qquad \quad \ \nabla \mathrm{\ is\ } C(S)\mathrm{-linear\ in\ the\ first\ argument}. \\\\\\
&= \frac{G_\rho}{2G} \qquad \qquad \qquad \qquad \qquad \ \ \ \mathrm{Differentiate\ } G = g(x_\ast \frac{\partial}{\partial \theta}, x_\ast \frac{\partial}{\partial \theta}). \\\\\\
&= \frac{(\sqrt{G})\_\rho}{\sqrt{G}}.
\end{align\*}

This is a special case of Liouville's formula for signed geodesic curvature. See <a href="#bibliography">[3]</a> for Liouville's formula.

For varying $\rho$ and fixed $\theta$, this gives the first order linear equation $ (\sqrt{G})\_{\rho} (\rho, \theta) - \kappa(\rho) \sqrt{G}(\rho, \theta) = 0$. 
The main assumption of the problem is that $\kappa$ is independent of $\theta$, assuming $\rho$ is small enough. Hence the solution of this equation is given by $\sqrt{G} = e^{U + V}$, for some antiderivative $U = U(\rho)$ of $\kappa$ and some function $V = V(\theta)$. In Theorem 8.3.3 of <a href="#bibliography">[2]</a> O'Neill shows $\lim_{\rho \to 0} (\sqrt{G})\_\rho(\rho, \theta) = 1$. (This is also in Proposition 4-6.3 of do Carmo <a href="#bibliography">[3]</a>). An application of the Mean Value Theorem further shows that $(\sqrt{G})\_\rho(0, \theta) = 1$. <a href="#g_derivative">See below</a> for proof of these facts. 

Our solution for $\sqrt{G}$, together with $(\sqrt{G})\_\rho(0, \theta) = 1$, implies \\[1 =  U'(0)e^{U(0) + V(\theta)},\\]
which implies that $V$ is a constant function, since this holds for all $\theta$; we needed the fact that $U$ is independent of $\theta$ to conclude that $V$ is constant. Therefore $G$ is a function only of $\rho$. Because the curvature depends on the metric, we could conclude now that the curvature depends only on $\rho$. Instead of leaving it that, let's give a precise formula for $K$ in geodesic polar coordinates. This will eventually lead to useful formulas for $\sqrt{G}$, and hence for the metric in a geodesic ball. Before continuing I want to add that O'Neill interprets $\sqrt{G}$ as the distance between nearby radial geodesics and $(\sqrt{G})\_\rho$ as the rate these radial geodesics spread apart. So $(\sqrt{G})\_\rho(0, \theta) = 1$ means at the pole the rate of spreading of radial geodesics is the same as in the Euclidean plane.

Consider the *Riemann curvature endomorphism*, 
\\[R(X, Y)Z := \nabla_{X}\nabla_{Y} Z - \nabla_{Y}\nabla_{X} Z - \nabla_{[X, Y]}Z.\\]
The sectional curvature at a point $p$ of a two dimensional subspace $W$ of $T_pM$ on a Riemannian manifold $M$ is
\\[K(W) = K(X, Y) := \frac{g(R(X, Y)X, Y)}{g(X, X) g(Y, Y) - g(X, Y)^2},\\]
where $\{X, Y\}$ is any frame which spans $W$ at $p$. (This is the version do Carmo uses in <a href="#bibliography">[4]</a>. Lee <a href="#bibliography">[0]</a> swaps the second $X$ and $Y$ in the numerator.) To understand this formula intuitively, the numerator is like an obfuscated second fundamental form determinant. There's not enough space to fully justify it, but I do give some justification for the case essential to our use. Also <a href="#historical_digression">see below</a> for a historical digression on sectional curvature. 

Since there is only one two dimensional subspace of $T_pS$, the formula given determines a smooth function $K$ on the surface, called the curvature. We calculate an auxiliary term first. Note that $[x_\ast \frac{\partial}{\partial \rho}, x_\ast \frac{\partial}{\partial \theta}] = x_\ast [\frac{\partial}{\partial \rho}, \frac{\partial}{\partial \theta}] = 0$; we used this fact in the proof of $F = 0$ to show that $\nabla_{x_\ast \frac{\partial}{\partial \rho}} x_\ast \frac{\partial}{\partial \theta} = \nabla_{x_\ast \frac{\partial}{\partial \theta}} x_\ast \frac{\partial}{\partial \rho}$.

\begin{align\*}
0 &= \nabla_{x_\ast \frac{\partial}{\partial \theta}}\nabla_{x_\ast \frac{\partial}{\partial \rho}} x_\ast \frac{\partial}{\partial\rho} \qquad \qquad \qquad \qquad \qquad \quad \mathrm{The\ radial\ lines\ are\ geodesics.} \\\\\\
&= \nabla_{x_\ast \frac{\partial}{\partial \rho}} \nabla_{x_\ast \frac{\partial}{ \partial \theta}} x_\ast \frac{\partial}{\partial \rho} - R(x_\ast \frac{\partial}{\partial \theta}, x_\ast \frac{\partial}{\partial \rho})x_\ast \frac{\partial}{\partial \rho} \qquad \mathrm{Definition\ of\ }R \\\\\\
&= \nabla_{x_\ast \frac{\partial}{\partial \rho}} \nabla_{x_\ast \frac{\partial}{ \partial \rho}} x_\ast \frac{\partial}{\partial \theta} + R(x_\ast \frac{\partial}{\partial \rho}, x_\ast \frac{\partial}{\partial \theta})x_\ast \frac{\partial}{\partial \rho}.
\end{align\*}
Note that this is essentially the Jacobi equation for $x_\ast \frac{\partial}{\partial \theta}$ along a radial geodesic; see <a href="#bibliography">[0]</a>.

We need one more auxiliary term. Orthonormal expansion implies 
\begin{align\*}
\nabla_{x_\ast \frac{\partial}{\partial \theta}} x_\ast \frac{\partial}{\partial \rho} &= g(\nabla_{x_\ast \frac{\partial}{\partial \theta}} x_\ast \frac{\partial}{\partial \rho}, x_\ast \frac{\partial}{\partial \rho}) x_\ast \frac{\partial}{\partial \rho} + g(\nabla_{x_\ast \frac{\partial}{\partial \theta}} x_\ast \frac{\partial}{\partial \rho}, \frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}})\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}} \\\\\\
&= g(\nabla_{x_\ast \frac{\partial}{\partial \theta}} x_\ast \frac{\partial}{\partial \rho}, \frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}})\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}} \qquad \qquad \qquad \mathrm{Differentiate\ } 1 = g(x_\ast \frac{\partial}{\partial \rho}, x_\ast \frac{\partial}{\partial \rho}) \\\\\\
&=\frac{1}{\sqrt{G}} g(\nabla_{x_\ast \frac{\partial}{\partial \rho}} x_\ast \frac{\partial}{\partial \theta}, x_\ast \frac{\partial}{\partial\theta})\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}} \\\\\\
&= \frac{G_\rho}{\sqrt{G}}\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}.
\end{align\*}


Note that the denominator in the sectional curvature formula is just $G$ in our case because $E = 1$ and $F = 0$. Now we may compute
\begin{align\*}
K &= K(x_\ast \frac{\partial}{\partial \rho}, x_\ast \frac{\partial}{\partial \theta}) \\\\\\
&= \frac{1}{G}g(R(x_\ast \frac{\partial}{\partial \rho}, x_\ast \frac{\partial}{\partial \theta})x_\ast \frac{\partial}{\partial \rho}, x_\ast \frac{\partial}{\partial \theta}) \\\\\\
&= \frac{1}{G}g(-\nabla_{x_\ast \frac{\partial}{\partial \rho}} \nabla_{x_\ast \frac{\partial}{ \partial \rho}} x_\ast \frac{\partial}{\partial \theta}, x_\ast \frac{\partial}{\partial \theta}) \qquad \qquad \ \ \mathrm{By\ the\ first\ calculation\ above} \\\\\\
&= \frac{1}{G} g(\nabla_{x_\ast \frac{\partial}{\partial \rho}}x_\ast \frac{\partial}{\partial \theta}, \nabla_{x_\ast \frac{\partial}{\partial \rho}}x_\ast \frac{\partial}{\partial \theta}) - \frac{G_{\rho\rho}}{2G} \qquad \ \ \ \mathrm{Differentiate\ } \frac{1}{2}G_\rho = g(\nabla_{x_\ast \frac{\partial}{\partial \rho}} x_\ast \frac{\partial}{\partial \theta}, x_\ast \frac{\partial}{\partial \theta}) \\\\\\
&= \frac{1}{G} g(\frac{G_\rho}{\sqrt{G}}\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}, \frac{G_\rho}{\sqrt{G}}\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}) - \frac{G_{\rho\rho}}{2G} \\\\\\
&= \frac{G_\rho^2}{G^2} - \frac{G_{\rho\rho}}{2G} \\\\\\
&= -\frac{(\sqrt{G})\_{\rho\rho}}{\sqrt{G}}.
\end{align\*}


We have thus derived the following second order differential equation for $\sqrt{G}$,
\\[(\sqrt{G})\_{\rho\rho} + K\sqrt{G} = 0.\\]
(<a href="#bibliography">[2]</a> and <a href="#bibliography">[3]</a> call this the Jacobi equation. In Riemannian geometry texts the Jacobi equation has a more general form.) Before pursuing our goal further, I should remark that $(\sqrt{G})\_{\rho\rho} = -K\sqrt{G}$ shows us how the curvature effects the spread of geodesics. We already know that at $\rho = 0$, they spread at the same rate as in the Euclidean plane. When $K < 0$ the rate of spread increases, when $K > 0$ the rate of spread decreases, and when $K = 0$ the rate of spread is constant. Thus in the hyperbolic plane the geodesics become farther apart than they would in the Euclidean plane, and inversely on the sphere. This interpretation is from <a href="#bibliography">[2]</a>.

Now let's continue. Under the assumption that small enough geodesic circles have constant geodesic curvature, we have shown that $\sqrt{G}$ is a function only of $\rho$. Therefore we can conclude that $K = -\frac{\sqrt{G}\_{\rho\rho}}{\sqrt{G}}$ is a function only of $\rho$. Showing this was our first goal, and with this we are almost done.

Let $p \in S$ and consider a geodesic ball $B$ such that all concentric circles of $p$ within $B$ have constant geodesic curvature. Let $q \in B$, so that $q$ is on the boundary of one of the concentric circles $C$ of $p$ which is contained in $B$. By assumption, $q$ has a geodesic ball $D$ such that all concentric circles of $q$ within $D$ have constant geodesic curvature. The main fact we have proven shows that the curvature of $S$ is constant along $C$. All small enough concentric geodesic circles of $q$ intersect $C$. This is because $\exp_q$ is a diffeomorphism locally and the same
happens for the local preimage of the smooth curve $C$ by $\exp_q$. Therefore all points on small enough concentric circles of $q$ have the same curvature as the points on $C$, and so the curvature is constant in a neighborhood of $q$. This argument applies to every point on $C$, so $C$ has a neighborhood with constant curvature. Taking the union of such neighborhoods over all concentric circles of $p$ smaller than $C$ shows that $p$ has a neighborhood with constant curvature. Finally, connectivity of $S$ shows that $S$ has constant curvature.

### Solving for $\sqrt{G}$ ###
We have answered the question, but since all of this work has been done, we might as well prove some other nearby facts which follow from the same line of reasoning.

Note that Jacobi's equation says $(\sqrt{G})\_{\rho\rho} = - K \sqrt{G}$. Unlike in the case of the equation for the geodesic curvature $\kappa$, both terms on the right are bounded as $\rho \to 0$. Since $\sqrt{G}(0, \theta) = 0$, we find $\sqrt{G})_{\rho\rho}(0, \theta) = 0$.

Thus Jacobi's equation also holds when $\rho = 0$. Hence, for fixed $\theta$, $g(\rho) = \sqrt{G}(\rho, \theta)$ solves the following initial value problem.

\\[g''(\rho) + K(\rho)g(\rho) = 0, \qquad g(0) = 0, \qquad g'(0) = 1.\\]

Standard techniques for linear ordinary differential equations show this has a unique solution. Hence $\sqrt{G}$ is determined by Jacobi's equation on each fixed $\theta$, and smoothness of $\sqrt{G}$ implies it is uniquely determined.

In the case of constant curvature $K$, the equation above can be explicitly solved with general form
\begin{align\*}
g(\rho) = \begin{cases} 
      c_1(\theta) \cos(\sqrt{K}\rho) + c_2(\theta) \sin(\sqrt{K} \rho) & K > 0 \\\\\\
      c_1(\theta)\rho + c_2(\theta) & K = 0 \\\\\\
      c_1(\theta) \cosh(\sqrt{-K}\rho) + c_2(\theta) \sinh(\sqrt{-K} \rho) & K < 0
   \end{cases}.
\end{align\*}
Since $g(0) = 0$ and $g'(0) = 1$, in each case the $c_1$ and $c_2$ can be solved for, and we find
\begin{align\*}
\sqrt{G}(\rho, \theta) = \begin{cases} 
      \frac{1}{\sqrt{K}} \sin(\sqrt{K} \rho) & K > 0 \\\\\\
      \rho & K = 0 \\\\\\
      \frac{1}{\sqrt{-K}} \sinh(\sqrt{-K} \rho) & K < 0
   \end{cases}.
\end{align\*}

### Geodesic circles have constant geodesic curvature on constant curvature surfaces ###
We can easily prove the converse to the main question. Since $\sqrt{G}$ depends only on $\rho$ in each case of the table given above, our expression for the geodesic curvature of a geodesic circle, $\kappa = \frac{(\sqrt{G})\_\rho}{\sqrt{G}}$, shows that $\kappa$ depends only on $\rho$. Hence the geodesic curvature of any geodesic circle is constant. The geodesic curvature of a radius $\rho$ geodesic circle is

\begin{align\*}
\kappa(\rho) = \frac{(\sqrt{G})\_\rho}{\sqrt{G}} = \begin{cases} 
      \sqrt{K} \cot(\sqrt{K} \rho) & K > 0 \\\\\\
      \frac{1}{\rho} & K = 0 \\\\\\
      \sqrt{-K} \coth(\sqrt{-K} \rho) & K < 0
   \end{cases}
\end{align\*} 

One interesting observation which can now be made is that in the constant positive curvature $K$ case the sign of the geodesic curvature changes when $\rho = \frac{\pi}{2\sqrt{K}}$. This can be visualized
on the unit sphere because before $\rho = \frac{\pi}{2}$ the geodesic circle curves inwards with respect to the tangent of the region it bounds, and afterwards it curves outwards. In the nonpositive 
constant curvature cases the geodesic curvature of geodesic circles is always positive, but geodesic circles become arbitrarily straight as they increase in radius.
### Surfaces of the same curvature are locally isometric ###
Because $\sqrt{G}$ is determined by the curvature, as we have seen above, at this point this fact is just formality. This fact is called Minding's Theorem in the case the curvatures are constant. In the general case I mean that each surface $(S, g), (S', g')$ has geodesic balls $B, B'$ with geodesic polar parameterizations $x, x'$ and with curvatures $K, K'$ such that $K(\rho, \theta) = K'(\rho, \theta)$ everywhere. Also consider metric coefficients $E, F, G$ and $E', F', G'$ which are defined as above. Since $K = K'$, the previous section shows $G = G'$.

The map $x' \circ x^{-1}$ is a diffeomorphism. Note that the chain rule shows $(x' \circ x^{-1})\_{\ast} x_\ast \frac{\partial}{\partial \rho} = x'\_\ast \frac{\partial}{\partial \rho}$ and $(x' \circ x^{-1})\_{\ast} x_\ast \frac{\partial}{\partial \theta} = x'\_\ast \frac{\partial}{\partial \theta}$.

Therefore we find
\begin{align\*}
(x' \circ x^{-1})^{\ast}g'(x_\ast \frac{\partial}{\partial \rho}, x_\ast \frac{\partial}{\partial \rho}) = g'(x'\_\ast \frac{\partial}{\partial \rho}, x'\_\ast\frac{\partial}{\partial \rho}) = E' = E = g(x_\ast \frac{\partial}{\partial \rho}, x_\ast \frac{\partial}{\partial \rho}).
\end{align\*}
The corresponding facts for $F$ and $G$ follow in the same way. Since $\{x_\ast \frac{\partial}{\partial \rho}, x_\ast \frac{\partial}{\partial \theta}\}$ is a frame away from the center of the geodesic ball, we conclude that \\[(y \circ x^{-1})^{\ast}g' = g.\\]
This means that $y \circ x^{-1}$ is an isometry on the center-deleted balls. Since every point on both surfaces is in the domain of an arbitrarily small center-deleted ball, $S$ and $S'$ are locally isometric. 

### Gauss-Bonnet formula for geodesic balls ###

With the facts we have accumulated we can quickly prove a special case of the Gauss-Bonnet formula, for geodesic balls. Consider a geodesic ball $B$ parameterized by $x$ and denote the $\theta$ curve at radius $\rho_0$ by $\gamma$. A unit-speed reparameterization of $\gamma$ satisfies $1 = |\frac{d\gamma}{ds}|$, and so the chain rule implies $|\frac{ds}{d\theta}| = \frac{1}{|\frac{d\theta}{ds}|} =|\frac{d\gamma}{d\theta}| = \sqrt{G}$. Hence the *total curvature* of $\gamma$ is \\[\int_{\partial B} \kappa ds = \int_0^{2\pi} \kappa\frac{ds}{d\theta}d\theta = \int_0^{2\pi} \frac{(\sqrt{G})\_\rho}{\sqrt{G}}\sqrt{G} d\theta = \int_0^{2\pi} (\sqrt{G})\_\rho d\theta.\\]
The *total curvature* of $B$ is 
\begin{align\*}
\int_{B} K dM &= \int_0^{2\pi} \int_0^{\rho_0} K(\rho, \theta) \sqrt\{\mathrm{det}\ dx(\rho, \theta)\}\ d\rho d\theta = \int_0^{2\pi} \int_0^{\rho_0} -\frac{(\sqrt{G})\_{\rho\rho}}{\sqrt{G}}(\rho, \theta) \sqrt{G}(\rho, \theta)\ d\rho d\theta \\\\\\
&= -\int_0^{2\pi} (\sqrt{G})\_\rho(\rho_0, \theta) - (\sqrt{G})\_\rho(0, \theta)\ d\theta = -\int_0^{2\pi} (\sqrt{G})\_\rho d\theta + 2\pi.
\end{align\*}
Adding together these two equations shows
\\[\int_{B} K dM + \int_{\partial B} \kappa ds = 2\pi.\\]

### $\sqrt{G}(\rho, \theta) =  \rho - \frac{K(p)}{6}\rho^3 + r(\rho, \theta) \rho^3$ ###

(I used <a href="#bibliography">[2]</a> as a reference for this and the next section.)

In the constant curvature $K$ case we found explicit expressions for $\sqrt{G}$. In the general case, we can use Taylor's theorem to collect our facts about $\sqrt{G}$ at $\rho = 0$ into an expression for $\sqrt{G}$.  Denote the center of the geodesic ball by $p$, so the curvature of the surface at $p$ is $K(p) = K(0, \theta)$. 

Differentiating $(\sqrt{G})\_{\rho\rho} + K\sqrt{G} = 0$ shows
\\[(\sqrt{G})\_{\rho\rho\rho}(0, \theta) = -K_\rho(0, \theta) (\sqrt{G})(0, \theta) - K(0, \theta)(\sqrt{G})\_\rho(0, \theta) = -K(0, \theta) = -K(p).\\]

Hence Taylor's theorem implies \\[\sqrt{G}(\rho, \theta) =  \rho - \frac{K(p)}{6}\rho^3 + r(\rho, \theta) \rho^3,\\]
such that $r = r(\rho, \theta)$ is some smooth function for which $\lim_{\rho \to 0} r(\rho, \theta) = 0.$

Differentiate $(\sqrt{G})\_{\rho\rho} + K\sqrt{G} = 0$ two or more times to determine higher order coefficients of $\sqrt{G}$ in terms of $K$ and its $\rho$-derivatives. For example, $(\sqrt{G})\_{\rho\rho\rho\rho}(0, \theta) = -2K_\rho(0, \theta)$. 

### Other characterizations of constant curvature surfaces ###
<a id="other-characterizations-of-constant-curvature-surfaces"></a>

I was wondering about other properties of geodesic circles and geodesic balls that might characterize constant curvature surfaces. If for all small enough radii every geodesic circle of that radius has the same total curvature, does the surface have constant curvature? Replace total curvature with length and ask the same question. 


First consider the length $L(\partial B_{\rho_0})$ of $\partial B_{\rho_0}$. By applying the Taylor series for $\sqrt{G}$, we find

\begin{align\*}
L(\partial B_{\rho_0}) = \int_0^{2\pi} \sqrt{G}(\rho_0, \theta) d\theta = \int_0^{2\pi} \rho_0 - \frac{K(p)}{6}\rho_0^3 + r(\rho_0, \theta) \rho_0^3\ d\theta = 2\pi\rho_0 - 2\pi\frac{K(p)}{6}\rho_0^3 + \rho_0^3 \int_0^{2\pi} r(\rho_0, \theta) d\theta.
\end{align\*}
Rearranging terms shows \\[K(p) = \frac{3}{\pi\rho_0^3}(2\pi\rho_0 - L(\partial B_{\rho_0})) + \int_0^{2\pi} r(\rho_0, \theta) d\theta.\\]
The remainder term is bounded on compact sets, since it is smooth, so we may pass the limit through the integral. Hence \\[K(p) = \lim_{\rho_0 \to 0} \frac{3}{\pi\rho_0^3}(2\pi\rho_0 - L(\partial B_{\rho_0})).\\]

Now we ask the question from the beginning of this section, "If for all small enough radii every geodesic circle with that radius has the same length, does the surface have constant curvature?" In this case, $L(\partial B_{\rho_0})$ is independent of $p$, for small enough $\rho_0$, so the limit expression we have determined above for $K(p)$ implies $K(p)$ is constant.

Now consider the total curvature case. Denote the total curvature of $\partial B\_{\rho_0}$ by $T(\kappa)$. Following the same procedure as for length, taking a derivative of the Taylor representation this time, we find 
\\[K(p) = \lim_{\rho_0 \to 0}\frac{1}{\pi\rho_0^2}(2\pi - T(\kappa)).\\]

We conclude again that $K$ must be constant. 

Now consider the area $A(B)$ of the geodesic ball. Following the same kind of procedure shows \\[K(p) = \lim_{\rho_0 \to 0}\frac{12}{\pi \rho_0^4}(\pi \rho_0^2 - A(B)).\\]
And so again we find that if all geodesic balls of a given radius have the same area, then the surface must have constant curvature. We could repeat this for total curvature on the ball, but instead we will cite the Gauss-Bonnet formula, which we have proved above. This shows that if all geodesic balls of a given radius have the same total curvature, then their boundary circles all have the same total curvature, and we already have the characterization in this case.

With this experience, the Gauss-Bonnet formula seems remarkable if only because it involves a nontrivial quantity which actually doesn't characterize constant curvature surfaces. 
A probably artificial, but unified, version of the questions above replaces length and geodesic curvature with $\int\_{\partial B} k^a ds$, for any integer $a \neq 0$. Note that small enough
geodesic circles always have positive geodesic curvature, so this essentially asks for the $L_a$ norms to be invariant. 
It seems like the analogous question to the one I've been solving should be doable for $\int\_{\partial B} k^2 ds$. We can ask the same questions for $\int\_{B}K^a dM$. We might consider the $\sup$ norm in all cases as well. 
I imagine certain combinations of these quantities might be invariant for wider classes of surfaces than those of constant curvature, akin to the Gauss-Bonnet formula, but I have not made much progress into this idea. 
I'd be interested in knowing about any case of a combination of these terms, or similar invariants, which doesn't characterize only constant curvature surfaces. I answer several of these questions,
and others, in the subsequent [post](/Geodesic-Circles2).

### On constant curvature surfaces, geodesics circles/balls of the same radius have the same length/area

We proved the analogous statement for geodesic curvature of geodesic circles, and wrote down formulas for the geodesic curvature of geodesic circles when $K$ is constant.
These formulas are useful to have, so let's do the same for length (i.e. circumference) and area.

First we have 
\begin{align\*}
L(\partial B_\rho) = \int_{\partial B_\rho} ds = \int_0^{2\pi} \sqrt{G} d\theta.
\end{align\*}

Looking above at our table for $\sqrt{G}$, we see
\begin{align\*}
L(\partial B_\rho) = \begin{cases} 
      \frac{2\pi}{\sqrt{K}} \sin(\sqrt{K} \rho) & K > 0 \\\\\\ 
      2\pi\rho & K = 0 \\\\\\
      \frac{2\pi}{\sqrt{-K}} \sinh(\sqrt{-K} \rho) & K < 0
   \end{cases}.
\end{align\*}

We can use this to conclude that a geodesic circle of radius $\rho$ on a radius $\frac{1}{\sqrt{K}}$ sphere in $\mathbb{R}^3$ has radius $\frac{1}{\sqrt{K}} \sin(\sqrt{K} \rho) = \sqrt{G}$ 
as a circle in $\mathbb{R}^3$. Recall that $\sqrt{G}$ is a measure of how spread apart the radial geodesics are. This observation allows us to visualize this measure as the Euclidean radius
of the given geodesic circle; we can see this radius increases until the geodesic circle is the equator and then it decreases, matching our intuition about how spread apart the
geodesics are. The same observations apply to geodesic circles in the $K = 0$ case. However, [there is no isometric embedding of a hyperbolic disk into $\mathbb{R}^3$ such that boundary maps
to a circle in $\mathbb{R}^3$.](https://math.stackexchange.com/questions/4139446/can-a-hyperbolic-disk-isometrically-embed-into-mathbbr3-with-a-circle-for) As Kajelad points out (coincidentally
just a few weeks before I made all of these calculations), in the negative curvature case  the image circle would have a diameter (as a set in $\mathbb{R}^3$) 
which is bigger than the diameter of the domain circle, which contradicts the requirement that the map be an isometry. 


Now let's compute the table for area. We see
\begin{align\*}
A(B_\rho) = \int_{B}dM = \int_0^{2\pi} \int_0^{\rho} \sqrt{G} d\rho d\theta.
\end{align\*}

Using our table for $\sqrt{G}$, it is a simple matter to calculate these integrals. We find the following table, which represents the areas in the $3$ separate cases.
\begin{align\*}
A(B_\rho) = \begin{cases}
      \frac{2\pi}{K}(1 - \cos(\sqrt{K} \rho)) & K > 0 \\\\\\
      \pi\rho^2 & K = 0 \\\\\\
      \frac{2\pi}{-K} (\cosh(\sqrt{-K} \rho) - 1) & K < 0
   \end{cases}.
\end{align\*}

Note that the area of a sphere in $\mathbb{R}^3$ of given radius can also be ascertained from this table by considering the area of a maximum radius geodesic ball in the first case.

Combining our formulas for $\kappa$, $L$, and $A$ gives us an invariant relationship which holds for all constant curvature surfaces. We see
\begin{align\*}
    2\pi = K \cdot A(B_\rho) + \kappa(\rho) \cdot L(\partial B_\rho).
\end{align\*} 
Of course, this is just an expression of the Gauss-Bonnet formula in the case the surface has constant curvature.

---

# Appendix #
<a id = "gauss_lemma"></a>
## Proof of Lemma 8.1.6 of <a href="#bibliography">[2]</a>: $E = 1$, $F = 0$, $G(0, \theta) = 0$, and $G > 0$ for $\rho > 0.$


For fixed $\theta = \theta_0$, the curve $x(\rho, \theta_0)$ is the unique geodesic with velocity vector $\cos(\theta_0)\ e_1 + \sin(\theta_0)\ e_2$ at $p$, by definition of the exponential map. Since $x(\rho, \theta_0)$ is a unit speed geodesic we see $E(\rho, \theta_0) = 1$. Hence $E = 1$.

Symmetry of $\nabla$ implies \\[\nabla_{x_\ast \frac{\partial}{\partial \rho}} x_\ast \frac{\partial}{\partial \theta} = \nabla_{x_\ast \frac{\partial}{\partial \theta}} x_\ast \frac{\partial}{\partial \rho} + [x_\ast \frac{\partial}{\partial \rho}, x_\ast \frac{\partial}{\partial \theta}] = \nabla_{x_\ast \frac{\partial}{\partial \theta}} x_\ast \frac{\partial}{\partial \rho} + x_\ast [\frac{\partial}{\partial \rho}, \frac{\partial}{\partial \theta}] = \nabla_{x_\ast \frac{\partial}{\partial \theta}} x_\ast \frac{\partial}{\partial \rho}.\\]

Since $x'(\rho, \theta_0) = x_\ast \frac{\partial}{\partial \rho}$ and $x(\rho, \theta_0)$ is a geodesic, we also know $\nabla_{x_\ast \frac{\partial}{\partial \rho}} x_\ast\frac{\partial}{\partial \rho} = 0$.
Then compatibility of $\nabla$ implies \\[\frac{\partial F}{\partial \rho} = g(x_\ast\frac{\partial}{\partial \rho}, \nabla_{x_\ast \frac{\partial}{\partial \rho}} x_\ast \frac{\partial}{\partial \theta}) = g(x_\ast\frac{\partial}{\partial \rho}, \nabla_{x_\ast \frac{\partial}{\partial \theta}} x_\ast \frac{\partial}{\partial \rho}) = \frac{1}{2} \frac{\partial E}{\partial \theta} = 0.\\]
Since $x(0, \theta)$ is constant, $x_\ast \frac{\partial}{\partial \theta} (0, \theta) = x'(0, \theta) = 0$, and hence $F(0, \theta) = 0$ for all $\theta$. Since $\frac{\partial F}{\partial \rho} = 0$, we see $F(\rho, \theta) = 0$ for all $\rho$ and $\theta$, and so $F = 0$.

At $(0, \theta)$, $x_\ast \frac{\partial}{\partial \theta}$ is $0$, and so $G(0, \theta) = 0$. On $\rho > 0$, $x_\ast \frac{\partial}{\partial \rho}$ and $x_\ast \frac{\partial}{\partial \theta}$ are independent and $g$ is positive definite, so the matrix of metric coefficients above has a positive determinant. So on $\rho > 0$, $G = EG - F^2 > 0$.

<a id = "g_derivative"></a>
## Proof of $\lim_{\rho \to 0} (\sqrt{G})\_\rho = 1$


I follow the proof from Theorem 8.3.3 of <a href="#bibliography">[2]</a>. Consider a radial geodesic $\gamma(\rho) = x(\rho, \theta_0)$. When $\rho > 0$, its velocity vector field is the restriction of $x_\ast \frac{\partial}{\partial \rho}$, and when $\rho > 0$, $\{ x_\ast \frac{\partial}{\partial \rho}, \frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}} \}$. Differentiating $0 = g(x_\ast \frac{\partial}{\partial \rho}, \frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}})$ and then applying the fact that $\gamma$ is a geodesic implies 
\\[0 = g(D_\rho x_\ast \frac{\partial}{\partial \rho}, \frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}) + g(x_\ast \frac{\partial}{\partial \rho}, D_\rho \frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}) = g(x_\ast \frac{\partial}{\partial \rho}, D_\rho\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}).\\]
Furthermore, differentiating $1 = g(\frac{x_\ast \frac{\partial}{\partial\theta}}{\sqrt{G}}, \frac{x_\ast \frac{\partial}{\partial\theta}}{\sqrt{G}})$ implies
\\[0 = g(\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}, D_\rho\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}).\\]
Since away from the origin $\{x_\ast \frac{\partial}{\partial \rho}, \frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}\}$ is an orthonormal frame, these two calculations and orthonormal expansion show that $D_\rho\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}} = 0$.
A vector field $w$ along a geodesic $\psi$ such that $D_\rho w = 0$ is said to be *parallel*. So we conclude that $\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}$ is parallel along $\gamma$, for $\rho > 0$. 


The restriction of $\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}$ to $\gamma$ for $\rho > 0$ extends uniquely to a smooth vector field $v = v(\rho)$ along $\gamma$ for $\rho \ge 0$. This is because there exists a neighborhood of $\rho = 0$ such that the vector field which is the restriction of $\frac{x_\ast \frac{\partial}{\partial \theta}}{\sqrt{G}}$ to the curve $\gamma$ on $\rho > 0$ extends to a smooth vector field on the entire neighborhood, and so $v$ can be defined to be the restriction of the vector field defined on the entire neighborhood to $\gamma$ for $\rho \ge 0$. Since $v$ is smooth, it has continuous coordinate functions under any coordinate system, which implies $v(0)$ is uniquely determined by $v$ on $\rho > 0$. 

Since $v$ is parallel for $\rho > 0$, on $\rho > 0$
\\[D_\rho x_\ast \frac{\partial}{\partial \theta} = D_\rho \sqrt{G}v = (\sqrt{G})\_\rho v + \sqrt{G} D_\rho v = (\sqrt{G})\_\rho v.\\]


Taking the limit of the last equality as $\rho \to 0$ shows \\[D_\rho x_\ast \frac{\partial}{\partial \theta} \bigg|\_{\rho = 0} = \lim\_{\rho_0 \to 0}D_\rho x_\ast \frac{\partial}{\partial \theta} \bigg|\_{\rho = \rho_0} = \left[\lim_{\rho_0 \to 0}(\sqrt{G})\_\rho(\rho_0, \theta_0)\right] v(0). \tag\*{($\ast$)}\\]
The first equality follows by smoothness (hence continuous differentiability) of $x_\ast \frac{\partial}{\partial \theta}$ along $\gamma$ for $\rho \ge 0$.

Recall $\phi(\rho, \theta) = \rho \cos(\theta) e_1 + \rho \sin(\theta) e_2$. $T_pS$ becomes a Riemannian manifold in a canonical way using the metric $g$ at $p$. 
Covariant differentiation, with Levi-Civita connection $\tilde{\nabla}$, in $T_pS$ is just usual differentiation. 
Hence $\tilde{D\_\rho} \phi\_\ast \frac{\partial}{\partial \theta}\bigg|\_{\rho = 0} = -\sin(\theta_0) e_1 + \cos(\theta_0)e_2$, and in particular this has length $1$.

Since $d(\exp\_p)\_0$ is an isometry, and $x = \exp_p \circ \phi$, we must have $\left[(\exp_p)\_{\ast} \tilde{D\_\rho} \phi\_\ast \frac{\partial}{\partial \theta}\right]\bigg\|\_{\rho = 0} = D\_{\rho} x\_{\ast} \frac{\partial}{\partial \theta}\bigg\|\_{\rho = 0}$. 
Since $d(\exp\_p)\_0$ preserves lengths, we see the length of $D\_\rho x\_\ast \frac{\partial}{\partial \theta}\bigg|\_{\rho = 0}$ must be $1$. Since $v(0)$ also has length $1,$ the equation ($\ast$) above shows $v(0) = D\_\rho x\_\ast \frac{\partial}{\partial \theta} \bigg|\_{\rho = 0}$, and therefore that $\lim\_{\rho \to 0} (\sqrt{G})\_\rho(\rho, \theta\_0) = 1$.

Note that we never needed the full concept of parallel transport, which features in O'Neill's proof. Also note that this proof only actually depends on the metric being $C^1$.

## Proof of $(\sqrt{G})\_\rho(0, \theta) = 1$

This is a technical point which seems to be taken for granted in all of these sources. Consider a function $g$ which is differentiable on $\rho > 0$ and continuous on $\rho \ge 0$, such that $\lim\_{\rho \to 0} g'(\rho) = 1$; $\sqrt{G}$ satisfies this for each fixed $\theta$. The Mean Value Theorem implies for each $a > 0$ that there exists $\rho\_a\in (0, a)$ such that $g'(\rho\_a) = \frac{g(a) - g(0)}{a}$. Hence,
\\[g'(0) = \lim\_{a\to 0} \frac{g(a) - g(0)}{a} = \lim\_{a \to 0} g'(\rho\_a) = 1.\\]
I think the last equality is worth justifying because $g'$ is not assumed to be continuous at $0$, so it might not be clear that the substitution rule applies. Let $\epsilon > 0$. Since $\lim\_{b \to 0} g'(b) = 1$, there exists $\delta\_1 > 0$ such that $b < \delta\_1$ implies $|g'(b) - 1| < \epsilon$. Since $\lim\_{a \to 0} \rho_a = 0$, there exists $\delta_2 > 0$ such that $a < \delta_2$ implies $\rho_a < \delta_1$. Therefore $a < \delta_2$ implies $|g'(\rho_a) - 1| < \epsilon$. And so for all $\epsilon > 0$ there exists $\delta_2 > 0$ such that $a < \delta_2$ implies $|g'(\rho_a) - 1| < \epsilon$, which implies the equality above.

<a id="sectional_curvature_derivation"></a>
## Our use case of the sectional curvature formula


I want to explain the case of the sectional curvature formula that we actually use, to make this page as self contained as possible. 

Looking at the calculation for $K$, we only really use this simplified version of the formula, \\[K = \frac{1}{G}g(-\nabla\_{x\_\ast \frac{\partial}{\partial \rho}} \nabla\_{x\_\ast \frac{\partial}{ \partial \rho}} x\_\ast \frac{\partial}{\partial \theta}, x\_\ast \frac{\partial}{\partial \theta}).\\]

I want to show, or suggest intuitively at least, that the numerator is like an obfuscated second fundamental form determinant. To do this, let's assume that the parameterization $x$ actually parameterizes a surface in $\mathbb{R}^3$, and that we can extend the domain of $x$ in a neighborhood of any point to parameterize an open set in $\mathbb{R}^3$. For vector fields $X, Y$ tangent to the surface, the ambient connection $\tilde{\nabla}$ in $\mathbb{R}^3$, which corresponds to normal differentiation, breaks into orthogonal parts
\\[\tilde{\nabla}_X Y = \nabla_X Y + (\nabla_X Y)^\perp.\\]
The first part, the tangential covariant derivative, is the covariant derivative coming from the Levi-Civita connection on $S$. The second part is perpendicular to the surface and is called the second fundamental form; it is denoted by $\rm II (X, Y)$. Denote the Euclidean metric on $\mathbb{R}^3$ by $\tilde{g}$; our assumptions means that $\tilde{g} = g$ whenever $g$ is defined.

Note that on the surface $x_\ast \frac{\partial}{\partial \theta}$ is perpendicular to anything produced by $\nabla^{\perp}$, this gives us the first part of the next calculation.
Then we can rewrite $\nabla\_{x_\ast \frac{\partial}{\partial \rho}} x\_\ast \frac{\partial}{\partial \theta}$ in terms of the ambient connection and the second fundamental form, getting the second part.

\begin{align\*}
g(-\nabla\_{x\_\ast \frac{\partial}{\partial \rho}} \nabla\_{x\_\ast \frac{\partial}{ \partial \rho}} x\_\ast \frac{\partial}{\partial \theta}, x\_\ast \frac{\partial}{\partial \theta}) &= g(-\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} \nabla\_{x\_\ast \frac{\partial}{ \partial \rho}} x\_\ast \frac{\partial}{\partial \theta}, x\_\ast \frac{\partial}{\partial \theta}) \\\\\\
&= \tilde{g}(-\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} \tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} x\_\ast \frac{\partial}{\partial \theta} + \tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} \rm II (x\_\ast \frac{\partial}{\partial \rho}, x\_\ast \frac{\partial}{\partial \theta}), x\_\ast \frac{\partial}{\partial \theta}).
\end{align\*}

Notice that now one of ours terms (the one we calculate with below) is the same as the term we started with, except using the ambient connection. We previously showed how to derive this kind of term from the Riemann curvature endomorphism; see the line before "By the Jacobi Equation". Also recall $[x\_\ast \frac{\partial}{\partial \rho}, x\_\ast \frac{\partial}{\partial \theta}] = 0$. Hence
\begin{align\*}
 \tilde{g}(-\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} \tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} x\_\ast \frac{\partial}{\partial \theta}, x\_\ast \frac{\partial}{ \partial \theta}) &= \tilde{g}(\tilde{R}(x\_\ast \frac{\partial}{\partial \rho}, x\_\ast \frac{\partial}{\partial \theta})x\_\ast \frac{\partial}{\partial \rho}, x\_\ast \frac{\partial}{\partial \theta}) \\\\\\
&= \tilde{g}(\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}}\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \theta}} x\_\ast \frac{\partial}{\partial \rho} - \tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \theta}}\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} x\_\ast \frac{\partial}{\partial \rho}, x\_\ast \frac{\partial}{\partial \theta}) \\\\\\
&= 0.
\end{align\*}
The last equality is because $\tilde{\nabla}$ is the Euclidean connection and partial derivatives commute.

Now we consider the other term. Consider a unit vector field $N$ which is normal to the surface. Orthonormal expansion shows \\[{\rm II} (X, Y) = \tilde{g}((\nabla\_X Y)^\perp, N)N = \tilde{g}(\tilde{\nabla}\_X Y, N)N = -\tilde{g}(Y, \tilde{\nabla}\_X N)N.\\]
Now let's calculate,

\begin{align\*}
\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} \rm II (x\_\ast \frac{\partial}{\partial \rho}, x\_\ast \frac{\partial}{\partial \theta}) &= \tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} \tilde{g}(\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} x\_\ast \frac{\partial}{\partial \theta}, N) N \\\\\\
&= \frac{\partial}{\partial \rho}\tilde{g}(\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} x\_\ast \frac{\partial}{\partial \theta})N + \tilde{g}(\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} x\_\ast \frac{\partial}{\partial \theta}, N) \tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}}N.
\end{align\*}

The first term is perpendicular to $x\_\ast \frac{\partial}{\partial \theta}$, so it will
become $0$ when we take our inner product. Now we continue with our original calculation, which implies

\begin{align\*}
g(-\nabla\_{x\_\ast \frac{\partial}{\partial \rho}} \nabla\_{x\_\ast \frac{\partial}{ \partial \rho}} x\_\ast \frac{\partial}{\partial \theta}, x\_\ast \frac{\partial}{\partial \theta})  &= \tilde{g}(\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} \rm II (x\_\ast \frac{\partial}{\partial \rho}, x\_\ast \frac{\partial}{\partial \theta}), x\_\ast \frac{\partial}{\partial \theta}) \\\\\\
&= \tilde{g}(\tilde{g}(\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} x\_\ast \frac{\partial}{\partial \theta}, N) \tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}}N, x\_\ast \frac{\partial}{\partial \theta}) \\\\\\
&= \tilde{g}(\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}} x\_\ast \frac{\partial}{\partial \theta}, N) \tilde{g}(\tilde{\nabla}\_{x\_\ast \frac{\partial}{\partial \rho}}N, x\_\ast \frac{\partial}{\partial \theta}) \\\\\\
&= -|{\rm II}(x\_\ast \frac{\partial}{\partial \rho}, x\_\ast \frac{\partial}{\partial \theta})|^2
\end{align\*}

With this last calculation, the deobfuscation is complete, and we see

\begin{align\*}
K = \frac{1}{G}g(-\nabla\_{x\_\ast \frac{\partial}{\partial \rho}} \nabla\_{x\_\ast \frac{\partial}{ \partial \rho}} x\_\ast \frac{\partial}{\partial \theta}, x\_\ast \frac{\partial}{\partial \theta}) = \frac{-|{\rm II}(x\_\ast \frac{\partial}{\partial \rho}, x\_\ast \frac{\partial}{\partial \theta})|^2}{G}.
\end{align\*}

The numerator is the determinant of the second fundamental form because ${\rm II}(x\_\ast \frac{\partial}{\partial \rho}, x\_\ast \frac{\partial}{\partial \rho}) = \tilde{g}((\nabla\_{x\_\ast \frac{\partial}{\partial \rho}} x\_\ast \frac{\partial}{\partial \rho})^\perp, N)N = 0$, and the denominator is of course the determinant of the first fundamental form because $E = 1$ and $F = 0$. Thus $K$ agrees with the concept of Gaussian curvature in the embedded case.

Note that if we run this section backwards, and we accept that the Levi-Civita connection is determined by the metric, then we get a proof of Gauss's Theorema Egregium. We parameterize a geodesic ball on an embedded surface by geodesic polar coordinates. The Gaussian curvature is the quotient of determinants given above. Then we through all of the steps of this section backwards and finish with the sectional curvature formula, which depends only on the metric on $S$.

<a id="historical_digression"></a>
## Historical digression on sectional curvature



Euler studied [7, published 1767] the curvature at a given point $p$ of an embedded surface as the collection of curvatures at $p$ of curves occurring as intersections of the surface with planes containing $p$; note that he immediately reduces the problem to study intersections with planes containing a normal to the surface. He determined that (unless there is only a single value) there is a closed interval of possible curvatures, and called the minimum/maximum curvatures *principal*. In pages 11-12 of <a href="#bibliography">[8, published 1827]</a> Gauss discusses the *Gauss map*, which maps a point on an embedded surface surface to a point on a sphere corresponding to the direction of that point's surface normal, and defines the *Gaussian curvature* as the ratio of infinitesimal areas of a triangle in the image of the Gauss map and the corresponding triangle on the surface. On page 15 he concludes that the Gaussian curvature is the product of Euler's principal curvatures. 

On page 18 he essentially shows that the infinitesimal ratio of areas which defines the Gaussian curvature can be re-expressed as the determinant of the second fundamental form to the determinant of the first fundamental form. 
I explain what essentially means. On page 7 he defines $\begin{bmatrix}a \\\\\\ b \\\\\\ c\end{bmatrix}$ and $\begin{bmatrix}a' \\\\\\ b' \\\\\\ c'\end{bmatrix}$ as coefficients of $\frac{\partial x}{\partial p}$ and $\frac{\partial x}{\partial q}$ for an embedding $x = x(p, q)$ into $\mathbb{R}^3$ of the surface ($x$ is my notation since he does not name it).
 He defines $N := \begin{bmatrix}A \\\\\\ B \\\\\\ C\end{bmatrix} := \begin{bmatrix}a \\\\\\ b \\\\\\ c\end{bmatrix} \times \begin{bmatrix}a' \\\\\\ b' \\\\\\ c'\end{bmatrix}$. 
 ($N$ is my notation. Also he does not use the cross product concept, because it was not yet invented.) He defines $E, F, G$ as the respective dot products of these two vectors; so $E, F, G$ give the first fundamental form of $x$. 
 He defines $\Delta := |N|$. Lagrange's identity implies $\Delta^2 = EF - G^2$, and so there is a typo at the bottom of page 18 (which also appears on page 21 of the original <a href="#bibliography">[8b]</a>). 
 He defines $D = N \cdot \frac{\partial^2 x}{\partial q^2}, D' = N \cdot \frac{\partial^2 x}{\partial p \partial q}, D'' = N \cdot \frac{\partial^2 x}{\partial q^2}$ (see pages 7 and 16), and so $DD'' - D'^2$ equals the determinant of the second fundamental form times two extra factors of $\Delta$. 
 Hence the formula Gauss gives reduces to the ratio of the determinants of the second and first fundamental forms.

On page 20 he concludes that the Gaussian curvature can be written terms of the first fundamental form alone; this result is called Gauss's Theorema Egregium and means that the curvature is an isometry invariant. 

A revolution happened in Riemann's 1868 paper (written in 1854) <a href="#bibliography">[9]</a>. In it Riemann introduces the ideas of a differentiable manifold, Riemannian metric, and sectional curvature, which enable the direct study of intrinsic geometry. The rationale Riemann uses for defining the sectional curvature appears on pages 6-7, and is as follows. Consider, momentarily, an arbitrary Riemannian manifold $M$, $p \in M$, and any two dimensional subspace $W$ of $T_pM$. Because $\exp_p$ is a diffeomorphism on some neighborhood of the origin of $T_pM$, the geodesics at $p$ and tangent to $W$ locally determine a two dimensional smooth surface. This surface has the induced metric from $M$. Because the Gaussian curvature of an embedded surface can be written in terms of its first fundamental form alone, the Gaussian curvature of these surfaces can be defined in terms of their induced metric. Then the *sectional curvature* at $p$ of $W$ is defined to be the Gaussian curvature at $p$ of the surface of geodesics. (See the introduction to chapter 4 of <a href="#bibliography">[4]</a>.)

Do Carmo writes that in <a href="#bibliography">[10, 1869]</a> Christoffel determined how to compute the sectional curvature from the metric. In formula (4) on page 48 he defines *Christoffel symbols of the first kind* in terms of derivatives of the metric. In formula (13) on page 54 he defines the coefficients of the Riemann curvature tensor in terms of the Christoffel symbols of the first kind. I was unable to identify where or if Christoffel connects the coefficients of the Riemann curvature tensor to the notion of Gaussian curvature, as do Carmo seems to say (granted, I can't actually read German). Regardless, in Ricci and Levi-Civita's 1901 paper <a href="#bibliography">[11]</a> a formula for the Gaussian curvature is given in terms of one of these coefficients, and more notably they introduce the notion of a *covariant derivative* and express it in terms of Christoffel symbols. The formula they give is essentially a special case of the formula we use, in coordinates.

I wanted to determine where the formula for the sectional curvature which we use above was first used, but was unable to so far. 
If I find some time then I'd also like to look at Levi-Civita's paper "Nozione di parallelismo in una varietà ..." in which he introduces parallel transport, Weyl's 1918 paper on affine connections, and also something from Cartan's work on connections. I'm also curious about what was happening between Euler and Gauss, and also what happened in the gap between Christoffel and Ricci/Levi-Civita.

<hr>

<a id="bibliography"></a>
# Bibliography #

[0] <cite authors="Lee, John M.">_Lee, John M._, [**Introduction to Riemannian manifolds**](http://dx.doi.org/10.1007/978-3-319-91755-9), Graduate Texts in Mathematics 176. Cham: Springer (ISBN 978-3-319-91754-2/hbk; 978-3-319-91755-9/ebook). xiii, 437&nbsp;p. (2018). [ZBL1409.53001](https://zbmath.org/?q=an:1409.53001).</cite>

[1] <cite authors="Whittemore, J. K.">_Whittemore, J. K._, [**A note on geodesic circles.**](http://dx.doi.org/10.2307/1967629), Annals of Math. (2) 3, 21-24 (1901). [ZBL32.0615.02](https://zbmath.org/?q=an:32.0615.02).</cite>

[2] <cite authors="O'Neill, Barrett">_O'Neill, Barrett_, Elementary differential geometry (Rev. 2nd ed.)., Amsterdam: Elsevier/Academic Press (ISBN 978-0-12-088735-4/hbk). xii, 503&nbsp;p. (2006). [ZBL1208.53003](https://zbmath.org/?q=an:1208.53003).</cite>

[3] <cite authors="do Carmo, Manfredo Perdigão">_do Carmo, Manfredo Perdigão_, Differential geometry of curves and surfaces, Englewood Cliffs, N. J.: Prentice-Hall, Inc. VIII, 503 p. $ 22.50 (1976). [ZBL0326.53001](https://zbmath.org/?q=an:0326.53001).</cite>

[4] <cite authors="do Carmo, Manfredo Perdigão">_do Carmo, Manfredo Perdigão_, Riemannian geometry. Translated from the Portuguese by Francis Flaherty, Mathematics: Theory &amp; Applications. Boston, MA etc.: Birkhäuser. xiii, 300 p. (1992). [ZBL0752.53001](https://zbmath.org/?q=an:0752.53001).</cite>

In case you want to read Whittemore's paper, he cites his formulas from the following textbook, due to Bianchi. I'm leaving a link to an archive.org copy. Whittemore cites pages 161, 148, 159. Note that it's in German.

[5] *Bianchi, Luigi*, Vorlesungen über differentialgeometrie, Leipzig, B.G. Teubner (1899). <a>https://archive.org/details/vorluberdiffgeo00bianrich/page/158/mode/2up</a>


I don't think there's an English version, but if you read Italian then much of the presentation of that book seems to follow an earlier Italian textbook due to Bianchi. I link (an updated edition of) it below. See pages 181, 93, 193.

[6] *Bianchi, Luigi*, Lezioni di geometria differenziale (2nd ed.), (1902).
<a>https://archive.org/details/lezionidigeomet00unkngoog/page/n194/mode/2up</a>

[Bianchi passed away in 1928, so these are out of copyright in almost every country.](https://en.wikipedia.org/wiki/List_of_countries%27_copyright_lengths)



[7] *Euler, Leonhard*, [Recherches sur la courbure des surfaces
(Research into the curvature of surfaces). Translated by Jerry Lodder](http://eulerarchive.maa.org/backup/E333.html)


[8a] <cite authors="Gauss, K. F.">_Gauss, K. F._, [Karl Friedrich Gauss' general investigations of curved surfaces of 1827 and 1825. Translated with notes and a bibliography by *J. C. Morehead* and *A. M. Hiltebeitel*.](http://www.hti.umich.edu/cgi/t/text/text-idx?c=umhistmath;idno=ABR1255), Princeton 126 S. (1902). [ZBL33.0632.07](https://zbmath.org/?q=an:33.0632.07).</cite>
<a>https://archive.org/details/cu31924001557226/page/n31/mode/2up</a>

I also link the original version.

[8b] <cite authors="Gauss, Carl Friedrich">_Gauss, Carl Friedrich_, Disquisitiones generales circa superficies curvas, Typis Dieterichianis (1828)
<a>https://archive.org/details/disquisitionesg00gausgoog/page/n26/mode/2up</a>

[9a] *Riemann, Bernhard*, [On the Hypotheses which lie at the Bases of
Geometry. Translated by *William Kingdon Clifford*.](https://www.emis.de/classics/Riemann/WKCGeom.pdf), Nature, Vol. VIII. Nos. 183, 184, pp. 14–17, 36, 37 

I also link the original version.

[9b] *Riemann, Bernhard*, [Ueber die Fläche vom kleinsten Inhalt bei gegebener Begrenzung.](https://www.emis.de/classics/Riemann/Geom.pdf)


[10] <cite authors="Christoffel, E. B.">_Christoffel, E. B._, [*Ueber die Transformation der homogenen Differentialausdrücke zweiten Grades.*](http://dx.doi.org/10.1515/crll.1869.70.46), Borchardt J. LXX, 46-70 (1869). [ZBL02.0128.03](https://zbmath.org/?q=an:02.0128.03).</cite>

[11a] <cite authors="Ricci, M. G.; Levi-Civita, T.">_Ricci, M. G.; Levi-Civita, T._, [*Méthodes de calcul différentiel absolu et leurs applications.*](http://dx.doi.org/10.1007/BF01454201), Math. Ann. 54, 125-201 (1901). [ZBL31.0297.01](https://zbmath.org/?q=an:31.0297.01).</cite>

[11b] <cite authors="Ricci, M. G.; Levi-Civita, T.">_Ricci, M. G.; Levi-Civita, T._, [*Methods of the absolute differential calculus and
their applications (Translated by Vanessa Hale)*](http://vmchale.com/translations/tensor_translation.pdf) 
