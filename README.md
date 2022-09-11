# SageMath GSOC Final Submission

This document serves as the final submission of the GSOC'22 project <Edge connectivity and edge disjoint spanning trees in digraphs>. This will likely be updated as I plan to keep working on this project beyond Summer of Code.

## The Arc

My proposal, which can also be seen in this repository, was for code to find edge connectivity within SageMath's graphs module. By the time Summer of Code started, that project had already been completed by my mentor, so a scope change was necessary. The first place I looked for a new project was the TO-DOs of the edge_connectivity file that was being merged. 

While we evaluated new project ideas, I read the relevant portions of [Anupam Gupta's Advanced Algorithms](https://www.cs.cmu.edu/~15850/notes/cmu850-f20.pdf) as well as studied more closely [Gabow's A Matroid Approach to Finding Edge Connectivity and Packing Arborescences](https://doi.org/10.1006/jcss.1995.1022) and [Anand Bhalgat, Ramesh Hariharan, Telikepalli Kavitha and Debmalya Panigrahi's Fast edge splitting and Edmonds' arborescence construction for unweighted graphs](https://users.cs.duke.edu/~debmalya/papers/soda08-splitting.pdf).

Some of the options we considered were implementing the tree-packing algorithms proposed in Gabow's work, extending the code to digraphs with multiple edges, and extending to weighted digraphs. At first, I looked into extending to multiple edges and/or to weighted graphs as this seemed like a more incremental task than implementing the tree-packing algorithm but quickly discovered that published research in these areas was very limited and ultimately not within what could be accomplished in a summer.
  
Ultimately, we changed the scope to implementing the tree-packing algorithms proposed in Gabow's work. Fortunately, I was also able to work from a recently published [<Experimental Study of Algorithms for Packing Arborescences>](https://drops.dagstuhl.de/opus/frontdoor.php?source_opus=16548) from a group at the University of Ioannina. 

### Key Challenges

Key challenges I experienced included a number of small, but pestering technical issues as well as larger issues related to the fundamental project. 
  
At the beginning of the project, I got a new computer. Unfortunately, it was challenging to compile sage on my new computer as the sage install process has not yet been optimized for Mac M1 chips. On the smaller side, I was unable for some time to push to and pull from the Sage Trac server. To solve this problem, I turned the the sage-devel Gogole Group for help and after a number of back and forths solved the problem. In trying to solve the problem, I had to uninstall and reinstall sage, which posed additional problems. 
  
More fundamentally, I struggled to understand all of Gabow's algorithm for some time, in particular the Augment Step and later the merging of sets. Understanding the algorithm and then the code that implemented in C++ posed a significant challenge.
  
  
### The Work

The work began by understanding the flow of the two different codebases and the mapping of various different variable names between the codebases. 



## Usage
  
Gabow's packing algorithm can be called from the edge connectivity file.


### Once Merged
  
Once the ticket is merged into SageMath development (and then eventually standard release), the code can be called by instantiating a graph.


## To-Do

At this point, all functionality is implemented and compiles but has not been tested and will likely not function as intended until further work is done. In the next few weeks and months, I plan to continue working on the code until it has reached a merge-able state. 
