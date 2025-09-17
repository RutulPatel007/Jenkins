# Jenkins

Here's a comprehensive review of the provided PDFs on Graph Theory, ordered by date, with detailed explanations of the topics included. This information is drawn directly from your sources to prepare you for your theory exam.

---

### **Overview of Graph Theory Topics (as per Sources)**

The sources cover fundamental concepts in Graph Theory, including:
*   **Basic Definitions**: Graphs, vertices, edges, paths, cycles, complete graphs, bipartite graphs, isomorphism.
*   **Special Graph Types**: Trees, Eulerian graphs, regular graphs, hypercubes, Petersen graph, spanning trees.
*   **Graph Properties and Theorems**: Degree sequences, connectivity, cut-edges, diameter, radius, eccentricity, center of a tree.
*   **Matching and Covering Concepts**: Matchings (perfect, maximal, maximum), M-augmenting paths, independent sets, vertex covers, edge covers, Hall's Theorem, Frobenius' Theorem, Gallai's Theorem.
*   **Graph Codes**: Prufer code.
*   **Graph Invariants**: Wiener Index.

---

### **PDF Review Ordered by Date**

#### **1. Notes-4-August-2025.pdf (CSE 825)**

This document introduces the broad scope of the Graph Theory course (CSE 825) and covers foundational definitions and concepts [1].

*   **Course Structure**: The course involves structural graph theory, basics, trees, optimization problems (min-max) related to matchings, vertex covers, edge covers, independent sets, cuts, connectivity, planar graphs, coloring, and special classes of graphs [1]. The grading includes 40 marks for pre-midterm topics, 40 marks for post-midterm topics, and 20 marks for a seminar, culminating in a quiz + mid-term and quiz + final exam structure [2]. References include "Graph Theory by Douglas West" and "Graph Theory by Diestel" [3].

*   **Königsberg Bridge Problem**: This classic problem is introduced with an illustration of a city divided by a river, connected by bridges, and its abstract representation as a graph with vertices (landmasses) and edges (bridges) [3]. This problem is historically significant as it led to the development of graph theory, specifically Eulerian paths and cycles.

*   **Graph Isomorphism**: This concept states that two graphs are considered the "same" even if they are drawn differently, provided there's a bijection (one-to-one correspondence) between their vertices that preserves adjacency [4]. An example shows two graphs, G and H, that appear different but are isomorphic, with a mapping of vertices demonstrating their equivalence [4].

*   **Paths and Cycles**:
    *   A **path** is a sequence of distinct vertices connected by edges. `P4` (a path with 4 vertices and 3 edges) is shown [5].
    *   A **cycle** is a closed path, where the start and end vertices are the same, and all other vertices are distinct. `C4` (a cycle with 4 vertices and 4 edges) is shown [5].

*   **Complete Graphs**: A **complete graph**, denoted `Kn`, is a simple graph where every pair of distinct vertices is connected by a unique edge [6].
    *   `C1` (a single vertex) is also `K1` [6].
    *   `C2` (two vertices with an edge) is also `K2` [6].
    *   `C3` (a triangle) is also `K3` [6].
    *   Examples of `K4` and `K5` are shown [6]. Complete graphs are a type of **regular graph** [7].

*   **Bipartite Graphs**: A graph is **bipartite** if its vertices can be divided into two disjoint sets, say X and Y, such that every edge connects a vertex in X to one in Y [8]. In other words, there are no edges within X or within Y [8]. An illustration shows vertices partitioned into two groups with edges only between groups [8].

*   **Complete Bipartite Graphs (K_m,n)**: This is a bipartite graph where every vertex in set X (of size m) is connected to every vertex in set Y (of size n) [8]. An example of `K3,2` is provided [8].

#### **2. Notes-6-August-2025.pdf (CSE 825)**

This document delves into enumerating simple graphs, further exploring graph isomorphism, and introducing key theorems related to cycles and graph structure.

*   **Counting Simple Graphs**: For a graph with `n` vertices, the maximum number of possible edges is given by the combination formula `n choose 2`, which is `n(n-1)/2` [9]. Since each of these potential edges can either exist or not exist in a simple graph, the total number of distinct simple graphs on `n` labeled vertices is `2^(n(n-1)/2)` [9]. For example, there are `2^(4*(3)/2) = 2^6 = 64` simple graphs on 4 labeled vertices [10].

*   **Graph Isomorphism Classes**: While there are many distinct graphs, some are structurally identical (isomorphic). The document provides examples of graphs with 4 vertices, showing graphs with zero edges, and one edge (which represents one isomorphism class) [10]. It also illustrates 15 different graphs (implied to be with 4 vertices, despite a label of "2 vertices") and identifies two of their isomorphism classes [11]. Further examples show isomorphism classes for graphs with 3, 4, 5, and 6 edges [12].

