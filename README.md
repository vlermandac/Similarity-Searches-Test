# Weakly Supervised Entity Linking of Article Topics for CiNii.

## 1. Dataset Creation
Considering a subset of the CiNii dataset, we create (weak) labels for the articles.

### 1.1 Topic labels
For now using the Computer Science Ontology. Eventually creating another one.
The topics are represented as a KG.

### 1.2 Label assignment
A label is asigned linking an article node to a topic node.
A link is decided based on:
1. Few exact string matching (expensive).
2. Jaccard with minhash.
3. n-gram inverted index.
4. Graph Kernel score treshold (still evaluating its usability).

### 1.3 Negative sampling
Draw some random topics for the articles that are not already linked with them. 

Finally, we merge the data in a single dataset.

## 2. GNN Training
(TBD) Still looking for a well suited model.

## 3. Article Classification
With the trained model, the goal is to classify the rest of CiNii articles that were not used as dataset.

This classification would be equivalent to perform a Link Prediction Task between all pairs of articles nodes and topics nodes.

All of this will be stored in a annotation layer/graph for easy querying with SPARQL.

## 4. Possible Follow-ups
- Considering also text embeddings to complement the results?