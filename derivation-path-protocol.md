# Derivation Path Protocol

> Represents an heirarchical deterministic path for use primarily with metanet nodes to determine the derived keys.

Metanet node addresses are formed from heirarchical deterministic (HD) keys. The root has the derived key `m/0`, it's children 
have the derived keys `m/0`, `m/1`, `m/2`, and so on. To be able to modify a metanet node, i.e. create a new version of the node,
add children to the node, or modify children of an existing node, the derived private key must be known. To make the metanet graph
self-contained, the derivation paths can be stored directly in the metanet transactions using the proposed protocol.

# Format

```
[protocol id] [derivation path]
```

The derivation path is of the form `m/i/i/i/i...`, where `i` is an integer.

# Example

The following example represents a metanet node with a B:// file and also a derivation path (using pipes):

```
OP_FALSE
OP_RETURN
meta
[node address]
[parent txid]
19HxigV4QyBv3tHpQVcUEQyq1pzZVdoAut // B:// file
[data]
[media type]
[file name]
|
[derivation path protocol]
m/0/1/25/10
```
