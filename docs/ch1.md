<!-- <!DOCTYPE markdown> -->

<!-- border div: https://stackoverflow.com/a/61945876 -->
<!-- markdown: https://stackoverflow.com/a/50974387 -->

<script>
function openDetails() {
    document.body.querySelectorAll('details')
        .forEach((e) => {(e.hasAttribute('open')) ?
        e.removeAttribute('open') : e.setAttribute('open', true);
        console.log(e.hasAttribute('open'))
    })
}
function test() {
    console.log("hello world")
}
</script>
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

    .thm {
    background: #f6d6d2;
    }

    .prop {
    background: #cfd7e1;
;
    }
</style>

<!-- mathjax: https://stackoverflow.com/a/39036912 -->
<script type="text/javascript" charset="utf-8" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML,
https://vincenttam.github.io/javascripts/MathJaxLocal.js">
</script>

<a onclick="openDetails()">Expand details</a>


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

Some notation used not found in <i>Rudin, 3rd ed</i>.

|Symbol                 |Explanation                         |
|:---------------------:|------------------------------------|
|$:=$                   | Defined equivalence.               |
|$\varnothing$          | The empty set.                     |
|$\land$                | And (logical operator).            |
|$\lor$                 | Or (logical operator).             |
|$\forall$              | For all (predicate).               |
|$\exists$              | There exists (predicate).          |
|$P \implies Q$         | If $P$ is true, then $Q$ is true.  |
|$P \longrightarrow Q$  | $P$ is true and $P \Rightarrow Q$ (therefore $Q$ is true). |


## INTRODUCTION

### Definitions 1.3 (sets).

<div class="boxed">
<details><summary><b>Set membership</b></summary><br>

A <b><i>set</i></b> is a collection of objects.

For a set $A$, write $x \in A$ to indicate $x$ is an <b><i>element</i></b> of $A$. Write $x \not\in A$ to indicate $x$ is not an element of $A$.
</details>

<details><summary><b>Subset and superset</b></summary><br><br>

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
<details><summary><b>Common sets</b></summary><br>

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
<details><summary><b>Order relation</b></summary><br>

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

<details><summary><b>Other definitions</b></summary><br>

<b>Less than</b> and <b><i>greater than:</i></b>

$$
    x < y
    \;:=\;
    y > x
    .
$$

<b><i>Weak</i> inequalities:</b>
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
<details><summary><b>Ordered set</b></summary><br>

An <b><i>ordered set</i></b> is a set $S$ in which an order $(<)$ is defined.

</details>
</div>


### Definition 1.7 (upper and lower bound).

<div class="boxed">
<details><summary><b>Upper bound</b></summary><br>

Let $(S, <)$ be an ordered set and $E \subset S$. Then if
$$
    \exists b \in S, \;
    \forall x \in E, \;
    x \le b,
$$
then we say $E$ is <b><i>bounded above</i></b> and call $b$ an <b><i>upper bound</i></b> of $E$.

</details>

<details><summary><b>Lower bound</b></summary><br>

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
<details><summary><b>Supremum</b></summary><br>

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
<details><summary><b>Infimum</b></summary><br>

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
<details><summary><b>Least-upper-bound property (LUBP)</b></summary><br>

An ordered set $(S, <)$ has the <b><i>least-upper-bound property</i></b> if for any $E \subset S$ where $E \ne \varnothing$, 
$$
    \exists b \in S, \; \forall x \in E,\; x \le b
    \implies
    \exists b \in S,\;
    b = \sup E.
$$

</details>
</div>

<br>

<b>Remark:</b> The rationals $\mathbb{Q}$ does <i>not</i> have the LUBP. For example, $E = \left\{x \in \mathbb{Q} : x < \sqrt 2 \right\} \subset \mathbb{Q}$ is bounded above by $\sqrt 2$ but has no supremum in $\mathbb{Q}$.

### Theorem 1.11 (sup LB=GLB).

<div class="boxed thm">
<details><summary><b>Supremum of lower bounds is the greatest lower bound</b></summary><br>

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
    </b></summary><br>

