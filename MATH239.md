#MATH 239

##Compositions

For a positive integer $n$, a **composition** of $n$ is a set of possibly repeated integers $k$. For all $k$ in the composition, $0<k_i\leq{n}$, and their sum is equal to $n$. An integer within a composition is called a **part**.

##Binomial Theorem

\[(a+b)^n=\sum_{k=0}^{n}{n\choose k}a^{n-k}b^k\]

\[(1+x)^n=\sum_{k=0}^{n}{n\choose k}x^k\]

\[(1-x)^{-n}=\sum_{k\geq{0}}{k+n-1\choose n-1}x^k\]

\[\frac{1}{1-x}=1+x+x^2+x^3+\dots{}\]

##Recurrence Relations

Suppose a recurrence relation can be written as a **homogeneous equation**:

\[c_0a_n+c_1a_{n-1}+c_2a_{n-2}+\dots+c_na_0=0\]

where $n\geq{0}$ and all $c_i$ are some constant real number. We can convert the recurrence relation to a **characteristic equation** by using $a_n=r^n$:

\[c_0r^n+c_1r^{n-1}+c_2r^{n-2}+\dots+c_n=0\]

The roots of the characteristic equation (say, P and Q) allow us to explicitly solve the recurrence relation (e.g. $a_n=c_1P^n+c_2P^n$).

##Generating Series

Consider a set $S$ that has elements $\sigma$. A **weight function** $w(\sigma)$ maps all elements in $S$ to some non-negative integer, its **weight**. The **generating series** $\Phi_S(x)$ is a polynomial in the following form, where for each term $a_ix^i$, $a_i$ equals the number of elements in $S$ that have a weight equal to $i$.

\[\Phi_S(x)=a_0x^0+a_1x^1+a_2x^2+...\]

We can prove the equality of two generating series $\Phi_{S_1}$ and $\Phi_{S_2}$ by providing a bijection between sets $S_1$ and $S_2$.

If a generating series has an **inverse**, unless its constant term is 0.

A generating series is also a **power series** if every coefficient is a well-defined number.

###Coefficients of Generating Series

The generating series can also be written as:
\[\Phi_S(x)=\sum_{\sigma\in S}x^{w(\sigma)}\]
We use $[x^n]\Phi_S(x)$ to denote $a_n$, or the $n^{th}$ coefficient of the generating series of $S$. All $i$ values are non-negative integers. Note that $[x^{n-1}]\Phi_S(x)=[x^n]x\Phi_S(x)$.

###Bounded Generating Series

\[\sum_{i=0}x^i=\frac{1}{1-x}\]

\[\sum_{i=0}^{n}x^i=\frac{1-x^{n+1}}{1-x}\]

##Sum Lemma

Consider a set $S$ with generating series $\Phi_S(x)$ and weight function $w(x)$. Suppose $S$ can be divided into disjoint sets $A$ and $B$. If $A$ and $B$ have use the same weight function $w$, then according to the **sum lemma**:

\[\Phi_S(x)=\Phi_A(x)+\Phi_A(x)\]

##Product Lemma

##Binary Strings

#Graphs

###Subgraphs

A subgraph $G'$ of $G$ is called a **spanning subgraph** if it shares the same set (all) of vertices.

##Walks

###Summary

A **walk** of a graph $G$ is an alternating sequence of vertices and edges $v_0,e_1,v_1,e_2,\dots,v_{k-1},e_k,v_k$ in $G$. The length of a walk is the number of its edges.

If all vertices in a walk are distinct, the walk is also a **path**.

If the first and last vertices in a path are identical, then the path is also **cycle**. A cycle that contains every vertex of a graph is called a **Hamilton cycle**.

###Theorems

> If there is a walk from $x$ to $y$ in $G$, then there is also a path.

> If there is a path from $x$ to $y$ and $y$ to $z$ then there is a path from $x$ to $z$.

> If $G$ is a graph where every vertex has degree 2 or more, then $G$ has a cycle.

