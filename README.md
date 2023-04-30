Download Link: https://assignmentchef.com/product/solved-cs213-assignment4-flip-the-bits
<br>
<strong>P1 : Flip the bits </strong>

There are ​<strong>n</strong>​ integers a​1,<sub>​ </sub> a​2<sub>​</sub>, …, an​. Each of those integers can be either <sub>​       </sub><strong>0</strong>​ or ​    <strong>1</strong>​ . You are​     allowed to do <strong>exactly one move</strong>​  :​ choose two indices ​<strong>i</strong>​ and ​<strong>j</strong>​ (1 ≤ i ≤ j ≤ n) and flip all values a​k for which their positions are in range [i,<sub>​       </sub> j] (that is i ≤ k ≤ j). Flipping the value of x means to apply the operation ​x = 1 – x​.

The goal is that, after exactly one move, obtain the maximal number of ones.

<u>Input:</u>

The first line of the input contains an integer ​<strong>n</strong>​ (1 ≤ ​<strong>n</strong>​ ≤ 100).

In the second line of the input there are n integers: a​1,<sub>​ </sub> a​2,<sub>​ </sub> …, a​n. It is guaranteed that<sub>​       </sub> each of those n values is either 0 or 1.

<u>Output:</u>

Print an integer — the maximal number of 1s that can be obtained after exactly one move.

<u>Examples:</u>

<table width="624">

 <tbody>

  <tr>

   <td width="312">Input</td>

   <td width="312">Output</td>

  </tr>

  <tr>

   <td width="312">51 0 0 1 0</td>

   <td width="312">4</td>

  </tr>

  <tr>

   <td width="312">41 0 0 1</td>

   <td width="312">4</td>

  </tr>

 </tbody>

</table>




In the first case, flip the segment from 2 to 5 (i = 2, j = 5). That flip changes the sequence, it becomes: [1 1 1 0 1]. So, it contains four ones. There is no way to make the whole sequence equal to [1 1 1 1 1].

In the second case, flipping only the second and the third element (i = 2, j = 3) will turn all numbers into 1.

<h1>File to be submitted : p1.cpp</h1>

<strong>P2 : Keeping up with the medians </strong>

Consider that integers are read from a data stream. You need to find median of elements read so for in an efficient way. Assume that there will be no duplicates in the stream.

We will simulate the stream and the query mechanism by defining two operations, explained in the input section.

A trivial algorithm to solve this problem is by implementing Insertion sort, thereby maintaining a sorted array to serve the query for the median. If we just ignore the stream, then this approach will have a complexity of O(n​<sup>2</sup>​). But can we do better?

Note that implementing algorithms for such dynamic environments are classified as ​<strong>online algorithms. </strong>If we have a slow algorithm, such as Insertion sort, to process the stream, then the​          algorithm in itself becomes a bottleneck for further processing of the stream. So can we find the medians in O(​<em>nlog(n)</em>​)?

<u>Input</u><u>​</u>:

The first line will contain the number of queries, ​<strong>q</strong>.​

The subsequent ​<strong>q </strong>lines will have the following two type of queries:​

<ol>

 <li><strong>c</strong> ​ ​<em>x</em>​ : Consume integer ​</li>

 <li><strong>m </strong>:​ Print the median so far</li>

</ol>

Assume that the very first query will not be ​<strong>m. </strong>

<u>Output:</u>

Print the median encountered so far whenever ​<strong>m </strong>is encountered​

<u>Example:</u>

<table width="624">

 <tbody>

  <tr>

   <td width="312">Input</td>

   <td width="312">Output</td>

  </tr>

  <tr>

   <td width="312">7 c 5mc 15 c 1mc 3m</td>

   <td width="312">554</td>

  </tr>

 </tbody>

</table>




Initially 5 is the only element consumed, hence the median is 5. After 15 and 1 are consumed, the median remains the same. On the consumption of 3, the median becomes the average of 5 and 3, which is 4

<h1>File to be submitted : p2.cpp</h1>

<strong>P3 : Who are your Ancestors? </strong>

Implement the Binary Search Tree. You can have a look at the Wikipedia of the same : <a href="https://en.wikipedia.org/wiki/Binary_search_tree">https://en.wikipedia.org/wiki/Binary_search_tree</a><a href="https://en.wikipedia.org/wiki/Binary_search_tree">.</a><u>​</u>

Use a node class for building the tree. ​<strong>Revise the concept of pointers and classes before attempting this question.</strong> A typical node structure that can be used is as follows :​

class​ ​Node​{

​public​ ​:​ ​int​ ​value;

​Node​*​ leftChild​;

​Node​*​ rightChild​;

}

You can add additional member variables and member functions depending on the use case that follows. Also you could have used a struct instead of a class for the same application.

You will be given ​<strong>n</strong> positive integers. Using the ​          ​<strong>n</strong> values you have to construct a binary search​           tree. The insertions in the binary search tree are done in the order of occurrence.

Using the constructed Binary Search Tree and given a query node, write a program that prints all the ancestors of the query node in the given binary tree.

A node ​<strong>x</strong> is an ancestor of node ​ ​<strong>y</strong>, iff there is a downstream path from ​ ​<strong>x</strong> to ​ ​<strong>y.  </strong>

<u>Input<strong> :</strong></u><u>​</u><strong>  </strong>

<strong>n</strong> : number of nodes in the tree.​

<strong>n</strong> space separated ​       ​<strong>distinct</strong> integers corresponding to the values of each node.​                <strong>queryNode</strong> : the node whose ancestors are to be printed​

<u>Output</u><u>​<strong>:</strong></u>