*   **Petersen Graph**: This is a specific non-planar graph with interesting properties.
    *   **Vertices**: The Petersen graph has 10 vertices [13]. These vertices can be represented as the 2-element subsets of a 5-element set (e.g., {1,2,3,4,5}) [13]. For instance, the subset {1,2} can be labeled as '12' [14].
    *   **Edges**: An edge exists between two vertices if their corresponding 2-element subsets are disjoint [13].
    *   The document shows two different drawings (visual representations) of the Petersen graph [14, 15]. The Petersen graph is also a **3-regular graph**, meaning every vertex has a degree of 3 [16].

*   **Cut-Edge Theorem**: A **cut-edge** (or bridge) is an edge whose removal increases the number of connected components in the graph [17]. The theorem states that an edge is a cut-edge **if and only if it belongs to no cycle** [17]. Illustrations show an edge whose removal disconnects a graph (a cut-edge) and an edge that is part of a cycle, which would not disconnect the graph if removed [17].

*   **Lemma: Every Closed Odd Walk Contains an Odd Cycle**:
    *   A **walk** is a sequence of alternating vertices and edges. A **closed walk** starts and ends at the same vertex. An **odd walk** is one with an odd number of edges (odd length) [18].
    *   **Proof by Induction**:
        *   **Base Case**: The lemma holds for walks of length 1 (a loop) and length 3 (a triangle) [18].
        *   **Induction Step**: Assume the lemma holds for all closed odd walks up to length `k-1`. Consider a closed odd walk `W` of length `k` [18, 19].
            *   **Case 1**: If `W` itself is a cycle, the proof is complete [19].
            *   **Case 2**: If `W` is not a cycle, it implies that at least one vertex `v` repeats within `W` [19]. If there are two consecutive repetitions of `v`, they form a cycle `Cv`.
                *   If `Cv` is of odd length, then we have found an odd cycle [20].
                *   If `Cv` is of even length, removing it from `W` leaves a shorter walk that is still of odd length [20]. By the induction hypothesis, this shorter odd-length walk contains an odd cycle, which is also an odd cycle in the original walk `W` [20].

#### **3. Notes-11-August-2025.pdf (CSE 825)**

This document focuses on the characterization of bipartite graphs and Eulerian graphs, alongside a lemma about graph cycles.

*   **Theorem: A Graph is Bipartite if and only if it has No Odd Cycles**: This is a fundamental theorem for characterizing bipartite graphs [21].
    *   **Proof (If Bipartite => No Odd Cycles)**:
        *   Assume G is bipartite, meaning its vertices can be partitioned into two sets, X and Y, with edges only between X and Y [21].
        *   Suppose, for contradiction, that G has an odd cycle C [21].
        *   Starting from any vertex `u` in C, traversing the cycle means alternating between vertices in X and Y [21]. For the path to return to `u`, it must have an even length. If the cycle C has an odd length, it would imply that a vertex is connected to another vertex within the same partition (e.g., an edge within X), which contradicts the definition of a bipartite graph [21, 22]. Therefore, a bipartite graph cannot have odd cycles.
    *   **Proof (If No Odd Cycles => Bipartite)**:
        *   Assume G has no odd cycles. We need to show that G is bipartite [22].
        *   Consider a connected component H of G and an arbitrary vertex `u` in H [23].
        *   Define two sets of vertices:
            *   `X`: All vertices `v` such that the minimum length path `f(v)` from `u` to `v` has an **even length** [23].
            *   `Y`: All vertices `v` such that the minimum length path `f(v)` from `u` to `v` has an **odd length** [23].
        *   These two sets (X, Y) form a partition of V(H) [23].
        *   To prove G is bipartite, we must show there are no edges within X and no edges within Y [23].
        *   Suppose, for contradiction, there is an edge `(x, y)` where both `x` and `y` are in X [24]. This means the minimum paths from `u` to `x` and `u` to `y` are both of even length. The path `u ~ x - y ~ u` (combining the path `u` to `x`, the edge `(x,y)`, and the path `y` to `u`) would form a closed walk of odd length [24]. According to the lemma discussed in Notes-6-August-2025.pdf, a closed odd walk contains an odd cycle [18, 24]. This contradicts our initial assumption that G has no odd cycles. Therefore, no edges exist within X (and similarly, no edges exist within Y) [24]. Thus, G is bipartite.

*   **Lemma: If Every Vertex Has Degree at Least 2, then the Graph Contains a Cycle**:
    *   If every vertex in a graph G has a **degree of at least 2** (`deg(u) >= 2` for all `u`), then G must contain at least one cycle [25].
    *   **Proof**: Start at an arbitrary vertex `u` and traverse a path `P` of maximal possible length [25]. Let `v` be the endpoint of this path. Since `deg(v) >= 2`, `v` must have another edge. This edge cannot lead to a new, unvisited vertex (otherwise, `P` wouldn't be maximal). Therefore, this edge must connect `v` to a vertex already in path `P`, thus forming a cycle [25].

*   **Theorem: A Graph is Eulerian if and only if it has at most One Non-trivial Component and all Vertices are of Even Degree**:
    *   An **Eulerian graph** is a graph that contains an Eulerian circuit (a closed trail that visits every edge exactly once) [26].
    *   **Proof (If Eulerian => Properties)**:
        *   If G is Eulerian, it has a closed trail containing all edges [26]. This implies that the graph must be connected, meaning it has at most one non-trivial component [26].
        *   For a closed trail, every time it enters a vertex, it must also leave it. Therefore, each vertex must have an **even number of incident edges**, i.e., an even degree [26, 27].
    *   **Proof (If Properties => Eulerian)**:
        *   Assume G is connected and all vertices have an **even degree** [27].
        *   Since `deg(v) >= 2` for all `v` (as degrees are even and the graph is non-trivial), by the previous lemma, G must contain a cycle C [25, 27].
        *   If this cycle C uses all edges of G, then G is Eulerian [27].
        *   Otherwise, remove the edges of C from G to form `G \ C`. In `G \ C`, all vertices still have even degrees (because two edges incident to each vertex in C were removed) [28]. `G \ C` may be disconnected [28].
        *   By induction hypothesis (on the number of edges), each connected component of `G \ C` is Eulerian and thus has an Euler trail [28].
        *   We can construct an Euler trail in the original graph G by starting at a vertex `u` in one of the components. When traversing the component and reaching a vertex `v` that was part of the removed cycle C, we can "jump" to C along one of its edges from `v`, traverse C, and then return to `v` to continue traversing the component [29]. This process ensures all edges are visited, forming an Eulerian trail in G [29].

#### **4. Notes-13-August-2025.pdf (CS 825)**

This document introduces degree sequences and extensively covers properties and characterizations of trees.

*   **Proposition: Degree Sequence (Handshaking Lemma)**: A sequence of non-negative integers `d1, d2, ..., dn` can be the **degree sequence** of some graph **if and only if the sum of these degrees (Σdi) is an even number** [30].
    *   **Proof Idea (Sufficiency)**: If Σdi is even, you can construct a graph. Create `n` vertices, one for each `di`. One way to form edges is to pair up vertices with odd degrees (since there must be an even number of them if the sum is even) [30]. Add edges between them. For the remaining degrees (which are now all even), or if a degree `di` was even initially, `di/2` self-loops can be added to each vertex to satisfy its degree [31, 32].

*   **Trees**:
    *   **Definition**: A **tree** is an acyclic (no cycles) connected graph [33]. Since trees have no cycles, they inherently have no odd cycles [33]. This directly implies that **all trees are bipartite** [33], based on the theorem from Notes-11-August-2025.pdf.
    *   **Components**: Examples illustrate different tree structures, highlighting **leaves** (vertices of degree 1) and **internal vertices** (vertices with degree greater than 1) [32]. A star graph `K1,5` is also shown as a type of tree [32].

*   **Spanning Tree**: A **spanning tree** of a connected graph G is a subgraph that is a tree and includes all the vertices of G [33]. A graph can have multiple spanning trees; examples are given for a specific graph G [33].

*   **Lemma: Properties of Trees**:
    *   **(1) Every tree with at least two vertices has at least two leaves.** [34].
        *   **Proof Idea**: This can be proven by induction on the number of vertices. A base case of a 2-vertex tree clearly has two leaves. For the induction step, consider how adding a new leaf node to a tree with `k-1` vertices results in a tree, and it maintains at least two leaves [34].
    *   **(2) Deleting a leaf from an `n`-vertex tree gives a tree with `n-1` vertices.** [34].
        *   **Proof**: If `u` is a leaf, its degree is 1. Removing `u` and its single incident edge (`T \ {u}`) results in a graph with `n-1` vertices [35]. This new graph `T \ {u}` remains connected because `u` was a leaf (its removal doesn't disconnect other parts of the graph) [35]. It also remains acyclic, because if `T \ {u}` had a cycle, that cycle would also have existed in the original tree T, which is a contradiction since T is acyclic [36]. Thus, `T \ {u}` is also a tree.

*   **Equivalent Properties Characterizing Trees**: The document outlines several equivalent properties that characterize a tree [36]. These are typically presented as implications proving that if a graph has one property, it also has the others. The specific property "D" is not explicitly defined in the provided source but is implied to mean that there is a **unique path between any two vertices** [37].
    *   **A => {B, C}**: A graph `G` with `n` vertices that is **connected and acyclic** (Property A) has `n-1` edges (Property B) [36].
        *   **Proof**: A graph with `n` vertices and `k` edges has at least `n-k` components [38]. Since `G` is connected, it has 1 component, so `n-k <= 1`, which means `k >= n-1` [38]. If `k` were greater than `n-1`, adding more edges to a connected graph with `n-1` edges would necessarily create a cycle, contradicting `G` being acyclic [38]. Therefore, `k` must be exactly `n-1`.
    *   **B => {A, C}**: A graph `G` with `n` vertices and `n-1` edges (Property B) that is **connected** (Property A part) is acyclic (Property C) [38].
        *   **Proof by Contradiction**: Suppose `G` is connected with `n-1` edges but contains a cycle. If we remove an edge `e` that belongs to this cycle, the graph `G \ {e}` remains connected (as removing an edge from a cycle does not disconnect a graph) and now has `n-2` edges [39]. However, a connected graph with `n` vertices requires at least `n-1` edges. Thus, `G \ {e}` cannot be a connected graph with `n` vertices and `n-2` edges without violating the property that it should have at least `n-k` components. This contradiction implies `G` must be acyclic [39].
    *   **C => {A, B}**: A graph `G` with `n` vertices and `n-1` edges (Property B) that has **no cycles** (Property C) is connected (Property A part) [39].
        *   **Proof**: Suppose `G` has `k` connected components [40]. Since `G` is acyclic, each of its components must also be acyclic. For each component `i` with `Vi` vertices, it must have `Vi-1` edges to be connected and acyclic (a tree) [40]. The total number of edges in `G` is the sum of edges in all components, `Σ(Vi-1)`. Since `ΣVi = n`, the total number of edges is `n-k` [40]. We are given that `G` has `n-1` edges, so `n-k = n-1`, which implies `k=1`. Therefore, `G` has only one connected component, meaning it is connected [40].
    *   **(A => D) & (D => A)**:
        *   **A => D**: If `G` is **connected and acyclic** (Property A), then there is a unique path between any two vertices (Property D) [37]. If there were more than one path between two vertices, these paths would combine to form a cycle, contradicting `G` being acyclic [37].
        *   **D => A**: Conversely, if there is a **unique path between any two vertices** (Property D), then `G` is connected. If `G` had a cycle, one could find at least two distinct paths between certain pairs of vertices within that cycle, contradicting the uniqueness property. Therefore, `G` must be acyclic [37, 41].

#### **5. Notes-20-August-2025.pdf (CSE 825)**

This document focuses on advanced properties of trees and a theorem concerning the diameter of a graph and its complement.

*   **Proposition: Spanning Tree Edge Exchange**:
    *   Let `T` and `T'` be two different spanning trees of a connected graph `G` [42].
    *   If you take an edge `e` that is in `T` but not in `T'` (`e ∈ E(T) \ E(T')`), and an edge `e'` that is in `T'` but not in `T` (`e' ∈ E(T') \ E(T)`), then the graph formed by removing `e` from `T` and adding `e'` (`T \ {e} + {e'}`) is also a spanning tree of `G` [42].
    *   **Caveat**: This proposition does *not* hold for all arbitrary choices of `e` and `e'` [43]. A specific example illustrates how a choice of `e` and `e'` can lead to a graph that is not a tree [43].
    *   **Proof**: When an edge `e` is removed from a tree `T`, `T` becomes disconnected into exactly two connected components (say, `U1` and `U2`), because every edge in a tree is a **cut-edge** [44]. The edge `e` originally connected a vertex `u` in `U1` to a vertex `v` in `U2`. Since `T'` is also a spanning tree of `G`, there must be a path in `T'` that connects `u` and `v` [44]. We can choose `e'` to be any edge from `T'` that lies on this path and connects `U1` and `U2` [44, 45]. By adding `e'` to `T \ {e}`, the graph becomes connected again and remains acyclic (as `e'` was chosen to bridge the two components without forming a cycle with existing edges), thus forming a new spanning tree [45].

*   **Theorem: Diameter of a Graph and its Complement**: For any simple graph `G`, if its **diameter `diam(G)` is greater than 3**, then the **diameter of its complement `diam(G̅)` is less than or equal to 3** [45].
    *   **Diameter**: The maximum eccentricity of any vertex in the graph [46].
    *   **Proof**: If `diam(G) > 3`, it means there exist at least two vertices, say `u` and `v`, in `G` such that the shortest path between them has a length of at least 4 [45]. This implies that `u` and `v` are not adjacent in `G`, and they do not share a common neighbor in `G` (if they did, there would be a path of length 2: `u-w-v`, making the diameter at most 2, contradicting `diam(G) > 3`) [45].
    *   In the **complement graph `G̅`**, an edge `uv` exists because `u` and `v` are not adjacent in `G` [47].
    *   Consider any other vertex `x` in `V(G) \ {u,v}`. Since `u` and `v` do not have a common neighbor in `G`, `x` cannot be a common neighbor. Therefore, `x` must be non-adjacent to at least one of `u` or `v` in `G`. This means that in `G̅`, `x` must be adjacent to at least one of `u` or `v` [47].
    *   This construction ensures that for any pair of vertices in `G̅`, a path of length at most 3 can be found:
        *   If `u` and `v` are the pair, `uv` is an edge (length 1).
        *   If `u` and `x` are the pair, if `ux` is not an edge in `G̅` (meaning `ux` *is* an edge in `G`), then `vx` is an edge in `G̅` (since `u,v` have no common neighbors in `G`). Then `u-y-x` or `u-v-x` path of length 2 or 3 can exist. The source states: "For every pair of vertices in `G̅`, there exists a path of length at most 3" [47]. Thus, `diam(G̅) <= 3` [47].

*   **Graph Metrics Illustrated**:
    *   **Eccentricity `e(v)`**: For a vertex `v`, its eccentricity is the maximum distance from `v` to any other vertex in the graph [46]. The example graph shows the eccentricity labeled for each vertex [46].
    *   **Diameter `diam(G)`**: The maximum eccentricity among all vertices. In the example, `diam(G) = 4` [46].
    *   **Radius `rad(G)`**: The minimum eccentricity among all vertices. In the example, `rad(G) = 2` [46].

#### **6. Notes-25-August-2025.pdf (CSE 825)**

This document focuses on the center of a tree, the Wiener index, and the Prufer code.

*   **Theorem: The Center of a Tree is a Vertex or an Edge**:
    *   The **center of a tree** is the set of vertices (or edges) with minimum eccentricity [48, 49].
    *   **Proof by Induction**:
        *   **Base Case**: For `n=1` vertex, the center is the single vertex itself. For `n=2` vertices (a single edge), the center is that single edge [48].
        *   **Induction Step**: Consider a tree `T` with `n` vertices. Remove all **leaves** (vertices of degree 1) from `T` [50]. The resulting graph, `T'`, is also a tree and has fewer vertices than `T` [50]. By the induction hypothesis, the center of `T'` is either a single vertex or a single edge [50].
        *   The key insight is that the vertices of minimum eccentricity in `T` are the same as those in `T'` [49, 51]. This means the center of `T` is identical to the center of `T'` [49]. While adding the leaves back to `T'` to reconstruct `T` increases the eccentricity of the internal vertices by 1, it doesn't change which vertices have the *minimum* eccentricity [49, 51]. This inductive argument proves that the center of any tree must be a single vertex or a single edge.
        *   **Note**: A maximum length path in a tree always ends in a leaf [49].

*   **Wiener Index `D(T)`**: The Wiener index is a graph invariant that sums the distances between all unordered pairs of vertices in a graph [51]. It's specifically applied to trees here.
    *   **Theorem**: Among all trees with `n` vertices, the Wiener Index `D(T)` is **minimized uniquely by stars** (star graphs) and **maximized uniquely by paths** (path graphs) [51].
    *   **Proof (Minimization by Stars)**:
        *   Examples of star graphs are shown as having minimum `D(T)` values [52].
        *   A tree `T` with `n` vertices has `n-1` edges, meaning `n-1` pairs of vertices are at a distance of 1 [53]. All other pairs are at a distance of at least 2 [53].
        *   In a star graph (`K1,n-1`), all pairs of non-central vertices are at an *exact* distance of 2 (via the central vertex) [53]. This configuration minimizes the total sum of distances [53].
        *   The Wiener index for a star `K1,n-1` is calculated as `D(K1,n-1) = 2(n-1) + 4 * (n-1 choose 2)` [54]. This simplifies to `2(n-1) + 4 * (n-1)(n-2)/2 = 2n-2 + 2(n^2 - 3n + 2) = 2n-2 + 2n^2 - 6n + 4 = 2n^2 - 4n + 2 = 2(n-1)^2` [54].
    *   **Proof (Maximization by Paths)**:
        *   Examples of path graphs are shown as having maximum `D(T)` values [52].
        *   The Wiener index `D(Pn)` for a path graph with `n` vertices can be calculated using a recurrence relation: `D(Pn) = D(Pn-1) + 2 * Σ(i from 1 to n-1)` (This recurrence accounts for adding a new endpoint to a path) [55].
        *   It can be shown by induction that `D(Pn)` is the maximum possible `D` value for any tree with `n` vertices [55]. If a leaf `u` is removed from any tree `T`, `D(T) = D(T-u) + Σ d(u,v)` for `v` in `V(T)` [56]. By induction hypothesis, `D(T-u) <= D(Pn-1)`. The sum `Σ d(u,v)` is maximized when `u` is a leaf in a path graph, leading to `D(T) <= D(Pn)` [56].

*   **Prufer Code**: This is a unique sequence of length `n-2` that acts as a bijection (one-to-one correspondence) between trees on `n` labeled vertices and sequences of length `n-2` of integers from 1 to `n` [57].
    *   **Generation Algorithm**:
        1.  Find the leaf with the smallest label in the current tree.
        2.  Record the label of its unique neighbor into the Prufer code.
        3.  Delete the leaf and its incident edge.
        4.  Repeat steps 1-3 until only two vertices remain.
    *   **Example (with a noted discrepancy in calculation in the source)**: For a tree with `n=8` vertices [57]:
        *   Initial step: Delete leaf '2', add its neighbor '7' to the code. Code: `7` [57].
        *   Next: Delete leaf '3', add its neighbor '4'. Code: `74` [58].
        *   Next: Delete leaf '5', add its neighbor '4'. Code: `744` [58].
        *   Next: Delete leaf '6', add its neighbor '1'. Code: `7441` [59].
        *   *At this point, the source's subsequent steps appear to have calculation errors based on the described rule.* For example, after deleting '6', the leaves are '7' and '8'. The smallest is '7', and its neighbor is '1'. According to the rule, '1' should be added. However, the source shows '7' being added, resulting in `74417` [59]. This seems to be a mistake in the example provided in the source. Regardless of the numerical error in the example, the *method* involves recording the neighbor of the smallest labeled leaf [57]. The final Prufer code given in the source is `744171` [59].

#### **7. Notes-3-Sep-2025.pdf (CSE 825)**

This document focuses on matchings, factors, and their related concepts, including a key theorem on maximum matchings.

*   **Matchings**: A **matching** in a graph `G` is a set of edges where no two edges share a common vertex [60].
    *   **Saturated Vertex**: A vertex is **saturated** by a matching `M` if it is an endpoint of an edge in `M` [60].
    *   **Perfect Matching**: A matching `M` is **perfect** if it saturates all vertices in the graph [60]. A graph with an **odd number of vertices (odd order)** cannot have a perfect matching [61].
        *   Examples of perfect matchings are shown for `K3,3` (a complete bipartite graph) [61] and the Petersen graph [62].
        *   An example of an even-order graph that does *not* have a perfect matching is also provided [63].
    *   **Maximal Matching**: A matching `M` is **maximal** if it cannot be extended by adding any more edges from the graph [63]. (It's not necessarily the largest possible matching). An example on `P6` (a path with 6 vertices) shows a maximal matching (red edges) [63].
    *   **Maximum Matching**: A matching `M` is a **maximum matching** if it has the largest possible number of edges among all possible matchings in the graph [63]. An example on `P6` shows a maximum matching (green edges), which is larger than the maximal matching shown for the same graph [63].

*   **Symmetric Difference of Two Matchings (M1 Δ M2)**:
    *   The symmetric difference `M1 Δ M2` consists of edges that are in `M1` or `M2` but not in both [64].
    *   **Lemma**: Every component of the symmetric difference of two matchings is either a **path or an even cycle** [65].
        *   **Proof**: For any vertex `v` in the graph `G`, at most one edge from `M1` and at most one edge from `M2` can be incident to `v` (since `M1` and `M2` are matchings) [66]. Therefore, in `F = M1 Δ M2`, every vertex `v` can have at most two edges incident to it [66].
        *   Components where every vertex has a degree of exactly 2 must be cycles [66]. These cycles must be of **even length** because edges in `M1 Δ M2` alternate between coming from `M1` and `M2` [67].
        *   Components where vertices have degrees of 0 or 1 must be paths (or isolated vertices) [67].

*   **Theorem: Maximum Matching and M-Augmenting Paths**: A matching `M` in a graph `G` is a **maximum matching if and only if `G` has no M-augmenting path** [67].
    *   An **M-augmenting path** is a path that starts and ends at vertices not saturated by `M` (unsaturated vertices), and whose edges alternate between being in `M` and not in `M` [68]. The path will always have an odd number of edges and the first and last edges are not in M.
    *   **Proof (=> If M is maximum => No M-augmenting path)**:
        *   Assume `M` is a maximum matching, but `G` has an M-augmenting path `P` [68].
        *   By "flipping" the edges along `P` (removing edges of `M` in `P` and adding edges not in `M` in `P`), we can construct a new matching `M' = (M \ E(P)) ∪ (E(P) \ M)` [68, 69].
        *   Because `P` is an augmenting path, it starts and ends with edges *not* in `M`. This "flipping" process adds one more edge to the matching `M'` than was in `M` [69]. This contradicts our initial assumption that `M` was a maximum matching. Therefore, a maximum matching cannot have an M-augmenting path.
    *   **Proof (<= If no M-augmenting path => M is maximum)**:
        *   Assume `M` has no M-augmenting path [69]. We need to show that `M` is a maximum matching.
        *   Let `M'` be any maximum matching in `G`. Consider the symmetric difference `M Δ M'` [69].
        *   Based on the lemma above, every component of `M Δ M'` is either a path or an even cycle [70].
        *   For **even cycle components**, the number of edges from `M` and `M'` in that component must be equal (as edges alternate) [70].
        *   For **path components**: Since `M` has no M-augmenting paths, any path component in `M Δ M'` that starts and ends with edges not in `M` (i.e., augmenting paths for `M`) cannot exist [70]. This implies that the endpoints of these paths must be saturated by `M` [70]. This leads to the conclusion that `M` must have at least as many edges as `M'` [70].
        *   Since `M'` was chosen as a maximum matching, `M` cannot have more edges than `M'`. Therefore, `|M| = |M'|`, meaning `M` is also a maximum matching [71].

*   **Factor of a Graph**: A **factor** of a graph is simply a spanning subgraph (a subgraph that includes all the vertices of the original graph) [72].
*   **k-factor**: A **k-factor** is a spanning subgraph where every vertex has a degree of `k` (it is k-regular) [72]. A perfect matching is an example of a **1-factor** (a spanning subgraph where every vertex has degree 1) [73].

#### **8. Notes-8-Sep-2025.pdf (CSE 825)**

This document details Hall's Marriage Theorem and Frobenius' Theorem, and illustrates the concept of vertex covers.

*   **Hall's Theorem (for Bipartite Graphs)**:
    *   An (X,Y)-bipartite graph (a bipartite graph with partitions X and Y) has a **matching that saturates X** (meaning every vertex in X is an endpoint of an edge in the matching) **if and only if for every subset `S` of `X`, the size of its neighborhood `N(S)` is greater than or equal to the size of `S` (`|N(S)| ≥ |S|`)** [74].
    *   **Proof (Necessary Part =>)**:
        *   Suppose there is a matching `M` that saturates `X` [74].
        *   Consider any subset `S` of `X`. Since `S` is saturated by `M`, all vertices in `S` are matched to distinct vertices in `Y` [74]. These distinct matched vertices must all be within the neighborhood `N(S)`. Therefore, the number of neighbors `|N(S)|` must be at least `|S|` [74].
    *   **Proof (Sufficiency Part <= by Contrapositive)**:
        *   We prove the contrapositive: if `|N(S)| < |S|` for some subset `S` of `X`, then no matching can saturate `X` [75].
        *   Assume, for contradiction, that `M` is a maximum matching in `G` and that `M` does *not* saturate `X` [75]. This means there is at least one vertex `u` in `X` that is not saturated by `M` [75].
        *   Consider all M-alternating paths starting from `u` [76]. Let `S'` be the set of vertices in `X` reachable by these paths, and `T` be the set of vertices in `Y` reachable by these paths [76].
        *   **Claim 1**: The matching `M` matches the set `S' \ {u}` with `T` [76, 77]. This is because M-alternating paths starting from `u` (an unsaturated vertex) will alternate edges `(not in M, in M, not in M, ...)`. The edges *in* `M` connect vertices from `S' \ {u}` to `T`.
        *   **Claim 2**: There is a bijection (one-to-one correspondence) between `S' \ {u}` and `T` [77]. This means `|T| = |S' \ {u}| = |S'| - 1` [78].
        *   **Claim 3**: `T = N(S')` [78]. (The source states `T <= N(S)` and then proves `T = N(S)`). Suppose there is a vertex `y` in `Y \ T` (meaning `y` is not reachable by an M-alternating path from `u`) that is a neighbor of some vertex `v` in `S'` [78]. This would mean an edge `vy` exists. If `vy` is not in `M`, then `u ~ v - y` forms an M-alternating path, making `y` part of `T`, a contradiction. If `vy` is in `M`, then `y` would be saturated by `M` and could potentially lead to an M-alternating path to `u` or be matched to another vertex in `X`. The argument concludes that `T` must be exactly the set of neighbors of `S'` (`N(S')`) [78].
        *   Combining Claim 2 and Claim 3: `|N(S')| = |T| = |S'| - 1`. This results in `|N(S')| < |S'|`, which contradicts Hall's condition for `S'`. Thus, our initial assumption that `M` does not saturate `X` must be false, meaning `M` must saturate `X` if Hall's condition holds.

*   **Frobenius' Theorem (Marriage Theorem)**: For `k > 0`, every **k-regular bipartite graph has a perfect matching** [79].
    *   **Proof**:
        *   In a k-regular bipartite graph with partitions `X` and `Y`, every vertex has degree `k` [79].
        *   The sum of degrees in `X` must equal the sum of degrees in `Y`, and both must equal the total number of edges. So, `k|X| = k|Y|`, which implies `|X| = |Y|` (since `k > 0`) [80].
        *   With `|X| = |Y|` and k-regularity, it can be shown that Hall's condition (`|N(S)| ≥ |S|`) holds for every subset `S` of `X` [80]. (The implicit reasoning is that if `|N(S)| < |S|` for some `S`, then `k|S|` edges must originate from `S`. These edges connect to `N(S)`. If `|N(S)| < |S|`, then the average degree in `N(S)` would have to be greater than `k`, which is impossible if all vertices have degree `k`).
        *   Since Hall's condition holds and `|X| = |Y|`, by Hall's Theorem, there exists a matching that saturates `X`. Since `|X| = |Y|`, this matching must also saturate `Y`, making it a perfect matching [80].

*   **Vertex Cover**: A **vertex cover** in a graph `G` is a set of vertices `C ⊆ V(G)` such that every edge in `G` has at least one of its endpoints in `C` [81].
    *   Examples are given illustrating vertex covers and matchings in different graphs, including non-bipartite and bipartite graphs [81-83]. These examples implicitly show the relationship between the size of a minimum vertex cover and a maximum matching (König's Theorem, although not explicitly named in the sources, is highly relevant here, especially for bipartite graphs).
    *   For graph G1, a matching of size 4 and a vertex cover of size 5 are shown, with a note that no vertex cover of size less than 5 exists [81].
    *   For bipartite graphs G3 and G4, the size of the matching is equal to the size of the vertex cover [82].
    *   For a non-bipartite graph G5, the matching size (2) is less than the vertex cover size (3) [83].

#### **9. Notes-15-Sep-2025.pdf (CSE 825)**

This document focuses on independent sets, edge covers, and theorems relating these concepts to vertex covers and matchings.

*   **Independent Sets & Independence Number**:
    *   An **independent set** (or stable set) `S` in a graph `G` is a set of vertices such that no two vertices in `S` are adjacent (no edge connects any pair of vertices within `S`) [84].
    *   The **independence number `α(G)`** is the maximum size of an independent set in `G` [85]. An example graph shows an independent set {1,2,5,6} with an independence number of 4 [84].

*   **Edge Cover**: An **edge cover** `L` in a graph `G` is a set of edges such that every vertex in `G` is an endpoint of at least one edge in `L` [86]. An example shows an edge cover formed by yellow and red edges, with a size of 4 [86].

*   **Vertex Cover (β(G))**: The **vertex cover number `β(G)`** is the minimum size of a vertex cover in `G` [85].

*   **Relationship between Independent Set and Vertex Cover**:
    *   **Lemma**: In a graph `G`, a set `S` is an independent set **if and only if its complement `S̅` (all vertices not in S) is a vertex cover** [85].
    *   **Proof**:
        *   If `S` is an independent set, then no two vertices within `S` are connected by an edge. Therefore, every edge in the graph must have at least one endpoint outside `S` (i.e., in `S̅`), making `S̅` a vertex cover [85].
        *   Conversely, if `S̅` is a vertex cover, then every edge has at least one endpoint in `S̅`. This means there are no edges connecting two vertices both within `S`, which by definition makes `S` an independent set [85, 87].
    *   **Theorem**: For any graph `G`, the **number of vertices `n(G)` is equal to the sum of its independence number `α(G)` and its vertex cover number `β(G)` (`n(G) = α(G) + β(G)`)** [85, 87]. This is because the complement of a maximum independent set is a minimum vertex cover, and vice versa [87].

*   **Gallai's Theorem**: For a graph `G` **without isolated vertices** (vertices with degree 0), the **number of vertices `n(G)` is equal to the sum of its maximum matching size `α'(G)` and its minimum edge cover size `β'(G)` (`n(G) = α'(G) + β'(G)`)** [87].
    *   `α'(G)` represents the size of the maximum matching [88].
    *   `β'(G)` represents the size of the minimum edge cover [88].
    *   **Proof Outline**:
        *   **(1) Construction from Maximum Matching to Edge Cover**: From a maximum matching `M`, an edge cover `L` can be constructed. `L` consists of all edges in `M` plus an additional edge for each vertex not saturated by `M` (unsaturated vertices) [89]. The size of this edge cover is `|L| = |M| + (n(G) - 2|M|) = n(G) - |M|` [89]. This shows `β'(G) <= n(G) - α'(G)`.
        *   **(2) Construction from Minimum Edge Cover to Matching**: From a minimum edge cover `L`, a matching `M` can be constructed. In a graph formed by `L`, each connected component is a **star graph** [89]. A matching can be formed by picking one edge from each of these star components [72]. The size of this matching `|M|` is `k`, where `k` is the number of stars. The number of vertices `n(G)` can be expressed as `n(G) = |L| + k` (since each edge in L covers 2 vertices, and k is the number of edges picked, some vertices are covered twice or more). The source states `|L| = n(G) - k` (where `k` is the number of stars), implying `k = n(G) - |L|` [72]. This shows `α'(G) >= n(G) - β'(G)`.
        *   By combining these two inequalities, `α'(G) = n(G) - β'(G)`, leading to `n(G) = α'(G) + β'(G)` [88].

*   **Factor and k-factor (Revisited)**:
    *   A **factor** of a graph is a spanning subgraph [72].
    *   A **k-factor** is a spanning subgraph that is `k`-regular (every vertex has degree `k`) [72].
    *   A **perfect matching** is a `1-factor` of a graph [73]. An example illustrates a graph G and its 1-factor [73].

---
Good luck with your theory exam today! Remember to clearly define terms and explain the logic of proofs and theorems based on these notes.