Consider the longest path in $G$, $v_0\dots{}v_k$. The ends of the path must have degree 2, and must be connected to some vertex in the path (otherwise the 'longest' path could be longer).

> If a graph $G$ has $n\geq{3}$ vertices, and every vertex has degree $\geq{n/2}$, then $G$ has a Hamilton cycle.

##Connectivity

###Summary

A graph is **connected** if for every vertex $x$ and $y$, there exists a walk (equivalently, path) from $x$ to $y$. The following are all connected graphs:

* complete graphs
* complete bipartite graphs (unless one side has no vertices)
* cycles
* n-cubes

A **component** of a graph $G$ is a maximal connected subgraph of $G$; that is, a connected subgraph $H$ of $G$ such that no connected subgraph $H'$ of $G'$ has $H$ as a proper subgraph.

If $(A,B)$ is a partition of the vertex set of a graph $G$ ($A\cup{B}=V$ and $A\cap{B}=\emptyset$), the **cut** induced by $(A,B)$ denotes the set of edges with one end in $A$ and the other end in $B$.

If the cut is also every edge in $G$, then $G$ is bipartite and $(A,B)$ is its partition. If $A\cup{B}$ is non-empty and the cut is empty, then the graph is **disconnected**. Otherwise, the graph is **connected**.

###Theorems

> If $x$ is a vertex of a graph $G$, and for all vertices $y$ of $G$, there is a path from $x$ to $y$, then $G$ is connected.

> If graph $G$ is connected then there does not exist a partition $(A,B)$ such that $A,B\neq{\emptyset}$ and its cut is empty. If a graph $G$ does not have a partition $(A,B)$ such that $A,B\neq{\emptyset}$ and its cut is empty, then $G$ is connected.

##Euler Tours

###Summary

An **Euler tour** is a closed walk that contains every edge exactly once. A graph with an Euler tour is **Eulerian**. Euler tours can only occur in connected graphs.

An edge is a **bridge** if, when removed from the graph, the number of components in the graph increases.

###Properties

> If $G$ is Eulerian, then every vertex of $G$ has an even degree. If every vertex of $G$ has an even degree, then $G$ has an Euler tour.

###Theorems

> Edge $e=uv$ of a graph $G$ is a bridge if $u$ and $v$ are in different components in subgraph $G-e$.

> Edge $e=uv$ is a bridge if and only if it is not contained in a cycle.

> If $x$ and $y$ are vertices of a connected graph $G$ with no bridge, then $G$ contains two edge-disjoint paths (paths that do not share edges, but may or may not share vertices) from $x$ to $y$.

##Trees

###Summary

A **tree** is a connected graph with no cycles. Trees contain some inner vertices, and some 1-degree vertices named **leaves**.

A **spanning tree** of a connected graph $G$ is a subgraph of $G$ that is a tree with the same vertex set as $G$.

###Properties

> A connected graph *G* is a tree if and only if every edge is a bridge.

###Theorems

> Every tree with 2 or more vertices has 2 or more leaves.

A 2-vertex tree has 2 leaves. Every vertex added is always a leaf, and can possibly turn one leaf into a non-leaf. So, added vertices do not decrease the number of leaves.

> If $T$ is a tree with *n* vertices then $T$ has $n-1$ edges.

A 1-vertex tree has no edges. Every added vertex adds exactly 1 edge.

> Trees are bipartite. Prove inductively by removing leaves.

> Every connected graph has a spanning tree. Prove inductively by removing leaves.

> A graph is bipartite if and only if it contains no odd cycle.

##Planarity

###Summary

A graph is **planar** if it can be drawn on a plane so that none of its edges intersect. Such a drawing is a **planar embedding** or **planar map**.

A planar embedding partitions the plane into connected regions called **faces**. This includes an unbounded **outer face**. Face are **adjacent** if they share at least one edge. The vertices and edges that form a face are its **boundary**. A closed walk around a face's perimeter is a **boundary walk**. The length of a boundary walk is the face's **degree**.

###Properties

> A graph is planar if and only if each of its components is planar.

