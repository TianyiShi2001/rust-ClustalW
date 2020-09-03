# rust-ClustalW

ClustalW implemented in Rust. When this is completed, it will be added to [rust-bio](https://github.com/rust-bio/rust-bio).


# Algorithm Outline

Given a set of sequences {_S<sub>1</sub>, S<sub>2</sub>, ...S<sub>k</sub>_}, ClustalW performs the following three steps:

1. Compute the optimal alignment for every pair of sequences _S<sub>i</sub>_ and _S<sub>j</sub>_. Then, the distance score of _S<sub>i</sub>_ and _S<sub>j</sub>_ is set to be `1-y/x` where `x` and `y` are the number of non-gap positions and the number of identical positions, respectively, in the alignment between _S<sub>i</sub>_ and _S<sub>j</sub>_.
2. Build the guide tree by hierarchical clustering from the distance matrix.
3. According to the guide tree, perform a series of alignments to align larger and larger groups of sequences.

