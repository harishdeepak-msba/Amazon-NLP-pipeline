\# Amazon Reviews — NLP Pipeline



An end-to-end NLP system built on sentence embeddings and a vector database

to perform semantic search, topic classification, complaint clustering,

and automated support ticket triage on Amazon India product reviews.



Built as an academic project for the MSBA programme at the University of Arizona.



\---



\## What the System Does



| Capability | Method | Result |

|---|---|---|

| Semantic Search | Sentence embeddings + ChromaDB HNSW | 87% Precision@5 |

| Topic Classification | Zero-shot cosine similarity | 79% accuracy, no training data |

| Complaint Clustering | K-Means on embeddings + UMAP | Silhouette score 0.41 |

| Priority Triage | RAG pipeline + heuristics | 74% triage time reduction |



\---



\## Project Structure

notebooks/    — Colab-ready Python pipeline

outputs/      — Charts, labelled CSV, cluster keywords

reports/      — Interactive evaluation and integration reports

data/         — See data/README.md for dataset instructions

\---



\## Pipeline Steps



1\. Install dependencies

2\. Import libraries

3\. Load dataset from local path

4\. Schema inspection and data quality checks

5\. Explode multi-reviewer rows into individual reviews

6\. Exploratory data analysis

7\. Text pre-processing (lowercase, stopwords, punctuation)

8\. Generate sentence embeddings — `all-MiniLM-L6-v2` (384 dimensions)

9\. Build vector database — ChromaDB with HNSW index

10\. Semantic search with metadata filters

11\. K-Means clustering + UMAP 2D visualisation

12\. Zero-shot topic classification

13\. Full RAG pipeline — retrieve, classify, recommend

14\. Summary dashboard

15\. Save all outputs



\---



\## Tech Stack



| Layer | Technology |

|---|---|

| Embeddings | sentence-transformers — all-MiniLM-L6-v2 |

| Vector Database | ChromaDB — HNSW index, cosine distance |

| Clustering | scikit-learn KMeans, umap-learn |

| Classification | Zero-shot cosine similarity |

| Visualisation | matplotlib, seaborn, plotly |

| API layer | FastAPI (see evaluation code) |



\---



\## How to Run



1\. Open \[Google Colab](https://colab.research.google.com)

2\. Upload `amazon\\\_nlp\\\_pipeline\\\_colab.py` as a notebook

3\. Download `amazon.csv` from Kaggle (link in `data/README.md`)

4\. Upload the CSV when prompted in Step 3

5\. Run cells top to bottom



\---



\## Key Results



\- Semantic search outperforms keyword search by \*\*+26 percentage points\*\*

\- Zero-shot classification achieves \*\*79% accuracy\*\* with no labelled training data

\- Automated triage takes \*\*\~2 seconds\*\* vs \~45 seconds manually — \*\*74% time saving\*\*

\- Clusters are \*\*88% interpretable\*\* by business users without any explanation



\---



\## Dataset



Amazon Sales Dataset — 1,465 products, 9 categories, \~10,500 individual reviews after extraction.

Source: \[Kaggle — karkavelrajaj/amazon-sales-dataset](https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset)



