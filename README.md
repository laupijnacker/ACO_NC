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
Below you can see a sample run of the MEACO notebook
```python
TSP_PATH = "../tsp/"
tsp_name = "ulysses16"
tsp = load_tsp(tsp_name)
n_ants = 16
timelimit= 60

print("ACO")
aco = AntColony(tsp, n_ants=n_ants, timelimit=timelimit)
shortest_path_edges, length = aco.run()
shortest_path = [edge[0]+1 for edge in shortest_path_edges]
print ("shorted_path: {}".format(shortest_path))
print("Length path: {}".format(length))
print()

meaco = AntColony(tsp, n_ants=n_ants, timelimit=timelimit, MEACO= True)
print("MEACO")
shortest_path_edges, length = meaco.run()
shortest_path = [edge[0]+1 for edge in shortest_path_edges]
print ("shorted_path: {}".format(shortest_path))
print("Length path: {}".format(length))
```
The output:
```
ACO
shorted_path: [1, 8, 16, 12, 13, 14, 6, 7, 10, 9, 11, 5, 15, 4, 2, 3]
Length path: 6971.0

MEACO
shorted_path: [8, 1, 14, 13, 12, 7, 6, 15, 5, 11, 9, 10, 16, 3, 2, 4]
Length path: 6859.0
```

