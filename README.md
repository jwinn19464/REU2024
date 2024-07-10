# REU2024

Packages:
dgl version
torch version
rdkit version
numpy version
networkx version

Weighing graphs notebook:
process single sample with function --> return graph, n_feats, label
splits dataset

collate --> returns batched_graph and labels
smiles_to_weighted_graph --> takes in all smiles from graphs in training set
smiles --> RDKit mol --> Adj matrix from RDKit using BO
RDKit adj matrix --> numpy array (print adj matrix as np array)--> unweighted nx graph

for loop transfer adj matrix values into weight attribute of i, j positions in nx graph
--> print edge data of nx graph --> get list of edge tuples (src, dest, weight dict)

pass nx graph and weight attribute to make dgl graph from nx
check adj matrix and weight tensors --> edata['weight'] returns edge weight tensor with weights listed in order that they appear in numpy adj matrix

weighted dgl graph was created from adj matrix

tox21_recent notebook:
Convert Junction Trees to DGLGraph

create junction tree DGLGraph by passing mol_tree to moltree_to_dglgraph --> returns a DGLGraph

Next Step: batch the junction trees and labels and feed to the GNN
junction trees must have node data:
junction tree have 'h' as node data and 'e' as edge data

Edge data taken off for now, potentially add them back via one-hot encoding in dgllife package
Add in the node features, just one-hot encode for now. Worry about avging node features of rings after REU

***************solve RDKit vectInt problem first to get tree decomp.
Look between server and local versions
run a test on local first
