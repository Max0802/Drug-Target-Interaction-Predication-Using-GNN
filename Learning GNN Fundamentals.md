## 1. A Gentle Introduction to Graph Neural Networks
>**Reference Link**: https://distill.pub/2021/gnn-intro/

### Overview

Neural Networks that operate on graph data are called graph neural networks. Practical applications of using GNN include **antibacterial discovery [1]** 3, **physics simulations [2]** 4, **fake news detection [3]** 5, **traffic prediction [4]** 6 and **recommendation systems [5]** 7.

The article explores and explains modern graph neural networks. The work was divided into four parts by authors. 
	1. First, look at the what kind of data is most naturally phrased as a graph with some common examples
	2. Second, explore what makes graphs different from other types of data and some of the specialized choices we have to make when using graphs.
	3. Third, build a modern GNN, walking through each of the parts of the models. Move gradually from a bare-bones implementation to a state-of- the-art GNN model. 
	4. Fourth and finally, the authors provide a GNN playground where you can play around with a real-word task and dataset to build a stronger intuition of how each component of a GNN model contributes to the predictions it makes.

### Establish what a graph is

A graph represents the relations (edges) between a collection of entities (nodes). One graph essentially has 3 components, which are:
	1.  **V** : Vertex (or node) attributes (e.g., node identity, number of neighbors)
	2. **E** : Edge (or link) attributes and directions (e.g., edge identity, edge weight)
	3. **U**: Global (or master node) attributes (e.g., number of nodes, longest path)

To further describe each node, edge or the entire graph, we can store information in each of these pieces of the graph. Here, we have 3 embeddings:
	1.  Vertex (or node) embedding
	2. Edge (or link) attributes and embedding
	3. Global (or master node) embedding

We can additionally specialize graphs by associating directionality to edges (_directed, undirected_).

==The edges can be directed, where an edge **𝑒** has a source node, **𝑣𝑠𝑟𝑐**, and a destination node **𝑣𝑑𝑠𝑡**. In this case, information flows from **𝑣𝑠𝑟𝑐** to **𝑣𝑑𝑠𝑡**. They can also be undirected, where there is no notion of source or destination nodes, and information flows both directions. Note that having a single undirected edge is equivalent to having one directed edge from **𝑣𝑠𝑟𝑐** to **𝑣𝑑𝑠𝑡**, and another directed edge from **𝑣𝑑𝑠𝑡** to **𝑣𝑠𝑟𝑐**.==

### Graphs data

We have some types of graph data, such as social networks, images as graph and text as graphs. For this project purpose, we will skip introducing these types of graph data. We will focusing on molecules as graphs. Molecules graph is more heterogeneously structured. In author's example, the number of neighbors to each node is variable (as opposed to the fixed neighborhood size of images and text).

#### Molecules graphs

 Molecules are the building blocks of matter, and are built of atoms and electrons in 3D space. All particles are interacting, but when a pair of atoms are stuck in a stable distance from each other, we say they share a covalent bond. Different pairs of atoms and bonds have different distances (e.g. single-bonds, double-bonds). It’s a very convenient and common abstraction to describe this 3D object as a graph, where nodes are atoms and edges are covalent bonds. Here are two common molecules, and their associated graphs.
 ![Molecules.png](image)
## Reference List
[1] A Deep Learning Approach to Antibiotic Discovery  Stokes, J.M., Yang, K., Swanson, K., Jin, W., Cubillos-Ruiz, A., Donghia, N.M., MacNair, C.R., French, S., Carfrae, L.A., Bloom-Ackermann, Z., Tran, V.M., Chiappino-Pepe, A., Badran, A.H., Andrews, I.W., Chory, E.J., Church, G.M., Brown, E.D., Jaakkola, T.S., Barzilay, R. and Collins, J.J., 2020. Cell, Vol 181(2), pp. 475--483.
[2] 