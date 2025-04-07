# Taylor's Theorem

Let $f$ possess at least $n+1$ derivatives on an open interval $I$ and let $a \in I$. Then for all $x \in I$, there exists $c$ between $x$ and $a$, such that

$$ f(x) = f(a) + f'(a)(x-a) + \frac{f''(a)}{2!}(x-a)^2 + \frac{f'''(a)}{3!}(x-a)^3 + \cdots + \frac{f^{(n)}(a)}{n!}(x-a)^n + R_n(x) $$

where:
- $f^{(n)}(a)$ denotes the $n$-th derivative of $f$ evaluated at the point $a$,
- $R_n(x)$ is the remainder term, which gives the error in the approximation. The Lagrange form of the remainder is:

$$ R_n(x) = \frac{f^{(n+1)}(c)}{(n+1)!}(x-a)^{n+1} $$

for some value $c$ between $x$ and $a$.

## Functions of Time

Taylor's theorem allows us to approximate a function around a point using its derivatives. If we consider position $x(t)$ as a function of time $t$, then a second-order Taylor expansion around $t$ gives:

$$ x(t + \Delta t) \approx x(t) + \dot{x}(t) \Delta t + \frac{1}{2} \ddot{x}(t) \Delta t^2 + \ldots $$

- In a constant-velocity model, we typically truncate after the first derivative:

  $$ x(t + \Delta t) \approx x(t) + \dot{x}(t) \Delta t $$

  This is effectively taking the first two terms of a Taylor expansion (position + first derivative term).

- In a constant-acceleration model, you keep the acceleration term $\ddot{x} \Delta t^2 / 2$ as well.

