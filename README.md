Our robust journey planner is composed of multiple jupyter notebooks, each of which is there for a specific task. However, they all are independent in the sense that by default the data is loaded from our home directories, to avoid the need of running all notebooks to be able to use the planner. The actual planner is in the file `main.ipynb`. There overall goal is to create the appropriate data structures to be able to easily build the netwrok on which we will run the predictive algorithm, their specific goal is described in the next section.

# The network
## The structure
## How it is built
Concerning the creation of the network, the following diagram illustrate the data pipeline of our project, each rectangle corresponds to a file (either create or present in the hdfs filesystem if it is at the root level) and each ellipse is a notebook.

PUT DIAGRAM

**create_edges_and_nodes**: oaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé d

**create_walking_edges**: oaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé d

**compute_statistics**: oaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé d

**add_statistics_to_edges**: oaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé d

**find_train_type_correspondance**: oaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé d

**main**: oaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé doaiwndpoiawndoaiwnd aiwd poawijdAOI/Dn<éoa ihd<aéo id<aé d

# Predictive algorithm
Dijkstra, les choix quon a fait etc...

# Possible improvements
????