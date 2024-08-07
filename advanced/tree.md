# Tree

> I made this topic separate from the Graph Theory because it contains one or more techniques that are specific to this type of graph

## Definition

Here are some definitions about tree from [CPH ](https://usaco.guide/CPH.pdf)handbook:

Some properties/definitions of trees:

* A graph is a **tree** iff it is connected and contains $$N$$ nodes and $$N−1$$ edges
* A graph is a **tree** iff every pair of nodes has exactly one simple path between them
* A graph is a **tree** iff it is connected and does not contain any cycles

General Tree Terminology:

* A **leaf** of a tree is any node in the tree with degree $$1$$
  * If the tree is rooted, the **root** with a single child is _not_ typically considered a leaf, but depending on the problem, this is not always the case
* A **star graph** has two common definitions. Try to understand what they mean - they typically appear in subtasks.
  * Definition 1: Only one node has degree greater than $$1$$
  * Definition 2: Only one node has degree greater than $$2$$
* A **forest** is a graph such that each **connected component** is a tree

Rooted Tree Terminology:

* A **root** of a tree is any node of the tree that is considered to be at the 'top'
* A **parent** of a node  is the first node along the path from $$n$$ to the **root**
  * The **root** does not have a **parent**. This is typically done in code by setting the **parent** of the **root** to be $$−1$$.
* The **ancestors** of a node are its **parent** and **parent's** **ancestors**
  * Typically, a node is considered its own ancestor as well (such as in the subtree definition)
* The **subtree** of a node $$n$$ are the set of nodes that have $$n$$ as an ancestor
  * A node is typically considered to be in its own subtree
  * Note: This is easily confused with **subgraph**
* The **depth**, or **level**, of a node is its distance from the root

## Traversal

The DFS required to traverse over a tree is simpler - we don't even need a visited array.

```cpp
void dfs(int cur, int par){
    for(auto & a: adj[cur]){
        if(a != par)
            dfs(a, cur);
    }
    // process stuff
}
```
