# Citation Star Map

**Citation Star Map** is a Python-powered interactive scientific literature explorer that transforms research papers into a navigable 3D universe.

Instead of browsing papers through lists and search results, users can explore scientific knowledge as a constellation of interconnected stars, where each star represents a real research paper and every connection represents a verifiable scholarly relationship.

The project focuses on health science, neuroscience, brain connectivity, and network medicine literature while maintaining strict data integrity standards.

---

## Vision

Scientific knowledge is a network.

Citation Star Map visualizes that network as an explorable galaxy, allowing researchers, students, and curious minds to discover how ideas connect across disciplines.

Every node is a real paper.

Every edge is traceable.

No fabricated citations.

No synthetic metadata.

---

## Key Features

### Real Scientific Literature

* Retrieves papers from scholarly databases
* Uses only real metadata
* Uses only verifiable citation relationships
* Supports DOI and Open Paper links

### Citation Network Construction

The graph is built from:

* Direct citations
* Co-citations

If citation coverage is incomplete:

* Keyword co-occurrence relationships are used as a fallback
* Fallback relationships are explicitly labeled

### Community Detection

* Louvain clustering
* Automatic research-community discovery
* Color-coded scientific domains

### Interactive 3D Exploration

* Orbit navigation
* Zoom controls
* Pan controls
* Auto-rotating camera
* Full-screen immersive visualization

### Research Details Panel

Selecting a paper reveals:

* Title
* Authors
* Abstract
* DOI
* Open access link (when available)
* Data completeness annotation

### Downloadable Corpus

Users can download:

* Paper metadata
* Citation graph
* References
* Research corpus archive

---

# Technology Stack

## Backend

* Python
* FastAPI
* Pydantic
* NetworkX
* Pandas
* NumPy

## Scientific Data

* OpenAlex API
* PyAlex
* Crossref API
* Semantic Scholar API (optional)

## Network Analysis

* NetworkX
* Python-Louvain
* Scikit-learn

## Frontend

Python-first architecture using:

* Reflex

The application minimizes frontend complexity by keeping state management, routing, data processing, and business logic in Python.

## Visualization

* Three.js rendering layer
* WebGL acceleration
* Interactive 3D graph visualization

---

# Project Architecture

```text
citation-star-map/
│
├── app/
│   ├── pages/
│   ├── components/
│   ├── state/
│   └── main.py
│
├── builder/
│   ├── fetch_papers.py
│   ├── build_graph.py
│   ├── communities.py
│   ├── layout.py
│   └── export.py
│
├── data/
│   ├── graph.json
│   └── corpus.zip
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

# Data Integrity Policy

## Allowed Relationships

✔ Direct citations

✔ Co-citations

✔ Keyword-based fallback edges

## Forbidden

✘ Invented citations

✘ Fabricated references

✘ Synthetic papers

✘ Artificial metadata

Every edge must be reproducible from retrieved source data.

---

# Completeness Annotations

Each paper is tagged with one of the following:

| Status              | Meaning                                                    |
| ------------------- | ---------------------------------------------------------- |
| full_citation_graph | Complete citation information available                    |
| partial_references  | Some references available                                  |
| keyword_fallback    | Citation coverage insufficient; keyword relationships used |

---

# Author Compatibility

The system supports both formats:

```python
authors = "John Doe"
```

and

```python
authors = ["John Doe", "Jane Smith"]
```

through a shared utility:

```python
get_first_author(authors)
```

---

# Reliability

## Error Boundary

Application-wide exception handling prevents runtime crashes and blank screens.

## Safe Hook Execution

All state initialization and hooks execute before conditional rendering.

## Reproducible Builds

The graph generation pipeline is deterministic and can be rebuilt from source data.

---

# Research Applications

* Citation analysis
* Literature review
* Knowledge discovery
* Network medicine
* Neuroscience mapping
* Scientific community detection
* Academic exploration

---

# Future Roadmap

* Multi-domain citation maps
* Temporal citation evolution
* Semantic clustering
* Research recommendation engine
* OpenAlex synchronization
* User-generated collections
* Export to Gephi and GraphML

---

# License

MIT License

---

> Mapping scientific knowledge as a navigable universe—one citation at a time.