A <b><i>field</i></b> $(F, +, \cdot)$ is a set $F$ with two operations, <b><i>addition</i></b> $(+)$ and <b><i>multiplication</i></b> $(\cdot)$, satisfying the "field axioms" for addition <b>(A)</b>, multiplication <b>(M)</b>, and the distributive law <b>(D)</b>.

<details>
    <summary><b>
    (A) Axioms for multiplication
    </b></summary><br>

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
    </b></summary><br>

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
    </b></summary><br>

$$
    \forall x, y, z \in F, \quad x\cdot(y+z) = x\cdot y + x \cdot z.
$$

</details>
</details>
</div>

### Proposition 1.14 (addition properties).

<div class="boxed prop">
<details>
    <summary><b>
    Properties of addition
    </b></summary><br>

Let $x, y, z \in F$ in field $(F, +, \cdot)$. Then the following are true.
<br>
<b>(a)</b> $x + y = x + z \implies y = z.$
<br>
<b>(b)</b> $x + y = x \implies y = 0.$
<br>
<b>(c)</b> $x + y = 0 \implies y = -x.$
<br>
<b>(d)</b> $-(-x) = x.$

<b>Proof.</b> See page 7 of <i>Rudin, 3rd ed.</i>

</details>
</div>

### Proposition 1.15 (multiplication properties).

<div class="boxed prop">
<details>
    <summary><b>
    Properties of multiplication
    </b></summary><br>

Let $x, y, z \in F, \; x \ne 0$ in field $(F, +, \cdot)$. Then the following are true.
<br>
<b>(a)</b> $x \cdot y = x \cdot z \implies y = z.$
<br>
<b>(b)</b> $x \cdot y = x \implies y = 1.$
<br>
<b>(c)</b> $x \cdot y = 1 \implies y = x^{-1}.$
<br>
<b>(d)</b> $(x^{-1})^{-1} = x.$

