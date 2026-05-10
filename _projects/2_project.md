---
layout: page
title: Fluffy - Ontology Alignment System
description: Lexical + Sentence-BERT embedding system for aligning OWL ontologies, evaluated on OAEI benchmark tracks.
img: assets/img/project_img/2.png
importance: 2
category: work
github: https://github.com/SujitBhatta21/fluffy-onto-alignment-system
tech:
  - python/python-original
  - jupyter/jupyter-original-wordmark
  - anaconda/anaconda-original

---

**Fluffy** is an ontology alignment system built for the IN3067/INM713 Web Semantics and Knowledge Graphs coursework. It combines lexical and semantic embedding matching to produce alignments in Turtle (`.ttl`) format, supporting all five OWL alignment predicates.

---

## What It Does

- **Lexical matching** via ISUB substring similarity with an inverted token index for scalability
- **Semantic matching** via Sentence-BERT (`all-MiniLM-L6-v2`) cosine similarity, accelerated with FAISS approximate nearest-neighbour search
- **Combined output** - union of both matchers, deduplicated
- Evaluated across 5 OAEI tracks: Anatomy, Conference, Digital Humanities, Bio-ML, and Knowledge Graph

---

## Key Results

| Track | Avg F-score | Note |
|---|---|---|
| Conference | ~0.37 | Best track - English, readable labels |
| Digital Humanities | ~0.35 | Required SKOS label support fix |
| Anatomy | 0.278 | High recall (0.85), low precision |
| Bio-ML | ~0.11 | Large ontologies, very high recall but poor precision |
| Knowledge Graph | ~0.008 | No `rdfs:label` annotations - label-driven approach fails |

---

## Tech Stack

<p>
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/sentence--transformers-SBERT-FF6F00?style=flat-square&logo=pytorch&logoColor=white" alt="sentence-transformers"/>
  <img src="https://img.shields.io/badge/RDFLib-Ontology-009688?style=flat-square" alt="RDFLib"/>
  <img src="https://img.shields.io/badge/owlrl-OWL_Reasoning-6A0DAD?style=flat-square" alt="owlrl"/>
  <img src="https://img.shields.io/badge/FAISS-ANN_Search-0078D4?style=flat-square" alt="FAISS"/>
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat-square&logo=jupyter&logoColor=white" alt="Jupyter"/>
</p>

---

## Key Highlights

- Added `SKOSAccessor` to handle ontologies using `skos:prefLabel` instead of `rdfs:label`, recovering zero-score Digital Humanities pairs
- Scalable variants of both matchers - token index for lexical, FAISS semantic search for embeddings - completing even the heaviest Bio-ML task in ~17 minutes (well within 2-hour limit)
- Applied OWL-RL reasoning for cross-ontology SPARQL queries over merged alignment graphs