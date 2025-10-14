The Chinese Remainder Theorem (CRT) is used to solve a set of congruent equations with one variable but different moduli, which are relatively prime as shown below:
$$x ≡ a_{1}\pmod{m_{1}}$$$$x ≡ a_{2}\pmod{m_{2}}$$$$x ≡ a_{n}\pmod{m_{n}}$$CRT states that the above equations have a unique solution if the moduli are relatively prime.


> [!danger] Solution of CRT
> $$
x = a_1 M_1 y_1 + a_2 M_2 y_2 + \cdots + a_n M_n y_n \pmod{M}$$
>where, $M = m_1 \cdot m_2 \cdot \ldots \cdot m_n$
>	$M_i = \frac{M}{m_i}$
>	$y_i = M_i^{-1} \mod m_i$