If a component is not planar, it has intersecting edges, and so does the graph. If a graph has an intersecting edge, it must belong to some component, so not all its components are planar.

> A edge cycle in a planar embedding is incident with exactly 2 faces and is contained exactly once in a boundary walk of that face.

> Every edge either contributes 2 degrees to a face (if it is a bridge) or 1 degree to two faces (if it is an edge cycle): $\sum_{f\in{F}}deg(f)=2|E|$

> The average degree of a face in an embedding is $\frac{2|E|}{|F|}$

###Theorems

> A bridge in a planar embedding is incident with exactly 1 face and is contained exactly twice in a boundary walk of that face.

All edges in a tree are bridges, so there are no cycles. The only face is the outer face. The boundary walk of the outer face would cross every edge twice to return to the starting vertex.

> A planar map of a tree has exactly one face of degree $2e=2v-2$.

In a tree, $e=v-1$. The tree also has only one face, so its degree must be $2e$ or $2v-2$.

> In a connected planar graph, $3f\leq{2e}$.

$2e$ represents the sum of all face degrees, and every face has degree at least 3.

> In a connected planar graph with $v\geq{3}$ vertices and $e$ edges, $e\leq{}3v-6$.

Use the result $3f\leq{2e}$ in Euler's formula:
\[2+e-v=f\]
\[6+3e-3v\leq{2e}\]
\[e\leq{3v-6}\]

> A planar connected graph has at least one vertex of degree $\leq{5}$.

$e\leq{3v-6}$, so $\sum_{v\in{V}}deg(V)\leq{6v-12}$. If we divide both sides by $v$, we have the average vertex degree on the left side, and some number between 5-6 on the right side, given $v\geq{1}$. There must be some vertex of degree $\leq{5}$ to produce this average.

##Euler's Formula


> **Euler’s Formula**: let $G$ be a connected graph with $p$ vertices and $q$ edges. If $G$ has a planar embedding with $f$ faces, then $p−q+f=2$.

* $G$ is connected so it has a spanning tree: $q\geq{p-1}$. The theorem holds for a tree since $p-q+f=p-(p-1)+1=2$
* assume $q>p-1$ and assume inductively that Euler’s formula is true for any connected graph on $p$ vertices with fewer than $q$ edges
* if $q>p-1$, $G$ is not a tree, so it contains some non-bridge $e$. With $e$ removed, the graph $G-e$ is still connected, planar and has $p$ vertices. Let the number of faces in $G-e$ be $f'$. Then $p-(q-1)+f'=2$, so $f'=q+1-p$
* by restoring $e$, we are adding one edge and splitting some face, meaning $G$ has $q+2-p$ faces. So $f=q+2-p$, or $p-q+f=2$

> Every planar embedding of a given connected planar graph has the same number of faces.

##Nonplanar Graphs

> The boundary of a face in a planar embedding contains a cycle (unless the embedding is a tree). **Proof**:

> $K_5$ and $K_{3,3}$ are not planar.

> A graph is nonplanar if and only if it has a subgraph that is an edge subdivision of $K_5$ or $K_{3.3}$.

##Kuratowski's Formula



##Fullerenes

A **fullerene** is a planar 3-regular graph.

A graph is **platonic** if it is $d$-regular, $d\geq{3}$ and has an embedding in the plane where all faces have $d^*, d^*\geq{3}$. There are exactly 5 platonic graphs:

|graph|$d$|$d^*$|
|---|---|---|
|tetrahedron|3|3|
|cube|3|4|
|dodecahedron|3|5|
|octahedron|4|5|
|icosahedron|5|3|

\[dv=2e\rightarrow{v=\frac{2e}{d}}\]
\[d^*f=2e\rightarrow{f=\frac{2e}{d^*}}\]
\[v-e+f=2\]
\[\frac{2e}{d}-e+\frac{2e}{d^*}=2\]
\[\frac{2}{d}-1+\frac{2}{d^*}=\frac{2}{e}\]
\[\frac{2}{d}+\frac{2}{d^*}=\frac{2}{e}+1\]

