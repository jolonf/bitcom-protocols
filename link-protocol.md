# Link Protocol

`12UqxsvAW8bwtwQbGzgW3jJWVkuEuq2rGA`
> A reference to another transaction.

References to other transactions can be used for a number of purposes not limited to:
 1. Separating data from the metanet graph. File data can be large, downloading a transaction to access 
the metadata requires downloading all of the data.
 2. Symbolic links similar to filesystem aliases. Allows a user to construct a graph with references to data not owned by the user.
 
# Format

```
12UqxsvAW8bwtwQbGzgW3jJWVkuEuq2rGA
[txid]
[name | ' ']
[mimeHint | ' ']
[protocolHints]
```

The name and protocol hint are optional.

 - `txid` - A valid transaction id
 - `name` - (Optional) A string representing the name of the resource. This could be identical to a name field in the 
 target transaction, or it could be a different name relevant to the owner's graph.
 - `mimeHint` - (Optional) This allows an application to prepare how to view the transaction before requesting the data. This is useful if the application is using another service to retrieve the data (e.g. Bico.Media).
 - `protocolHints` - (Optional) A list of protocol addresses. It may be useful to know the protocol used in the target transaction. The target transaction may consist of multiple protocols, for example a B:// file followed by a DIP protocol. The protocol hint would indicate the relevant protocols which could help in forming the query to retrieve the target transaction.
 
 # Example
 
 ```
12UqxsvAW8bwtwQbGzgW3jJWVkuEuq2rGA
 a3907e5b910f798c8d0fb450d483a0aefa5ce40ac74064b377603e5ea51deccb
 Logo
 image/jpeg
 meta
 19HxigV4QyBv3tHpQVcUEQyq1pzZVdoAut
 ```
The example refers to a transaction which contains a metanet protocol and an image using the B:// protocol.
