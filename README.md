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