<b>Proof.</b> Similar to proof of [Proposition 1.14.](#proposition-114-addition-properties)

</details>
</div>


### Proposition 1.16 (other field properties).

<div class="boxed prop">
<details>
    <summary><b>
    Other field properties
    </b></summary><br>

Let $x, y, z \in F$ in field $(F, +, \cdot)$. Then the following are true.
<br>
<b>(a)</b> $0 \cdot x = 0.$
<br>
<b>(b)</b> $x, y \ne 0 \implies x \cdot y \ne 0.$
<br>
<b>(c)</b> $(-x)\cdot y = -(x \cdot y) = x \cdot (-y).$
<br>
<b>(d)</b> $(-x)\cdot(-y) = x \cdot y.$

<b>Proof.</b> See book.

</details>
</div>


### Definition 1.17 (ordered field)

<div class="boxed">
<details>
    <summary><b>
    Ordered field
    </b></summary><br>

An <b><i>ordered field</i></b> $((F, +, \cdot), <)$ is a <b>field</b> $F$ that is also an <b>ordered set</b> such that $\forall x, y, z \in F$,

<b>(i)</b> $y < z \implies x + y < x + z,$
<br>
<b>(ii)</b> $x, y > 0 \implies x \cdot y > 0$.

</details>
</div>


### Proposition 1.18 (ordered field properties)

<div class="boxed prop">
<details>
    <summary><b>
    Properties of an ordered field
    </b></summary><br>

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

<b>Proof.</b> See page 8 of <i>Rudin, 3rd ed.</i>

</details>
</div>


## THE REAL FIELD

### Theorem 1.19 (existence of R).


<div class="boxed thm">
<details>
    <summary><b>
    The <i>existence theorem</i>
    </b></summary><br>

There exists an ordered field $\mathbb{R}$ which has the [least-upper-bound property](#definition-110-lubp).

Moreover, $\mathbb{R}$ contains $\mathbb{Q}$ as a subfield.

The members of $\mathbb{R}$ are called <b><i>real numbers.</i></b>

<b>Proof.</b> See appendix in page 17 of <i>Rudin, 3rd ed.</i>

</details>
</div>


### Theorem 1.20 (AP and DQ).

<div class="boxed thm">

This theorem contains two important results: the <b><i>archimedean property</i></b> of $\mathbb{R}$ <b>(AP)</b> and the <b><i>density</i></b> of $\mathbb{Q}$ in $\mathbb{R}$ <b>(DQ).</b>

<details>
    <summary><b>
    The archimedean property (AP)
    </b></summary><br>


<b>(a)</b> The <b><i>archimedian property</i></b> states that any positive $x\in\mathbb{R}$ can be added a finite number of times to be greater than any other real number $y \in \mathbb{R}$:
$$
    x, y \in \mathbb{R},
    \quad
    x > 0
    \implies
    \exists n \in \mathbb{N},
    \quad
    n \cdot x = \underbrace{x+ ... +x}_{n \text{ times}} > y.
$$

<details>
    <summary><b>
    Proof of (a).
    </b></summary><br>

Suppose <b>(a)</b> is false, and let $x, y \in \mathbb{R},\; x > 0$ such that
$$
    \forall n \in \mathbb{N}, \quad nx \le y.
$$

Let $\mathbb{N}x = \{nx : n \in \mathbb{N}\} \subset \mathbb{R},$ for which $y$ is an upperbound. Then $\exists b = \sup (\mathbb{N}x) \in R$ by [Theorem 1.19](#theorem-119-existence-of-r).

Since $x > 0$, $b - x < b$ and $b - x$ is not an upperbound of $\mathbb{N}x$. Then
$$\begin{align*}
    \exists m \in \mathbb{N},
    \;
    b - x < mx \in \mathbb{N}x
    &\longrightarrow
    b < mx + x = (m+1)x
    \\
    &\longrightarrow
    b = \sup (\mathbb{N}x) < (m+1)x \in \mathbb{N}x,
\end{align*}$$
which contradicts the definition of $\sup (\mathbb{N}x)$ as an upper bound of $\mathbb{N}x$. $\square$

</details>

</details>

<details>
    <summary><b>
    Density of Q in R (DQ)
    </b></summary><br>

<b>(b)</b> We say that $\mathbb{Q}$ is <b><i>dense</i></b> in $\mathbb{R}$, since there is always a rational $p \in \mathbb{Q}$ that fits between any two real numbers $x, y \in \mathbb{R}$ of distinct order:
$$
    x, y \in \mathbb{R},
    \quad
    x < y
    \implies
    \exists p \in \mathbb{Q},
    \quad
    x < p < y.
$$
<details>
    <summary><b>
    Proof of (b).
    </b></summary><br>

Let $x, y \in \mathbb{R}$ where $x < y$. Then $y - x > 0$.

Let $n \in \mathbb{N}$ where $n \ge 1$ such that by <b>(a)</b>,
$$
    n(y - x) > 1
    \longrightarrow
    nx + 1 < ny.
$$

By <b>(a)</b> again, let $m_1, m_2 \in \mathbb{N}$ where
$$
    m_1 \cdot 1 = m_1 > n x,
    \quad
    m_2 \cdot 1 = m_2 > -nx,
$$
such that $-m_2 < nx < m_1$.

Then there exists a natural $m \in \mathbb{N}$ larger or equal to $nx$ where $-m_2 \leq m \leq m_1$ and
$$\begin{align*}
    m - 1 \le nx < m
    &\longrightarrow
    nx < m < nx + 1 < ny
    \\
    &\longrightarrow
    nx < m < ny
    \\
    &\longrightarrow
    x < \frac{m}{n} < y.
\end{align*}$$

Thus there exists some $p = \frac{m}{n} \in \mathbb{Q}$ where $x < p < y$.

</details>

</details>

</div>

<!-- 

<div class="boxed">
<details>
    <summary><b>
    Title
    </b></summary><br>

</details>
</div>

-->

<!-- 

$$\begin{align}
\end{align}$$

-->
