
<!-- https://stackoverflow.com/a/61945876 -->

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Page Title</title>
    <style>
      /* Whatever that is inside this <style> tag is all styling for your markup / content structure.
      /* The . with the boxed represents that it is a class */
      .boxed {
        background: #F2F2F2;
        color: black;
        border: 3px solid #535353;
        margin: 0px auto;
        width: 456px;
        padding: 10px;
        border-radius: 10px;
      }
    </style>
  </head>
  <body>
  
<!-- ### Definition (logic).

Use $:=$ or $:=$ to denote a definition.

A mathematical statement can be either true or false, which we call the truth value of the statement.

Examples of statements $P$:

* $P := 1 + 1 = 2$ (True)
* $P := 2 + 2 = 5$ (False)
* $P := \sqrt 2$ is rational (False)
* $P :=$ Sweden is a European country (True)

Examples of non-statements:

* Hello 

Let $P$ and $Q$ be statements. -->

# Chapter 1: The Real and Complex Number Systems

### Notation

Some notation used not found in *Rudin, 3rd ed*.

|Symbol          |Explanation             |
|:--------------:|------------------------|
|$:=$            | Defined equivalence.   |
|$\land$         | And (logical operator).|
|$\lor$          | Or (logical operator). |
|$\varnothing$   | The empty set.         |


## INTRODUCTION

### Definitions 1.3 (sets).


<div class="boxed">
<details><summary><b>Set membership</b></summary>

A ***set*** is a collection of objects.

For a set $A$, write $x \in A$ to indicate $x$ is an ***element*** of $A$. Write $x \not\in A$ to indicate $x$ is not an element of $A$.
</details>

<details><summary><b>Subset and superset</b></summary><br>

Let $A$ and $B$ be sets.

We say $A$ is a ***subset*** of $B$ ($A \subseteq B$) or $B$ is a ***superset*** of $A$ ($B \supseteq A$) if every element of $A$ is an element of $B$:
$$
    A \subseteq B
    \;:=\;
    B \supseteq A
    \;:=\;
    \forall a \in A, a \in B.
$$

If there are also elements in $B$ that are not in $A$, we can use ***proper* subset** ($A \subset B$) and ***proper* superset** ($B \supset A$):

$$
    A \subset B
    \;:=\;
    B \supset A
    \;:=\;
    (A \subseteq B) \land (\exists b \in B, b \not\in A).
$$
</details>
</div>

### Definition 1.4 (rationals).

<div class="boxed">
<details><summary><b>Common sets</b></summary>

Let $\mathbb{N}$ denote the set of ***natural*** numbers.
$$
    \mathbb{N} = \left\{0, 1, 2, ...\right\}.
$$

Let $\mathbb{Z}$ denote the set of ***integers***.
$$
    \mathbb{Z} = \left\{0, 1, -1, 2, -2, ...\right\}.
$$

Let $\mathbb{Q}$ denote the set of ***rationals***:
$$
    \mathbb{Q} = \left\{\frac{p}{q} : p, q \in \mathbb{Z}, q \ne 0\right\}
$$

</details>
</div>

---

## ORDERED SETS

### Definitions 1.5 (order).

<div class="boxed">
<details><summary><b>Order relation</b></summary>

Let $S$ be a set. An ***order*** $(<)$ on $S$ has two properties:

1. If $x, y \in S$ then only one of the following is true:
$$
    x < y,\quad x = y,\quad y < x.
$$
2. If $x, y, z \in S$ then
$$
    (x < y) \land (y < z) \implies x < z.
$$

</details>

<details><summary><b>Other definitions</b></summary>

**Less than** and ***greater than:***

$$
    x < y
    \;:=\;
    y > x
    .
$$

***Weak* inequalities:**
$$
    x \le y
    \;:=\;
    y \ge x
    \;:=\;
    (x < y) \lor (x = y).
$$

</details>
</div>



### Definition 1.6 (ordered set).

<div class="boxed">
<details><summary><b>Ordered set</b></summary>

An ***ordered set*** is a set $S$ in which an order $(<)$ is defined.

</details>
</div>

### Definition 1.7 (upper and lower bound).

<div class="boxed">
<details><summary><b>Upper bound</b></summary>

Let $(S, <)$ be an ordered set and $E \subset S$. Then if
$$
    \exists b \in S, \;
    \forall x \in E, \;
    x \le b,
$$
then we say $E$ is ***bounded above*** and call $b$ an ***upper bound*** of $E$.

</details>

<details><summary><b>Lower bound</b></summary>

A ***lower bound*** $a$ of $E \subset S$ ***bounded below*** is defined the same way:
$$
    \exists a \in S, \;
    \forall x \in E, \;
    x \ge a.
$$

</details>
</div>


### Definition 1.8 (supremum and infimum).


<div class="boxed">
<details><summary><b>Supremum</b></summary>

Let $(S, <)$ be an ordered set, $E \subset S$, and $E$ be bounded above. If there is an $a \in S$ where
1. $b$ is an upper bound of $E$ $(\forall x \in E,\; b \le x)$, and
2. if $x < b$ then $x$ is not an upper bound of $E$ $(y < b \Rightarrow \exists x \in E,\ y < x)$,

then $b$ is called the ***least upper bound*** or ***supremum*** of $E$. We write
$$
b = \sup E.
$$
</details>
</div>

<div class="boxed">
<details><summary><b>Infimum</b></summary>

Similarly, we define the ***greatest lower bound*** or **infimum** as
$$
    a = \inf E
    \; := \;
    (\forall x \in E,\; a \le x) \;
    \land
    (a < y \Rightarrow \exists x \in E, x < y)
    .
$$

</details>
</div>

### Definition 1.10 (LUBP).

<div class="boxed">
<details><summary><b>Least-upper-bound property (LUBP)</b></summary>

An ordered set $(S, <)$ has the ***least-upper-bound property*** if for any $E \subset S$ where $E \ne \varnothing$, if $E$ 
$$
    \exists b \in S, \; \forall x \in E,\; x \le b
    \implies
    \exists s \in S,\;
    s = \sup E.
$$

</details>
</div>


### Theorem 1.11 (sup LB=GLB).

<div class="boxed">
<details><summary><b>Supremum of lower bounds is the greatest lower bound</b></summary>

Let $(S, <)$ be an ordered set with the LUBP.

Let $B \subset S, B \ne \varnothing,$ and $B$ be bounded below $(\exists a \in S, \forall x \in B, a \le x)$.

Let $L$ be the set of all lower bounds of $B$.

Then
$$
    \exists a \in S, a = \sup L = \inf B.
$$


**Proof.** See page 5 of *Rudin, 3rd ed*.

</details>
</div>


<!-- 

$$
$$

-->

  </body>
<html>