n space separated nodes in increasing order of ancestry starting from the queryNode(excluding) to the root.

If the queryNode is the root node or it is not present in the tree, then print ​<strong>-1</strong>.​

<strong><u>Worked out Example:</u></strong>

<u>Input</u><u>​</u> :  n = 4

5 1 3 7

3 <u>Soln</u>​ :

<ul>

 <li>First we insert the node with value 5, the BST looks like :</li>

 <li>Then we insert the value 1, since 1 &lt; 5, it will be the left child of 5 , the tree now looks like:</li>

 <li>Then we insert the value 3, since 3 &lt; 5, we look at the left subtree and since 3 &gt; 1 we insert it at the right subtree of 3.</li>

 <li>While inserting 7, since 7 &gt; 5, we insert it at the right subtree of 5, the final tree now is :</li>

</ul>

Now the query node is that of value 3, looking at the graph we see that the ancestors of 3 are 1 and 5 in order. Therefore the output is : 1 5.

<u>Examples</u><u>​<strong>:</strong></u>

<table width="624">

 <tbody>

  <tr>

   <td width="312"><strong>Input </strong></td>

   <td width="312"><strong>Output </strong></td>

  </tr>

  <tr>

   <td width="312">34 3 63</td>

   <td width="312">4</td>

  </tr>

  <tr>

   <td width="312">41 2 3 44</td>

   <td width="312">3 2 1</td>

  </tr>

  <tr>

   <td width="312">64 5 1 3 6 97</td>

   <td width="312">-1</td>

  </tr>

  <tr>

   <td width="312">823 12 8 9 1 89 13 423</td>

   <td width="312">-1</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<h1>File to be submitted : p3.cpp<strong> </strong></h1>

<strong>P4 : Are you in the loop?</strong>

Given a vertex, check whether it belongs to a loop in the graph. A loop or a cycle is a path of edges and vertices wherein a vertex is reachable from itself.

This problem is important in the field of Computer Networks, as we can afford to remove a router in the network if it belongs to a loop (think why?)

Graph : (V, E), where V : set of vertices number 0 to |V| – 1 and E be the set of edges in the form of tuples : (V​i, V<sub>​       </sub>​j)<sub>​ </sub>, which means there is a directed edge from V​i to V<sub>​                       </sub>​j. There are no self<sub>​            </sub> loops in the graphs. I.e. there are no edges of the form (V​i, V<sub>​              </sub>​i).<sub>​</sub>

(Hint : Read about Depth First Search and Breadth First Search in a graph.)

<u>Input</u><u>​</u> :

n, m : n = |V| : number of vertices, m = |E| : the number of edges;

Next m lines of the form V​i V<sub>​     </sub>j​ which denotes an edge from V<sub>​                  </sub>​i to V<sub>​        </sub>​j. i&lt; n, j&lt; n.<sub>​             </sub> q : the given query vertex, q &lt; n, implies we want to check if V​q is in a loop.<sub>​                       </sub>

<u>Output</u><u>​</u> :

1 : if that vertex is a part of a loop / cycle

0 : otherwise

<u>Examples</u>​ :

<table width="624">

 <tbody>

  <tr>

   <td width="312">Input</td>

   <td width="312">Output</td>

  </tr>

  <tr>

   <td width="312">3 30  11  22  01</td>

   <td width="312">1</td>

  </tr>

  <tr>

   <td width="312">3 30  11  20 21</td>

   <td width="312">0</td>

  </tr>

  <tr>

   <td width="312">4 51  22  12 30 20 11</td>

   <td width="312">1</td>

  </tr>

 </tbody>

</table>

<h1>File to be submitted : p4.cpp</h1>

<strong>P5 : Minimum Spanning Tree (Bonus) : </strong>

Given a completely-connected and undirected graph, a ​<em>spanning tree</em>​ of that graph is a subgraph that is a tree and connects all the vertices together. A single graph can have many different spanning trees. A ​<em>minimum spanning tree (MST)</em>​ or minimum weight spanning tree for a weighted, completely-connected and undirected graph is a spanning tree with weight less than or equal to the weight of every other spanning tree. The weight of a spanning tree is the sum of weights given to each edge of the spanning tree. Completely-connected graph means that there exists an edge between every pair of vertices.

Thus, a minimum spanning tree has (|V| – 1) edges where |V| is the number of vertices in the given graph. The graph has |V|​<sup>2</sup> edges, represented as an adjacency matrix, denoted from now on as ​<strong>adj</strong>​. The adjacency matrix element ​<strong>adj[i][j]</strong> is the weight of the edge going from vertex i to vertex j, here 0 &lt; i, j &lt; |V| – 1. You might notice that in the undirected case, <strong>adj </strong>​is a symmetric matrix.

<u>Input</u>​ :

<strong>N</strong>​ : number of vertices in the graph (|V|)

Next ​<strong>N</strong> lines : each line contains N space separated non negative integers of the adjacency matrix.

(Thus a total of N​<sup>2</sup>​ non negative integers) <u>Output</u>​ :

Output a single integer, which is the sum of the weights of the edges in the MST.

<u>Examples</u>​ :

<table width="624">

 <tbody>

  <tr>

   <td width="312">Input</td>

   <td width="312">Output</td>

  </tr>

  <tr>

   <td width="312">25 00 5</td>

   <td width="312">0</td>

  </tr>

  <tr>

   <td width="312">30 5 15 0 31 3 0</td>

   <td width="312">4</td>

  </tr>

  <tr>

   <td width="312">20 55 0</td>

   <td width="312">5</td>

  </tr>

 </tbody>

</table>

<h1>File to be submitted : p5.cpp</h1>


