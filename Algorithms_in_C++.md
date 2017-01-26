#Lecture Notes (Rough 1st version):

-----------------

#Algorithms in C++
##Chapter 1:

---------

###History of Algorithsm

1. Euclid's algorithms
2. Church and Turing (1930s) [2]

(To be added more from Wikipedia and other book sources)


###What is an algorithm?

Definition: "...methods for solving problems that are suited for computer implemenation...the stuff of computer science" [1]

method for solving a problem [2]

###What will be covered?

Arrays, stacks, queues, trees, and more [1]

###What is a data structure?

"...Complicated methods of organizing the data..." [1]
"...[result in] the byproducts or endproducts of algorithms"

method to store information [2]

###Why study algorithms?

1. To solve problems that could not otherwise be addressed.
2. For intellectual stimulation. 
3. To become a proficient programmer. 
4. They may unlock the secrets of life and of the universe. 
5. For fun and profit. 
6. Impact are broad and far-reaching
7. Old roots, new opportunities [2]

Internet, Biology, Comptuers, Computer Graphics, Security, Multimedia, Social Networks, Physics [2]

###How do you understand a computer program?

1. managing its complexity
2. decomposing it into smaller subtasks that can be easily implemented

[1]

###Tips and Tricks of Computer Algorithms

1. Don't over-optimize

###steps to develop a usable algorithm

1. Model the problems
2. Find an algorithms to solve it
3. Fast enough? Fits in memory?
4. If not, figure out why.
5. Find a way to address the problem.
6. Iterate when possible.

###Dynamic Connectivity

####What is the union find problem?

An algorithms that finds out if there is a path connecting two objects (verticies).

Function call:
e.g. `connected(0,7)` [2]

####What is the union command?

A union command essentially forces the operation to connect two objects. (Clarify the short-range or long-range connections)

Replace components containing two objects with their union. [2]

Funciton call:
e.g. `union(4,3)` [2]

####What are the applications for the union find algorithm?

Applications involving the following mutating the objects like:
1. Photo pixels
2. Computer networks
3. Social network friends
4. Chip transistors
5. Math elements
6. Fortran variable names
7. System metallic sites [2]

####How do you know that something "is connected to"?

1. Reflexive: 
2. Symmetric: 
3. Transitive: 

####When implementing the operations, what are the problems that need to be addressed?

1. Check if the object pair is in the same component

####What is a component?

###Union Find:

#####Union Find Algorithm and Data Type API:

Goals:
1. Number of objects N can be enormous
2. Number of operations M can be enormous
3. Find queries and union commands may be intermixed [2]

Dynamic connectivity client:

```
public static void main(String[] args)
{
	int N = Stdin.readInt();
	UF uf = new UF(N);
	while (!StdIn.isEmpty())
	{
		int p = StdIn.readInt();
		int q = StdIn.readInt();
		if (!uf.connected(p,q)) {
			uf.union(p,q);
			StdQut.println(p + " " + q);
		}
	}
}
```

####What does this client program do?

1. Reads N objects from standard input
2. Reads in pair of integers from standard inputs
3. Connect them if not connected and print out [2]

####Quick Find (Array-based):

Have a bitmap index where the component is the value with the index being the object or vertex in the graph involved in the union find.

#####What are the problems with this implementation?

1. Part of only one components (no overlaping components) -- multiple values for one index
2. Big Integers needed for web or world-scale graphs (Doesn't scale -- too slow!)
3. Dynamic graph 
4. Insertion 
5. Deletion
6. Array to a linked list (used in many LRU and MFU caching algorithms -- look up)
7. Shard the array among two computers
8. Concurrent union find and connect in parrallel on distributed systems (Graph Databases -- Preagal & GraphLab)

Naive implementation:

```
public class QuickFindUF
{
	private int[] id;
	
	public QuickFindUF(int N) 
	{
		id = new int[N];
		for (int i = 0; i < N; i++) {
			id[i] = 1;
		}
	}
	
	public boolean connected(int p, int q) {
		return id[p] == id[q];
	}
	
	public void union(int p, int q) {
		int pid = id[p];
		int qid = id[q];
		for (int i = 0; i < id.length; i++) {
			if (id[i] == pid) id[i] = qid;
		}
	}
}
```
####


###Fundamentals

ADT - 

Arrays, linked list, stacks, queues, and trees

####Arrays

#####What is an array?

Fixed number of data items that are stored contiguously and that are accessible by an index

#####Pros

1. O(1) asymptotic lookup if it is a bitmap array

#####Cons

1. Size of the array must be known beforehand

###Sorting



###Searching

binary search trees, balanced trees, hashing, digital search trees and tries

###String Processing

File compression, crytography

###Geometric Algorithms

convex hull

###Graph Algorithms

shortest path, MST, network flow, and matching

###Mathematical Algorithms

RNG, Solution of simultaneous equations, data fitting, and integration

###Advanced Topics

dynamic programming, linear programming, exhaustive search, NP-completeness


[1]: Algorithms in C++, Robert Sedgewick, 1992
[2]: https://www.coursera.org/learn/algorithms-part1/lecture/buZPh/course-introduction