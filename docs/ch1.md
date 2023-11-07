<!-- <!DOCTYPE markdown> -->

<!-- border div: https://stackoverflow.com/a/61945876 -->
<!-- markdown: https://stackoverflow.com/a/50974387 -->
<style>
    /* Whatever that is inside this <style> tag is all styling for your markup / content structure.
    /* The . with the boxed represents that it is a class */
    .boxed {
    background: #F2F2F2;
    color: black;
    border: 3px solid #535353;
    margin: 0px auto;
    width: auto;
    max-width: 1000px;
    padding: 10px;
    border-radius: 10px;
    }
</style>

<!-- mathjax: https://stackoverflow.com/a/39036912 -->
<script type="text/javascript" charset="utf-8" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML,
https://vincenttam.github.io/javascripts/MathJaxLocal.js">
</script>



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

<span style="display:block" class="boxed">
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
</span>


### Definition 1.4 (rationals).

<span style="display:block" class="boxed">
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
</span>



## ORDERED SETS

### Definitions 1.5 (order).

<span style="display:block" class="boxed">
<details><summary><b>Order relation</b></summary>

Let $S$ be a set. An ***order*** $(<)$ on $S$ has two properties:

**(i)** If $x, y \in S$ then only one of the following is true:
$$
    x < y,\quad x = y,\quad y < x.
$$
**(ii)** If $x, y, z \in S$ then
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
</span>


### Definition 1.6 (ordered set).

<span style="display:block" class="boxed">
<details><summary><b>Ordered set</b></summary>

An ***ordered set*** is a set $S$ in which an order $(<)$ is defined.

</details>
</span>


### Definition 1.7 (upper and lower bound).

<span style="display:block" class="boxed">
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
</span>


### Definition 1.8 (supremum and infimum).

<span style="display:block" class="boxed">
<details><summary><b>Supremum</b></summary>

Let $(S, <)$ be an ordered set, $E \subset S$, and $E$ be bounded above. If there is an $a \in S$ where
<br>
**(i)** $b$ is an upper bound of $E$:
$$
    \forall x \in E,
    \quad
    b \le x
$$

**(ii)** if $x < b$ then $x$ is not an upper bound of $E$:
$$
    y < b
    \implies
    \exists x \in E,
    \quad
    y < x,
$$

then $b$ is called the ***least upper bound*** or ***supremum*** of $E$. We write
$$
b = \sup E.
$$
</details>
</span>

<span style="display:block" class="boxed">
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
</span>

### Definition 1.10 (LUBP).

<span style="display:block" class="boxed">
<details><summary><b>Least-upper-bound property (LUBP)</b></summary>

An ordered set $(S, <)$ has the ***least-upper-bound property*** if for any $E \subset S$ where $E \ne \varnothing$, if $E$ 
$$
    \exists b \in S, \; \forall x \in E,\; x \le b
    \implies
    \exists s \in S,\;
    s = \sup E.
$$

</details>
</span>


### Theorem 1.11 (sup LB=GLB).

<span style="display:block" class="boxed">
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
</span>



## FIELDS


### Definition 1.12 (field).

<span style="display:block" class="boxed">
<details>
    <summary><b>
    Field axioms
    </b></summary>

A ***field*** $(F, +, \cdot)$ is a set $F$ with two operations, ***addition*** $(+)$ and ***multiplication*** $(\cdot)$, satisfying the "field axioms" for addition **(A)**, multiplication **(M)**, and the distributive law **(D)**.

<details>
    <summary><b>
    (A) Axioms for multiplication
    </b></summary>

**(A1)** Closure:
$$
    x, y \in F
    \implies
    x + y \in F
    .
$$
**(A2)** Commutativity:
$$
    \forall x, y \in F,
    \quad
    x + y = y + x
    .
$$

**(A3)** Associativity:
$$
    \forall x, y, z \in F,
    \quad
    (x + y) + z = x + (y + z)
    .
$$

**(A4)** Existence of identity:
$$
    \exists 0 \in F,
    \quad
    \forall x \in F,
    \quad
    0 + x = x
    .
$$

**(A5)** Existence of inverse:
$$
    \forall x \in F,
    \quad
    \exists -x \in F,
    \quad
    x + (-x) = 0
    .
