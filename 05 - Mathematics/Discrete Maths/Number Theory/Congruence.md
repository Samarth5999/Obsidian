---
prerequisites:
  - "[[Divisibility]]"
  - "[[Number Theory]]"
---


>[!important] Definition
>If a and b are integers and m is a fixed positive integer, then a is congruent to b modulo m,
>if m divides a − b
>$$a \equiv b \pmod{m}$$
>"a ≡ b (mod m)" means that a and b leave the same remainder when divided by m
>We use this notation to indicate that a is congruent to b modulo m.

Relation of congruency on the set of integers is an equivalence relation. It means that congruence modulo m (written as $a \equiv b \pmod{m}$) groups integers in such a way that the relation satisfies equivalence relation i.e. **Reflexivity**, **Symmetry** and **Transitivity**.

>[!example] 
>1. 17 is congruent to 5 modulo 6 because 6 divides 17 − 5 = 12, we see that 17 ≡ 5 (mod 6)
>2. 24 and 14 are not congruent modulo 6 because 24 − 14 = 10 is not divisible by 6
>3. $8 \equiv -1 \pmod{9}$ or $8 \equiv 8 \pmod{9}$

>[!important] 
>$$a \equiv b \pmod{m} \implies a-b=mk \text{ or } a=b+mk$$
>

---
## Properties of Congruence

* $a \equiv b \pmod{m}$ iff $a \mod{m} = b \mod{m}$
* If $a \equiv b \pmod{m}$ and $c \equiv d \pmod{m}$, then $a + c \equiv b+d \pmod{m}$ and $ac \equiv bd \pmod{m}$ but the vice versa maybe false
* $a + b \pmod{m}$ = $((a \pmod{m}) + (b \pmod{m})) \pmod{m}$
* $ab \pmod{m}$ = $((a \pmod{m}(b \pmod{m}) \pmod{m}$

