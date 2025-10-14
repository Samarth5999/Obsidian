---
prerequisites:
  - "[[Number Theory]]"
follow-up:
  - "[[Euclidean Algorithm]]"
---
# GCD

> [!important] Definition
> The largest integer d such that $d|a$ and $d|b$, where a and b both are not zero is called the greatest common divisor of a and b or $\gcd(a,b)$

>[!example]
>1. The positive common divisors of 24 and 36 are 1, 2, 3, 4, 6, and 12. Hence, $\gcd(24, 36) = 12$
>2. The integers 17 and 22 have no positive common divisors other than 1, so that $\gcd(17, 22)=1$.

### Properties of GCD

1. $\gcd(0,\pm a) = a$
2. $\gcd(0,\pm 0) = ND$
3. $\gcd(a,b) = \gcd(a,-b) = \gcd(-a,b)= \gcd(-a,-b)$
4. If $d=\gcd(a,b)$ then $\gcd(ka,kb) =$ ND if k = 0, $|k|d$ if $k\neq0$
5. Let $a = bq + r$, where a, b, q, and r are integers then $$\gcd(a,b) = \gcd(b,r)$$
6. If $a|b$ and $c|b$ then $ac|b$ if $\gcd(a,c) = 1$
7. If $a|bc$ and $\gcd(a,b)=1$ then $a|c$

>[!important] Important Results
> $$a\times b = \gcd(a,b) \times lcm(a,b)$$




