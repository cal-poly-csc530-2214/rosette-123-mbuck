## Homework 1 - Mackinnon Buck

### 2.

Original formula: `!(!r => !(p && q))`

Subformulas:

```
p && q
(!r => !(p && q))
```

Variable mappings:

```
x1 <=> p && q
x2 <=> !r => !x1
```

Substitution conjunction:

```
!x2 && (x2 <=> !r => !x1) && (x1 <=> p && q)
```

Substitution transformations:

```
x1 <=> p && q       === (x1 => (p && q)) && ((p && q) => x1)
                    === (!x1 || (p && q)) && (!(p && q) || x1)
                    === (!x1 || p) && (!x1 || q) && (!p || !q || x1)

x2 <=> !r => !x1    === (x2 => (!r => !x1)) && ((!r => !x1) => x2)
                    === (!x2 || (!r => !x1)) && (!(!r => !x1) || x2)
                    === (!x2 || (r || !x1)) && (!(r || !x1) || x2)
                    === (!x2 || r || !x1) && ((!r && x1) || x2)
                    === (!x2 || r || !x1) && (!r || x2) && (x1 || x2)
```

Final CNF:
```
(!x2) && (!x2 || r || !x1) && (!r || x2) && (x1 || x2) && (!x1 || p) && (!x1 || q) && (!p || !q || x1)
```

(where `x1` is a<sub>p && q</sub> and `x2` is a<sub>!r => !a<sub>p && q</sub></sub>)

### 5.

* Level 1:
  * Decision: 1
  * BCP: 1, 3
  * Conflict Clause: N/A
  * Implication Graph: TODO
* Level 2:
  * Decision: 2
  * BCP: 2
  * Conflict Clause: 4 -2 -3
  * Implication Graph: TODO
* Level 1:
  * Decision: N/A
  * BCP:
  * Conflict Clause: 4 -2 -1
  * Implication Graph: TODO
* Level 0:
  * Decision: N/A
  * BCP: -1, 3, 4, -2
  * Conflict Clause: N/A
  * Implication Graph: TODO
