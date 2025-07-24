# Similarity Search Approaches for Academic Database

## Data
### Overview
- rdf files representing japanese academic articles ~961 MB.
- Each article might have an english translation 39k english articles, 76k japanese articles.
- From each article we parsed the uri, title and abstract.

### Topic classification
The keyBERT library was used to extract keywords from the abstracts of the articles. The keywords were then used to classify the articles into topics using OpenAI's gpt-4o-mini model.

It takes ~43 minutes to classify all the articles in a M1 macbook air 8GB RAM.

| Field                       | Count |
|-----------------------------|-------|
| Medical and Health Sciences | 1003  |
| Social Sciences             | 992   |
| Arts and Humanities         | 455   |
| Engineering and Technology  | 249   |
| Natural Sciences            | 238   |
| Agricultural Sciences       | 87    |

## Indexes to test
### Based on Jaccard (Set) Similarity
1. LSH (Locality Sensitive Hashing) + minhash
2. LSHForest + minhash
3. LSHEnsemble + minhash
### Based on Semantic Similarity
4. LSH + cosine similarity
5. HNSW (Hierarchical Navigable Small World)

## Evaluation
- Create benchmark using LLM or by hand.
  - Classification article - topic.
  - Annotate really similar articles.

