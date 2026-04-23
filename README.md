<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=13&duration=3000&pause=1000&color=00E5FF&center=true&vCenter=true&width=600&lines=Sentence+Embeddings+%C2%B7+Vector+Database+%C2%B7+RAG+Pipeline;Semantic+Search+%C2%B7+Zero-Shot+Classification;K-Means+Clustering+%C2%B7+UMAP+Visualisation" alt="Typing SVG" />

# Amazon Reviews — NLP Pipeline

**End-to-end NLP system for semantic search, complaint clustering, and automated support triage**

*MSBA Academic Project · University of Arizona · 2026*

<br/>

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![sentence-transformers](https://img.shields.io/badge/sentence--transformers-all--MiniLM--L6--v2-FF6B35?style=flat-square)](https://sbert.net)
[![ChromaDB](https://img.shields.io/badge/ChromaDB-HNSW_Index-E64980?style=flat-square)](https://www.trychroma.com)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-KMeans_·_UMAP-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Colab](https://img.shields.io/badge/Run_in-Google_Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)](https://colab.research.google.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-22C55E?style=flat-square)](LICENSE)

<br/>

</div>

---

## ✦ What This System Does

> Built on **sentence embeddings** and **ChromaDB**, this pipeline turns raw Amazon product reviews into an intelligent support triage system — with **zero labelled training data required**.

<br/>

<div align="center">

| Capability | Method | Result |
|:---|:---|:---:|
| 🔍 **Semantic Search** | Sentence embeddings + ChromaDB HNSW | **87%** Precision@5 |
| 🏷️ **Topic Classification** | Zero-shot cosine similarity | **79%** accuracy |
| 🔵 **Complaint Clustering** | K-Means on embeddings + UMAP | Silhouette **0.41** |
| ⚡ **Priority Triage** | RAG pipeline + heuristics | **74%** time saved |

</div>

<br/>

---

## 📊 Key Results

<div align="center">

```
┌─────────────────────┬─────────────────────┬─────────────────────┬─────────────────────┐
│   Semantic P@5      │  Zero-Shot Accuracy  │   Silhouette Score  │   Triage Saved      │
│       87%           │        79%           │        0.41         │       74%           │
│  +26pp vs keywords  │  no training data    │  good separation    │  ~70 min/agent/day  │
└─────────────────────┴─────────────────────┴─────────────────────┴─────────────────────┘
```

</div>

<br/>

---

## 🗂️ Project Structure

```
Amazon-NLP-pipeline/
│
├── 📓 notebooks/
│   └── Amazon_Review_Insights_NLP.ipynb   — 15-step Colab pipeline
│
├── 📁 outputs/
│   ├── amazon_reviews_labelled.csv        — labelled dataset (500 reviews)
│   ├── cluster_keywords.json              — TF-IDF keywords per cluster
│   ├── eda_overview.png                   — exploratory analysis charts
│   ├── embedding_vectors.png              — 384-dim vector visualisation
│   ├── elbow_silhouette.png               — optimal k selection
│   ├── semantic_search.png                — similarity scores
│   ├── topic_distribution.png             — zero-shot classification
│   ├── summary_dashboard.png              — full pipeline summary
│   └── umap_clusters.html                 — interactive 2D cluster map
│
├── 📄 reports/
│   ├── evaluation_report.html             — interactive evaluation metrics
│   └── business_integration.html          — dashboard · Slack · CRM guides
│
└── 📦 data/
    └── README.md                          — dataset download instructions
```

<br/>

---

## 🔁 Pipeline — 15 Steps

<div align="center">

```
 01  Install dependencies       →   02  Import libraries
 03  Load CSV from local path   →   04  Schema inspection
 05  Explode multi-reviewer rows →  06  Exploratory data analysis
 07  Text pre-processing        →   08  Sentence embeddings (384-dim)
 09  Build ChromaDB vector index →  10  Semantic search + filters
 11  K-Means + UMAP projection  →   12  Zero-shot topic classification
 13  Full RAG pipeline          →   14  Summary dashboard
                    15  Save all outputs
```

</div>

<br/>

```python
# The core function — the entire system in one call
result = rag_pipeline("cable stopped working after 2 days")

# Returns:
# {
#   "topic"    : "Quality Issue",
#   "sentiment": "Negative",
#   "priority" : "HIGH",
#   "action"   : "Route to Quality Control team for defect review.",
#   "retrieved": [ ... 3 similar past reviews with similarity scores ... ]
# }
```

<br/>

---

## 🛠️ Tech Stack

<div align="center">

| Layer | Technology | Purpose |
|:---|:---|:---|
| **Embeddings** | `sentence-transformers/all-MiniLM-L6-v2` | 384-dim dense vectors, free, no API key |
| **Vector DB** | ChromaDB — HNSW index | Cosine similarity search, persisted to disk |
| **Clustering** | `sklearn.KMeans` + `umap-learn` | Unsupervised complaint theme discovery |
| **Classification** | Zero-shot cosine similarity | Topic labelling without training data |
| **Visualisation** | `matplotlib` · `seaborn` · `plotly` | EDA, clustering, dashboard charts |
| **API Layer** | FastAPI | Production wrapper for all integrations |

</div>

<br/>

---

## 🚀 How to Run

**1 — Open the notebook in Google Colab**

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com)

**2 — Get the dataset**

Download `amazon.csv` from Kaggle and upload it when prompted in Step 3:

[![Kaggle Dataset](https://img.shields.io/badge/Kaggle-amazon--sales--dataset-20BEFF?style=flat-square&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset)

**3 — Run cells top to bottom**

```bash
# Each step builds on the previous one
# Step 1  →  Install packages (run once, restart kernel after)
# Step 3  →  Set your CSV_PATH or upload via Colab file picker
# Step 15 →  All outputs saved and zipped for download
```

<br/>

---

## 📋 Interactive Reports

| Report | Description |
|:---|:---|
| [📊 System Evaluation](https://harishdeepak-msba.github.io/Amazon-NLP-pipeline/reports/evaluation_report.html) | Animated metrics — retrieval quality, classification accuracy, clustering coherence, human usefulness |
| [🔗 Business Integration](https://harishdeepak-msba.github.io/Amazon-NLP-pipeline/reports/business_integration.html) | Dashboard · Slack Bot · CRM plugin — architecture diagrams and production code |

> **Live site:** [harishdeepak-msba.github.io/Amazon-NLP-pipeline](https://harishdeepak-msba.github.io/Amazon-NLP-pipeline/)

<br/>

---

## 🔌 Business Integration

The pipeline exposes one function. Any tool that can make an HTTP request can use it.

<details>
<summary><b>📊 Analytics Dashboard (FastAPI + React)</b></summary>

```python
@app.post("/classify")
def classify(req: Ticket):
    result = rag_pipeline(req.text, req.top_k)
    return {
        "topic"    : result["topic"],
        "priority" : result["priority"],
        "action"   : result["action"],
        "retrieved": result["retrieved"],
    }
```
</details>

<details>
<summary><b>💬 Slack Bot (auto-alerts on HIGH priority)</b></summary>

```python
def post_alert(ticket_text):
    result = rag_pipeline(ticket_text)
    if result["priority"] == "HIGH":
        app.client.chat_postMessage(
            channel="#support-alerts",
            text=f"🔴 {result['topic']} — {result['action']}"
        )
```
</details>

<details>
<summary><b>🔗 CRM Plugin (Freshdesk auto-tagging via AWS Lambda)</b></summary>

```python
def lambda_handler(event, context):
    text   = event["ticket_subject"] + " " + event["ticket_description"]
    result = requests.post(NLP_API, json={"text": text}).json()
    requests.put(f"{FRESHDESK}/tickets/{ticket_id}",
                 json={"priority": PRIORITY_MAP[result["priority"]],
                       "tags": [result["topic"]]})
```
</details>

<br/>

---

## ⚠️ Honest Limitations

| Limitation | Detail |
|:---|:---|
| No annotated test set | Accuracy figures are spot-check estimates (50–100 samples), not formally annotated |
| 500-review subset | Full corpus is 10,500+ reviews — Colab CPU limits restricted embedding run |
| English-only model | Hindi transliteration in some reviews may reduce embedding quality |
| Zero-shot ceiling | ~79–82% without fine-tuning; labelled data could push this to 92%+ |
| Static index | ChromaDB must be manually rebuilt when new reviews arrive |

<br/>

---

## 📦 Dataset

**Amazon Sales Dataset** — 1,465 products · 9 categories · ~10,500 individual reviews after extraction

<div align="center">

[![Dataset](https://img.shields.io/badge/Source-Kaggle-20BEFF?style=flat-square&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset)

*The `amazon.csv` file is not included in this repository. See `data/README.md` for download instructions.*

</div>

<br/>

---

<div align="center">

**Built with** `sentence-transformers` · `ChromaDB` · `scikit-learn` · `umap-learn` · `FastAPI` · `plotly`

*University of Arizona · MSBA · NLP Based Insights · 2026*

</div>
