Download Link: https://assignmentchef.com/product/solved-csc3102-homework1-avl-versus-simple-binary-search-trees
<br>



<ul>

 <li>Compare Attributes of AVL and Simple Binary Search Trees</li>

</ul>

In class we showed that searching a binary search tree is O(<em>h</em>), where <em>h </em>is the height of the tree. On average, a binary search tree with <em>n </em>keys generated from a random series of insertions has expected height O(lg<em>n</em>). The self-balancing property of an AVL tree generally ensures that its height is shorter than a simple binary search tree for the same series of insertions. The difference in heights between an AVL tree and a binary search tree after inserting sorted data in parallel in the trees is relatively large. Inserting random data in parallel in the trees leads to relatively small difference in height, if any. The choice regarding which tree will give the overall better performance depends on, among other factors, how critical this difference in height is to the performance of the application and also the time that is required to restore balance to an AVL tree after insertion and deletion operations.

In this project you will augment the implementations of a parametric extensible AVL tree and a simple binary search tree abstract data types. You will then write a program that instantiates an AVL tree and a simple binary search tree to store strings. Your program will execute a series of <em>insert</em>, <em>remove </em>and <em>traversal </em>instructions on them. The program will be called <em>HarvestAnalyzer</em>. It will take the name of a <em>command file </em>as a command line argument and execute the instructions in the file while performing a trace of the instructions as they are executed. The command file consists of instructions in one of these formats:

<ol>

 <li><em>insert word</em></li>

 <li><em>remove word</em></li>

 <li><em>traverse</em></li>

</ol>

The <em>insert </em>command in the file is followed by a word. When your program reads this instruction, it inserts the uppercase version of the word into the AVL and binary search trees. Whenever a word is inserted, a message is displayed showing the word that is inserted along with the size and height of each tree and whether the tree is <em>full </em>and <em>complete</em>. Additionally, the number of leaf nodes and their levels, in left-to-right order, are also displayed.

<strong>Definition 1. </strong>The <strong>Level </strong>of a leaf node is the length of the path from the root to the leaf node. Observe that the root node in a tree with only one node is a leaf node and its level is 0.

4 and 1, respectively.

Figure 1: The Levels of the Leaf Nodes

For the command <strong>insert ignominious</strong>, a typical trace would be generated and formatted as shown in Listing 1.

Listing 1: A Sample Trace After Insertion

inserted: IGNOMINIOUS in the AVL inserted: IGNOMINIOUS in the BST

<table width="411">

 <tbody>

  <tr>

   <td width="146">Type: size</td>

   <td width="92">height</td>

   <td width="92">full?</td>

   <td width="80">complete?</td>

  </tr>

  <tr>

   <td width="146">AVL: 1</td>

   <td width="92">0</td>

   <td width="92">true</td>

   <td width="80">true</td>

  </tr>

  <tr>

   <td width="146">BST: 1</td>

   <td width="92">0</td>

   <td width="92">true</td>

   <td width="80">true</td>

  </tr>

 </tbody>

</table>

AVL:

Number of Leaf Nodes: 1

Levels of Leaf Nodes: 0

BST:

Number of Leaf Nodes: 1

Levels of Leaf Nodes: 0

When the <strong>remove </strong>instruction is executed, the program determines the depth of the word in the tree and displays the word, its depth in the tree and then removes the word from the tree. It also displays the size and height of each tree and whether the tree is <em>full </em>and <em>complete</em>. Additionally, the number of leaf nodes and their levels, in left-to-right order, are also displayed. A typical trace would appear in the format shown in Listing 2.

Listing 2: A Sample Trace After Deletion

removed: IGNOMINIOUS from a depth of 0 in the AVL removed: IGNOMINIOUS from a depth of 0 in the BST

<table width="411">

 <tbody>

  <tr>

   <td width="147">Type: size</td>

   <td width="92">height</td>

   <td width="92">full?</td>

   <td width="80">complete?</td>

  </tr>

  <tr>

   <td width="147">AVL: 0</td>

   <td width="92">-1</td>

   <td width="92">true</td>

   <td width="80">true</td>

  </tr>

  <tr>

   <td width="147">BST: 0</td>

   <td width="92">-1</td>

   <td width="92">true</td>

   <td width="80">true</td>

  </tr>

 </tbody>

</table>

AVL:

Number of Leaf Nodes: 0 Levels of Leaf Nodes: N/A

BST:

Number of Leaf Nodes: 0

Levels of Leaf Nodes: N/A

See another example of a trace in Listing 3, this time when there are two of more leaf nodes.

Listing 3: A Sample Trace After Deletion

inserted: ASTUTE in the AVL inserted: ASTUTE in the BST

Type: size       height    full?     complete?

AVL: 8          3         false     false

BST: 8          4         false     false

AVL:

Number of Leaf Nodes: 4

Levels of Leaf Nodes: 2    3   2   2

BST:

Number of Leaf Nodes: 3

Levels of Leaf Nodes: 1    4   3

When the <em>traverse </em>command is executed it performs an in-order traversal of each tree and displays the contents of the trees in tabular format, one word per line, followed by the word count. A typical trace would appear as shown in Listing 4.

Listing 4: A Sample Trace After traverse

AVL (in-order): ASCERTAIN

ASTUTE

BASTION

———————————-word count: 3

BST (in-order): ASCERTAIN

ASTUTE

BASTION

———————————-word count: 3

To run the program, the name of the command file is entered as a command line argument. I have included three sample command text files, <em>smalltrees.ops</em>, <em>sortedtrees.ops </em>and <em>bigtrees.ops</em>, and a text file, <em>smalltrees.out</em>, containing the output that the program should generate when <em>smalltrees.ops </em>is used as the command file. You can use the files with the <em>small </em>prefix to verify the correctness of your program. Your program should also work correctly on <em>bigtrees.ops</em>, <em>sortedtrees.ops </em>and any valid command file. These files are included in the starter code zip archive for the project. Exhaustively test your program including with additional command files. See project files for details on assigned tasks.