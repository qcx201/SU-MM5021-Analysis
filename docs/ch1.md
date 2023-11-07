<!-- <!DOCTYPE markdown> -->

<!-- border div: https://stackoverflow.com/a/61945876 -->
<!-- markdown: https://stackoverflow.com/a/50974387 -->
<style>
    .boxed {
    background: #F2F2F2;
    color: black;
    border: 3px solid #535353;
    margin: 0px auto;
    width: auto;
    max-width: 850px;
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

- $P := 1 + 1 = 2$ (True)
- $P := 2 + 2 = 5$ (False)
- $P := \sqrt 2$ is rational (False)
- $P :=$ Sweden is a European country (True)

Examples of non-statements:

- Hello 

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

A <b><i>set</i></b> is a collection of objects.

For a set $A$, write $x \in A$ to indicate $x$ is an <b><i>element</i></b> of $A$. Write $x \not\in A$ to indicate $x$ is not an element of $A$.
</details>

<details><summary><b>Subset and superset</b></summary><br>

Let $A$ and $B$ be sets.

We say $A$ is a <b><i>subset</i></b> of $B$ ($A \subseteq B$) or $B$ is a <b><i>superset</i></b> of $A$ ($B \supseteq A$) if every element of $A$ is an element of $B$:
$$
    A \subseteq B
    \;:=\;
    B \supseteq A
    \;:=\;
    \forall a \in A, a \in B.
$$

If there are also elements in $B$ that are not in $A$, we can use <b><i>proper</i> subset</b> ($A \subset B$) and <b><i>proper</i> superset</b> ($B \supset A$):

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

Let $\mathbb{N}$ denote the set of <b><i>natural</i></b> numbers.
$$
    \mathbb{N} = \left\{0, 1, 2, ...\right\}.
$$

Let $\mathbb{Z}$ denote the set of <b><i>integers</i></b>.
$$
    \mathbb{Z} = \left\{0, 1, -1, 2, -2, ...\right\}.
$$

Let $\mathbb{Q}$ denote the set of <b><i>rationals</i></b>:
$$
    \mathbb{Q} = \left\{\frac{p}{q} : p, q \in \mathbb{Z}, q \ne 0\right\}
$$

</details>
</div>



## ORDERED SETS

### Definitions 1.5 (order).

<div class="boxed">
<details><summary><b>Order relation</b></summary>

Let $S$ be a set. An <b><i>order</i></b> $(<)$ on $S$ has two properties:

<b>(i)</b> If $x, y \in S$ then only one of the following is true:
$$
    x < y,\quad x = y,\quad y < x.
$$
<b>(ii)</b> If $x, y, z \in S$ then
$$
    (x < y) \land (y < z) \implies x < z.
$$

</details>

<details><summary><b>Other definitions</b></summary>

**Less than</b> and <b><i>greater than:</i></b>

$$
    x < y
    \;:=\;
    y > x
    .
$$

***Weak</i> inequalities:**
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

An <b><i>ordered set</i></b> is a set $S$ in which an order $(<)$ is defined.

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
then we say $E$ is <b><i>bounded above</i></b> and call $b$ an <b><i>upper bound</i></b> of $E$.

</details>

<details><summary><b>Lower bound</b></summary>

A <b><i>lower bound</i></b> $a$ of $E \subset S$ <b><i>bounded below</i></b> is defined the same way:
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
<br>
<b>(i)</b> $b$ is an upper bound of $E$:
$$
    \forall x \in E,
    \quad
    b \le x
$$

<b>(ii)</b> if $x < b$ then $x$ is not an upper bound of $E$:
$$
    y < b
    \implies
    \exists x \in E,
    \quad
    y < x,
$$

then $b$ is called the <b><i>least upper bound</i></b> or <b><i>supremum</i></b> of $E$. We write
$$
b = \sup E.
$$
</details>
</div>

<div class="boxed">
<details><summary><b>Infimum</b></summary>

Similarly, we define the <b><i>greatest lower bound</i></b> or <b>infimum</b> as
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

An ordered set $(S, <)$ has the <b><i>least-upper-bound property</i></b> if for any $E \subset S$ where $E \ne \varnothing$, if $E$ 
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


<b>Proof.</b> See page 5 of <i>Rudin, 3rd ed</i>.

</details>
</div>



## FIELDS


### Definition 1.12 (field).

<div class="boxed">
<details>
    <summary><b>
    Field axioms
    </b></summary>

A <b><i>field</i></b> $(F, +, \cdot)$ is a set $F$ with two operations, <b><i>addition</i></b> $(+)$ and <b><i>multiplication</i></b> $(\cdot)$, satisfying the "field axioms" for addition <b>(A)</b>, multiplication <b>(M)</b>, and the distributive law <b>(D)</b>.

<details>
    <summary><b>
    (A) Axioms for multiplication
    </b></summary>

<b>(A1)</b> Closure:
$$
    x, y \in F
    \implies
    x + y \in F
    .
$$
<b>(A2)</b> Commutativity:
$$
    \forall x, y \in F,
    \quad
    x + y = y + x
    .
$$

<b>(A3)</b> Associativity:
$$
    \forall x, y, z \in F,
    \quad
    (x + y) + z = x + (y + z)
    .
$$

<b>(A4)</b> Existence of identity:
$$
    \exists 0 \in F,
    \quad
    \forall x \in F,
    \quad
    0 + x = x
    .
$$

<b>(A5)</b> Existence of inverse:
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

<b>(M1)</b> Closure:
$$
    x, y \in F \implies x \cdot y \in F
    .
$$

<b>(M2)</b> Commutativity:
$$
    \forall x, y \in F,
    \quad
    x \cdot y = y \cdot x
    .
$$

<b>(M3)</b> Associativity:
$$
    \forall x, y, z \in F,
    \quad
    (x \cdot y) \cdot z = x \cdot (y \cdot z)
    .
$$

<b>(M4)</b> Existence of identity:
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

<b>(M5)</b> Existence of inverse:
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
</div>

### Proposition 1.14 (addition properties).

<div class="boxed">
<details>
    <summary><b>
    Properties of addition
    </b></summary>

Let $x, y, z \in F$ in field $(F, +, \cdot)$. Then the following are true.
<br>
<b>(a)</b> $x + y = x + z \implies y = z.$
<br>
<b>(b)</b> $x + y = x \implies y = 0.$
<br>
<b>(c)</b> $x + y = 0 \implies y = -x.$
<br>
<b>(d)</b> $-(-x) = x.$

</details>
</div>

### Proposition 1.15 (multiplication properties).

<div class="boxed">
<details>
    <summary><b>
    Properties of multiplication
    </b></summary>

Let $x, y, z \in F, \; x \ne 0$ in field $(F, +, \cdot)$. Then the following are true.
<br>
<b>(a)</b> $x \cdot y = x \cdot z \implies y = z.$
<br>
<b>(b)</b> $x \cdot y = x \implies y = 1.$
<br>
<b>(c)</b> $x \cdot y = 1 \implies y = x^{-1}.$
<br>
<b>(d)</b> $(x^{-1})^{-1} = x.$

</details>
</div>


### Proposition 1.16 (other field properties).

<div class="boxed">
<details>
    <summary><b>
    Other field properties
    </b></summary>

Let $x, y, z \in F$ in field $(F, +, \cdot)$. Then the following are true.
<br>
<b>(a)</b> $0 \cdot x = 0.$
<br>
<b>(b)</b> $x, y \ne 0 \implies x \cdot y \ne 0.$
<br>
<b>(c)</b> $(-x)\cdot y = -(x \cdot y) = x \cdot (-y).$
<br>
<b>(d)</b> $(-x)\cdot(-y) = x \cdot y.$

</details>
</div>


### Definition 1.17 (ordered field)

<div class="boxed">
<details>
    <summary><b>
    Ordered field
    </b></summary>

An <b><i>ordered field</i></b> $((F, +, \cdot), <)$ is a <b>field</b> $F$ that is also an <b>ordered set</b> such that $\forall x, y, z \in F$,

<b>(i)</b> $y < z \implies x + y < x + z,$
<br>
<b>(ii)</b> $x, y > 0 \implies xy > 0$.

</details>
</div>


### Definition 1.18 (ordered field properties)

<div class="boxed">
<details>
    <summary><b>
    Properties of an ordered field
    </b></summary>

For any $x, y, z \in F$ of an ordered field $F$:
<br>
<b>(a)</b> $x > 0 \implies -x < 0$ and vice versa.
<br>
<b>(b)</b> $x > 0,\; y < z \implies x \cdot y < x \cdot z.$
<br>
<b>(c)</b> $x < 0,\; y < z \implies x \cdot y > x \cdot z.$
<br>
<b>(d)</b> $x \ne 0 \implies x^2 > 0$.
<br>
<b>(e)</b> $0 < x < y \implies 0 < y^{-1} < x^{-1}$.

</details>
</div>


<!-- 

<div class="boxed">
<details>
    <summary><b>
    Title
    </b></summary>

</details>
</div>

-->

<!-- 

$$\begin{align}
\end{align}$$

-->