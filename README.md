# Citation Star Map

An interactive 3D scientific citation explorer that transforms a curated corpus of health-science and brain-connectivity research into a navigable star field.

Instead of displaying papers as a traditional network graph, Citation Star Map visualizes research papers as glowing stars in deep space, allowing users to explore citation relationships, co-citation structures, and scientific communities through an immersive Three.js-powered experience.

---

## Features

### True 3D Citation Universe

* Built with Three.js and React Force Graph 3D
* Orbit, zoom, and pan controls
* Auto-rotating camera
* Fullscreen hero experience
* No 2D fallback

### Real Scientific Papers Only

* Retrieves metadata from open scholarly sources
* No fabricated papers
* No fabricated citations
* No synthetic references

### Citation-Based Network Construction

Graph edges are derived exclusively from:

* Direct citations
* Co-citations

If citation density is insufficient, the system falls back to:

* Keyword co-occurrence relationships

Fallback edges are explicitly labeled in the exported dataset.

### Community Detection

* Louvain clustering
* Jewel-colored communities
* Interactive legend filtering

### Interactive Exploration

* Hover communities to isolate clusters
* Click nodes to highlight neighbors
* Detailed paper information panel
* Full abstract display
* Open Paper links

### Visual Effects

* THREE.Sprite radial glow stars
* Unreal Bloom Pass
* Stardust particle field
* Faint gold citation edges
* Deep-space aesthetic

### Downloadable Corpus

Users can download the complete research corpus as a ZIP archive containing:

* Graph data
* Paper metadata
* Reference data

---

## Technology Stack

### Backend

* Python
* FastAPI
* NetworkX
* Python-Louvain
* Pandas
* OpenAlex API

### Frontend

* React
* React Force Graph 3D
* Three.js
* Zustand

---

## Project Structure

```text
citation-star-map/
│
├── backend/
│   ├── app/
│   ├── builder/
│   │   ├── fetch_papers.py
│   │   ├── build_graph.py
│   │   ├── community.py
│   │   └── export_zip.py
│   └── requirements.txt
│
├── frontend/
│   ├── public/
│   ├── src/
│   └── package.json
│
├── data/
│   ├── graph.json
│   └── corpus.zip
│
├── README.md
└── LICENSE
```

---

## Data Integrity Policy

### Allowed

✔ Direct citation edges

✔ Co-citation edges

✔ Keyword fallback edges (explicitly labeled)

### Forbidden

✘ Invented citations

✘ Invented references

✘ Fabricated papers

✘ Synthetic metadata

Every relationship in the graph must be traceable to retrieved source records.

---

## Paper Metadata Schema

```json
{
  "id": "paper_id",
  "title": "Paper Title",
  "authors": ["Author A", "Author B"],
  "abstract": "Abstract text",
  "doi": "10.xxxx/xxxxx",
  "openPaperUrl": "https://...",
  "community": 2,
  "degree": 14,
  "completeness": "full_citation_graph"
}
```

### Completeness Values

* full_citation_graph
* partial_references
* keyword_fallback

---

## Author Compatibility

The application supports both formats:

```javascript
authors: "John Doe"
```

and

```javascript
authors: ["John Doe", "Jane Smith"]
```

using a dedicated utility:

```javascript
getFirstAuthor(authors)
```

---

## Reliability

### Error Boundary

The entire application is wrapped in:

```jsx
<ErrorBoundary>
  <App />
</ErrorBoundary>
```

### Hook Safety

All React hooks execute before any early return conditions to prevent blank screens and runtime failures.

---

## License

MIT License

---

## Vision

Scientific knowledge is often explored through lists, tables, and search engines.

Citation Star Map aims to make scientific literature feel like a discoverable universe—where papers become stars, citation paths become constellations, and research communities emerge as galaxies waiting to be explored.