$$

</details>
<details>
    <summary><b>
    (M) Axioms for multiplication
    </b></summary>

**(M1)** Closure:
$$
    x, y \in F \implies x \cdot y \in F
    .
$$

**(M2)** Commutativity:
$$
    \forall x, y \in F,
    \quad
    x \cdot y = y \cdot x
    .
$$

**(M3)** Associativity:
$$
    \forall x, y, z \in F,
    \quad
    (x \cdot y) \cdot z = x \cdot (y \cdot z)
    .
$$

**(M4)** Existence of identity:
$$
    \exists 1 \in F,
    \quad
    1 \ne 0,
    \quad
    \forall x \in F,
    \quad
    1 \cdot x = x
    .
$$

**(M5)** Existence of inverse:
$$
    \forall x \in F,
    \quad
    \exists x^{-1} \in F,
    \quad
    x \cdot x^{-1} = 1
    .
$$

</details>
<details>
    <summary><b>
    (D) The distributive law
    </b></summary>

$$
    \forall x, y, z \in F, \quad x\cdot(y+z) = x\cdot y + x \cdot z.
$$

</details>
</details>
</span>

### Proposition 1.14 (addition properties).

<span style="display:block" class="boxed">
<details>
    <summary><b>
    Properties of addition
    </b></summary>

Let $x, y, z \in F$ in field $(F, +, \cdot)$. Then the following are true.
<br>
**(a)** $x + y = x + z \implies y = z.$
<br>
**(b)** $x + y = x \implies y = 0.$
<br>
**(c)** $x + y = 0 \implies y = -x.$
<br>
**(d)** $-(-x) = x.$

</details>
</span>

### Proposition 1.15 (multiplication properties).

<span style="display:block" class="boxed">
<details>
    <summary><b>
    Properties of multiplication
    </b></summary>

Let $x, y, z \in F, \; x \ne 0$ in field $(F, +, \cdot)$. Then the following are true.
<br>
**(a)** $x \cdot y = x \cdot z \implies y = z.$
<br>
**(b)** $x \cdot y = x \implies y = 1.$
<br>
**(c)** $x \cdot y = 1 \implies y = x^{-1}.$
<br>
**(d)** $(x^{-1})^{-1} = x.$

</details>
</span>


### Proposition 1.16 (other field properties).

<span style="display:block" class="boxed">
<details>
    <summary><b>
    Other field properties
    </b></summary>

Let $x, y, z \in F$ in field $(F, +, \cdot)$. Then the following are true.
<br>
**(a)** $0 \cdot x = 0.$
<br>
**(b)** $x, y \ne 0 \implies x \cdot y \ne 0.$
<br>
**(c)** $(-x)\cdot y = -(x \cdot y) = x \cdot (-y).$
<br>
**(d)** $(-x)\cdot(-y) = x \cdot y.$

</details>
</span>


### Definition 1.17 (ordered field)

<span style="display:block" class="boxed">
<details>
    <summary><b>
    Ordered field
    </b></summary>

An ***ordered field*** $((F, +, \cdot), <)$ is a **field** $F$ that is also an **ordered set** such that $\forall x, y, z \in F$,

**(i)** $y < z \implies x + y < x + z,$
<br>
**(ii)** $x, y > 0 \implies xy > 0$.

</details>
</span>


### Definition 1.18 (ordered field properties)

<span style="display:block" class="boxed">
<details>
    <summary><b>
    Properties of an ordered field
    </b></summary>

For any $x, y, z \in F$ of an ordered field $F$:
<br>
**(a)** $x > 0 \implies -x < 0$ and vice versa.
<br>
**(b)** $x > 0,\; y < z \implies x \cdot y < x \cdot z.$
<br>
**(c)** $x < 0,\; y < z \implies x \cdot y > x \cdot z.$
<br>
**(d)** $x \ne 0 \implies x^2 > 0$.
<br>
**(e)** $0 < x < y \implies 0 < y^{-1} < x^{-1}$.

</details>
</span>


<!-- 

<span style="display:block" class="boxed">
<details>
    <summary><b>
    Title
    </b></summary>

</details>
</span>

-->

<!-- 

$$\begin{align}
\end{align}$$

-->