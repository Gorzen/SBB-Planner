Our robust journey planner is composed of multiple jupyter notebooks. They all have a specific purpose (e.g. to create a certain data structure) but act as a whole together. However, they all are independent in the sense that by default the data is loaded from our home directories so each one of them can be run separetely, to avoid the need of running all notebooks to be able to use the planner. The actual planner is in the file `main.ipynb`. The goal of each notebook, except for `main.ipynb`, is to ease the creation of the network used by the predictive algorithm of the planner. They will create intermediate data structures to this aim.

The video presenting the project can be found [here](https://www.youtube.com/watch?v=Z4xStTFRn4g)

# The network
## The structure
The network we use is a directed multigraph (a graph with potentially multiple edges between nodes), with stations as nodes and part of the travel as edges. In other words, nodes are the points in space and edges how someone go from one to another. For example, an edge could be a five minute walk to change from a bus station to a train platform or a travel using any transport; bus, tram, train, etc. If it is an edge related to a transport, it will be an 'atomic part' of travel, so if there is an edge for a train from node A to node B it means that the train does not stop between A and B. Since the planner takes only into account a 15km radius around _Zürich HB_ the number of nodes is reasonable, however for the number of edges to be reasonable we assume that the maximum travel time in this zone is 2 hours and create the network for the 2 hour that precedes the arrival time.

Once the network is built, all the informations needed are contained in it. For the edge corresponding to walking travels, there can only be at most one of them between nodes as we can start to walk at any time, the only informations useful for these edges is the duration. However for a travel using public transport more informations are required: the time of departure, the type of transport, the id of the current transport travel and the duration along with its uncertainty. The id can be used to know if the user has to change transport at a given station platform. The time of departure's use is obvious, this is the principal reason that multiple edges are possible between nodes. The other reason is that the uncertainty we compute depends on the type of transport (bus, tram, but also type of train if it is a train), on which nodes are the end of the travel but also on the hour of the travel. We use this information to get better estimates as the delays will not be the same at 10am or 5pm. For the uncertainty we store the durations corresponding the each possible uncertainty, meaning that we compute a confidence interval for the durations that approximate the duration we have to take into account if we want to be sure at a certain confidence level to be arrived at the station. For the choice of confidence, we choose to use only the following: 0.9, 0.91, 0.92, ..., 0.99. This is because we find that fine grain enough and a lower confidence interval will likely not change the travel, from a user point of view it does not make sense to require a minimum confidence level for its path but to set it to 50%.

## How it is built
Concerning the creation of the network, the following diagram illustrate the data pipeline of our project, each rectangle corresponds to a file (either created or already present in the hdfs filesystem if it is at the root level) and each ellipse is a notebook.

PUT DIAGRAM

**create_edges_and_nodes**: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

**create_walking_edges**: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

**compute_statistics**: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

**add_statistics_to_edges**: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

**find_train_type_correspondance**: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

**main**: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

# Predictive algorithm
- Reverse the network
- (Reversed) dijkstra
- how we handle the probabilities (while the validating does not work, use the confidence interval for the duration in the algorithm)
- ???

# Possible improvements
???

# Contributions
**Marijn Van Der Meer**:

**Lucien Iseli**:

**Florian Ravasi**:

**Jules Gottraux**: