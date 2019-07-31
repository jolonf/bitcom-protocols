# Directory Protocol

> A protocol that indicates that the transaction represents a metanet directory.

The metanet is a graph consisting of leaf and non-leaf nodes. If a metanet graph is used to represent a 
filesystem structure it is useful to know if a node is intended to represent a directory. This is useful
for two reasons:
 1. An empty directory, i.e. a node without any children, is indistinguishable from a file.
 2. It makes determining whether a node is a directory simpler by removing the need to check all file protocol possibilities.
 
 # Format
 
 ```
 [protocol address] [name]
 ```
 
 The format simply contains the protocol itself and a name for the directory. Other data can be appended after using pipes.
 
 # Example
 
 The following example is of a metanet node directory including it's derivation path:
 
 ```
 OP_FALSE
 OP_RETURN
 meta
 [node address]
 [parent txid]
 [directory protocol]
 myDir
 |
 [derivation path protocol]
 m/0/1
 ```