For any $e$, $1+\frac{2}{e}>1$. If $d,d^*\geq{4}$, then $\frac{2}{d}+\frac{2}{d^*}\leq{1}$. At least one of $d,d^*$ needs to be 3. If $d=3,d^*\geq{6}$, then $\frac{2}{d}+\frac{2}{d^*}\leq{1}$. If $G$ is platonic
with vertex degree $d$ and face degree $d^*$, $e=\frac{2dd^*}{2d+2d^*-dd^*}$.

Case 1: $(d,d^*)=(3,3)\rightarrow{e=6,v=4,f=4}$. Tetrahedron ($K_4$)

Case 2: $(d,d^*)=(3,4)\rightarrow{e=12,v=8,f=6}$.

* > If $G$ is connected and not a tree, then the boundary of every face in a planar embedding of $G$ contains a cycle.
* > If $G$ is a connected planar graph with $p$ vertices and $q$ edges, then $q\leq{3p-6}$. If $q>3p-6$ then $G$ is nonplanar.

Consider a planar embedding of $G$ with $p$ vertices, $q$ edges, $r$ faces. By handshake theorem for faces, $2q=\sum_{f\in{F}}\deg{(f)}\geq{3r}$, because each face has degree $\geq{3}$. Then $2q\geq{3r},r\leq{\frac{2}{3}q}$. By Euler's formula,
\[2=p-q+r\]
\[2\leq{p-q+\frac{2}{3}q}\]
\[2\leq{p-\frac{1}{3}q}\]
\[6\leq{3p-q}\]
\[q\leq{3p-6}\]
This proof is not sufficient to prove a graph is planar (only if it is not planar).

We use the terms **dense** and **sparse** to refer to the number of edges in a graph realtive to the number of vertices.

* > If $G$ is a connected planar graph that is not a tree, with $p$ vertices, $q$ edges, and every cycle has length at least $d$, then $q\leq{\frac{d}{d-2}(p-2)}$
* > If $G$ is a connected bipartite graph that is not a tree, with $p$ vertices, $q$ edges, then $q\leq{2p-4}$

A **subdivision** of a graph $G$ is a graph contained by replacing each edge of $G$ by a path of length $\geq{1}$. Imagine inserting vertices directly onto graph edges. Subdividing or 'unsubdividing' a graph has no effect on whether or not the graph is planar.

* > If $H$ is a subdivision of a graph $G$ then $H$ is planar if and only if $G$ is planar.
* > If $H$ is a non-planar graph and $G$ is a graph containing a subdivision of $H$ as a subgraph, then $G$ is non-planar.

**Kuratowski's Theorem**: $G$ is planar if and only if $G$ contains no subdivision of $K_5$ or $K_{3,3}$ as a subgraph.

##Graph Colouring

Let $k\in{N}$. A **k-colouring** of a graph $G=(V,E)$ is a function from $V$ to a set of size $k$ (whose elements are called **colours**) so that adjacent vertices are mapped to differernt colours always. A graph that has a k-colouring is called **k-colourable**. Determining if a graph is k-colourable for $k\geq{3}$ is an NP hard problem.

> $G$ is bipartite if and only if $G$ is 2-colourable. **Proof**: if $G$ is bipartite, let each bipartition be one colour. If $G$ is 2-colourable, let all vertices of one colour belong to one bipartition.

> The complete graph $K_n$ is $n$-colourable but not $k$-colourable for any $k<n$.

> The cycle $C_n$ is 2-colourable if and only if n is even, and is 3-colourable if and only if n is odd

> If $G$ is k-colourable, it is also k'-colourable for all $k'\geq{k}$

**Six-Colour Theorem**: every planar graph is 6-colourable. Use induction on the number of verties. If $G$ has 6 or fewer vertices, the proof is trivial. Suppose for $n\geq{6}$, the theorem holds for every planar graph on $n$ vertices. Let $G'$ be a planar graph on $n+1$ vertices.

