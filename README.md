# Similarity Search Approaches for Academic Database

## Indexes to test
### Based on Jaccard (Set) Similarity
1. LSH (Locality Sensitive Hashing) + minhash
2. LSHForest + minhash
3. LSHEnsemble + minhash
### Based on Semantic Similarity
4. LSH + cosine similarity
5. HNSW (Hierarchical Navigable Small World)

## Evaluation
- Create benchmark using LLM.
  - Classification article - topic.
  - Annotate really similar articles.

