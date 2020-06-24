# Analysing different ACO extensions
This repository contains implementations of various ACO extensions. The code for the base ant system was forked from a repository by [Akvall2](https://github.com/Akavall/AntColonyOptimization/). 


# Data 
The algorithms were run on TSP problems found on [TSPLIB95](http://elib.zib.de/pub/mp-testdata/tsp/tsplib/tsp/index.html)
The oliver30 tsp problem was not in this database. This problem was manually converted to the same format as used in TSPLIB. The data on which the experiments were run can be found in the [tsp](https://github.com/laupijnacker/ACO_NC/tree/master/tsp) folder

# Running a Notebook
To run a notebook, you have to download the tsp problem that you want to test. In the notebooks change the path parameter to the path to the tsp problem(s).
The timelimit used for the problems are shown in the table below

| tsp name  |  timelimit (s)  |
|--|--|
|  ulysses16 | 60  |
|  oliver30  | 180  |
| st70 | 300  |
| eil101| 720 |

# Sample Run