Lemma: every planar graph has a vertex of degree $\leq{5}$. Let $G=(V,E)$ be a planar graph . We know $|E|\leq{3|v|-6}$ by lemma. The handshake theorem shows that $2|E|=\sum_{v\in{V}}\deg{(v)}$, so $\frac{\sum{\deg{v}}}{|V|}=6-\frac{12}{|V|}$. So the average degree is less than 6, so $G$ has a vertex of degree $\leq{5}$.

Inductively, $G-v$ has a 6-colouring. Some colour is not used by any neighbour of $v$, assigning this colour to $v$ gives a 6-colouring of $G$.

##Contraction

The $/$ operator (e.g. $Q/e$) means contraction of the edge $e$ in the graph $Q$. $e$ is removed and the endpoints $x,y$ of $e$ become a single vertex. All neighbours of $x$ OR $y$ become a neighbour of ther contraction vertex, $z$.

If $e=xy$ is an edge of a graph $G=(V,E)$, then $G/e$ denotes the gtaph with vertex set $(V|\{x,y\}U\{z\})$ where $z$ is a new vertex not in $V$, and edge set $\{uv:uv\in{E}\text{ and }\{u,v\}\cap\{x,y\}=\emptyset\}$.

* > If $G$ is planar then $G/e$ is planar.
* > Every planar graph is 5-colourable

##Dual Planar Maps

For a planar embedding $G$ (the **primal map**), the **dual planar** $G'$ is constructed as follows:

* $G'$ has one vertex for each face of $G$
* vertices in $G'$ are joined by an edge if their $G$ faces have an edge in common

A dual planar map $G'$ depends on the particular embedding of $G$. There may exist multiple non-isomorphic dual planars $G'$ for a single $G$. A dual planar may be a **multigraph**: a vertex may have multiple edges to another vertex, or even to itself.

> In terms of numbers of edges, faces, and vertices, $e=e',f=v',v=f'$.

> The dual of a dual is the original embedding: $G''=G$.

> Contraction and deletion are dual operators: $(G/e)'=G'\setminus{}e$, and $(G\setminus{}e)'=G'/e$.

> The duals of all platonic graphs are also platonic graphs.

##Matching

A **matching** is an edge subset $M$ of $E$ such that each vertex of $G$ has degree at most 1 (vertices are 'matched'). A vertex incident with an edge of $M$ is **saturated**, otherwise it is **unsaturated**. If every vertex is saturated, then $M$ is a **perfect matching**. Some graphs cannot have a perfect matching (e.g. odd number of vertices), so their largest possible matching is a **maximal matching**.

An **alternating path** is a path in $G$ whose edge sequence alternates between being in and out of a matching $M$ in $G$. If the alternating path begins and ends on distinct, unsaturated vertices, then it is an **augmenting path**.

> Every augmenting path has odd length.

> If a matching has an augmenting path, then $M$ is not a maximum matching.

##Covers

A **cover** is a vertex subset $C$ of $V$ such that every edge of $G$ has at least one end on a vertex in $C$. $V$ is trivially a cover.

> In a bipartite graph with bipartition $(A,B)$, both $A$ and $B$ are covers.

> If $M$ is a matching of $G$ and $C$ is a cover of $G$, then $|M|\leq{|C|}$: since $C$ is a cover, it contains at least one end from each edge in $M$. The ends of these edges are all distinct, so $|C|\geq{|M|}$.

> If $M$ is a matching and $C$ is a cover of $G$, and $|M|=|C|$ then $M$ is a maximum matching and $C$ is a minimum cover. By proposition, every matching $M'$ has size $|M'|\leq{|C|}=|M|$, so $M$ is a maximm matching. Similarly, every cover $C$ has size $|C'|\geq{|M|}=|C|$ so $C'$ is a minimum cover.

##XY Construction



##Hall's Theorem
Let $G$ be a bipartite graph with bipartition $(A,B)$. Then $G$ has a matching saturating $A$ if and only if $|N(A')\geq{|A'|}$ for all $A'\subseteq{A}$, without loss of generality.
