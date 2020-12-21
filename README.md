# Important notes from https://christophm.github.io/interpretable-ml-book/feature-importance.html
final tree generation is contained within a function that takes bool args or parameters from decision tree parameter optimization note books



# Decision Tree Classifier Parameters

The minimum weighted fraction of the sum total of weights (of all the input samples) required to be at a leaf node. Samples have equal weight when sample_weight is not provided. weights can be provided by permutation importance

## Decision Tree Vocab
Root Node - It represents the entire population or sample and this further gets divided into two or more homogeneous sets.
Splitting - It is a process of dividing a node into two or more sub-nodes.
Decision Node - When a sub-node splits into further sub-nodes, then it is called a decision node.
Leaf/ Terminal Node - Nodes do not split is called Leaf or Terminal node.
Pruning - When we remove the sub-nodes of a decision node, this process is called pruning. You can say the opposite process of splitting.
Branch / Sub-Tree - A subsection of the entire tree is called branch or sub-tree.
Parent and Child Node - A node, which is divided into sub-nodes is called the parent node of sub-nodes whereas sub-nodes are the child of the parent node.
Entropy - A decision tree is built top-down from a root node and involves partitioning the data into subsets that contain instances with similar values (homogeneous). ID 3 algorithm uses entropy to calculate the homogeneity of a sample. If the sample is completely homogeneous the entropy is zero and if the sample is equally divided it has an entropy of one.
Information Gain - The information gain is based on the decrease in entropy after a dataset is split on an attribute. Constructing a decision tree is all about finding an attribute that returns the highest information gain (i.e., the most homogeneous branches).
Internal Node - An internal node (also known as an inner node, inode for short, or branch node) is any node of a tree that has child nodes 
Branch - The lines connecting elements are called "branches".





by
Leo Breiman
https://link.springer.com/article/10.1023%2FA%3A1010933404324
