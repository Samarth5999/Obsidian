We can apply relational operator for every primitive type except Boolean.
Ex: `sout(true > false) // CE: operator > cannot be applied to boolean, boolean`

We can't apply relational operator for object types. 
Ex: `sout("durga123" > "durga") // CE: operator > cannot be applied to j.l.string, j.l.string` 

Nesting of relational operator is not allowed otherwise we will get CE.
Ex: `sout(10 > 20 > 30) // CE: operator > cannot be applied to boolean, int`