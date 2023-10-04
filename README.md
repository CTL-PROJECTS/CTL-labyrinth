# CTL-labyrinth

related reference: https://journals.aps.org/pre/abstract/10.1103/PhysRevE.84.046703

## representation

Consider a regular two-dimensional *N* x *N* grid of nodes (grid constant 1) that serve to connect the pathway. i.e., one visits adjacent nodes while walking through a maze. Each of the *N*<sup>2</sup> nodes has four next neighbors to which it can either be connected by a bond, or unconnected. Boundary nodes thus have bonds that point outwards of the grid. All these boundary bonds are disconnected (inactive, passive), with the exception of the maze entry and exit bonds that are connected (active) to the outside world. If one enters a maze through the entry bond one immediately meets a node, the so-called entry node. As soon as one has reached the exit node, one can use the exit bond to leave the maze. Node positions within a labyrinth may be denoted by a pair (*x,y*), where *x* and *y* are integers in 1,..,*N*. A labyrinth is therefore specified by *N*, the entry and exit pairs such as *n*<sub>entry</sub>=(5,1) and *n*<sub>exit</sub>=(5,N), and a number of active bonds between two pairs like (1,3)<->(2,3) and (2,3)<->(2,4). Let us denote the number of bonds by *B* and the bond pairs by *n*<sub>1</sub>(j) and *n*<sub>2</sub>(j) where j=1,..,B. For the previous example, the first bond has *n*<sub>1</sub>(1)=(1,3), *n*<sub>2</sub>(1)=(2,3) and the 2nd bond has *n*<sub>1</sub>(2)=(2,3), *n*<sub>2</sub>(2)=(2,4). The solution of a maze is a sequence of bond numbers, such as [4,10,13,2,1,9,21], where the first bond number (here: 4) has either *n*<sub>1</sub>(4)=*n*<sub>entry</sub> or *n*<sub>2</sub>(4)=*n*<sub>entry</sub> while the last bond number (here: 21) has either *n*<sub>1</sub>(21)=*n*<sub>exit</sub> or *n*<sub>2</sub>(21)=*n*<sub>exit</sub>, and the intermediate bonds should be connected.

## def create_labyrinth(N)

This function creates and returns *n*<sub>entry</sub>, *n*<sub>exit</sub>, *B*, *n*<sub>1</sub>(1), *n*<sub>2</sub>(1), *n*<sub>1</sub>(2), *n*<sub>2</sub>(2), ..., *n*<sub>1</sub>(B), *n*<sub>2</sub>(B) by randomly choosing, with 50% probability, potential bonds to be active or broken. There are 2*N(N+1)* bonds in total. As described, *4N-2* of the boundary bonds are passive (all *4N* but the entry and exit), the remaining bonds can be either active (bonded) or passive (non-bonded or non-existent). Using this algorithm, some mazes may remain unsolvable, others may have several different solutions, there might also be loops and nodes that cannot be reached from the entry.    



## Draw the labyrinth

Draw the created labyrinth as follows. Active bonds are drawn as black lines connecting the bonded nodes. Walls corresponding to passive bonds are drawn as lines of length 1, perpendicular to the passive bond, and centered at the middle of the bond. 
