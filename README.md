# Using-DFS-to-Complete-a-State-Space-Search-for-the-Water-Jug-Problem-
Please See ReadMe for more info

This program outputs the set of states and the size of the set of states that can be reached from the start state of the water jug problem with jugs of sizes determined by the user.

The water jug problem:

There are 3 jugs that have capacities
of A gallons, B gallons, and C gallons. A pump with an unlimited supply of water is
available which can be used to fill the jugs. Water may be poured from one jug to
another or to the ground. None of the jugs has any measuring marks on it. In the start
state, all the three jugs are empty. This is denoted (0, 0, 0); the first number is the
amount of water in the A-gallon jug, the middle number is the amount of water in the
B-gallon jug, and the last number is the amount of water in the C-gallon jug. For
example, if A=8, B=5, and C=3, a possible next state is (8, 0, 0) which is reached by
pouring water into the 8-gallon jug. From the state (8, 0, 0) a possible next state is (5,
0, 3) which is reached by pouring water from the 8-gallon jug to the 3-gallon jug. From
the state (5, 0, 3) a possible next state is (0, 0, 3) which is reached by pouring water
from the 8-gallon jug to the ground.

The size of each jug is set by the user at the beginning of the program, as the values input for 'A:', 'B:' and 'C:'.

The program can be run by running the JAR file from the command line.





Data Structures used to complete this task:

(Multiple solutions were created and compared, with this being the best one).

Solution 3: The iterative solution, with HashMap.
◊ This used the series of 12 if statements again, along with what was stored in the 
closed list, to judge which successors could be generated and added to the open list.
◊ This used the HashSet to store the closed list again.
◊ This used the LinkedList to represent the open list (stack).
◊ It also used a HashMap to track which states had been added to the open list
(HashMap was used because it has constant access time so allows fast lookup). This
worked by: when a successor was pushed onto the stack, it was also added to the 
HashMap. Now, when a successor is being evaluated to see if it can be generated 
(using the 12 rules to check viability, and the HashSet to see if has already been 
explored), the HashMap is now also checked to see if that state is already waiting to 
be explored in the open list. This means the HashSet doesn’t have to be checked 
when a state is popped from the stack, but the state that is popped does need to be 
removed from the HashMap, in addition to being added to the HashSet (closed list).
The consequence of this is that, for inputs A=1234567, B=765432, C=3:
- The first 1 million states were found in 9.5s (1.5s (19%) slower than in 
solution 2).
- The program ran out of heap space and crashed after finding 8.82 million 
unique states (1.95 million (28%) more unique states found than in solution 
2).
◊ These results led me to choose Solution 3 as the preferred solution, as I believe the 
19% increase in time to find the first 1 million states (due to adding and removing 
from the HashMap) is outweighed by finding 28% more states in total (because the 
stack is kept shorter due to not adding duplicates to it, meaning heap space runs out 
after finding more unique states than it otherwise did in solution 2).
