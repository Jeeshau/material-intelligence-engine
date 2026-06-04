# Material Intelligence Engine

> An AI-powered material search system for interior design workflows, built with real project data from Bolt Design Group.

## Overview

A full-stack data system that ingests, normalizes, and semantically searches interior design material libraries across multiple projects. Combines structured SQL filtering with vector-based semantic search to enable natural language queries over 227+ real material records.

## Features

- **Multi-source ETL** — Ingests material data from Notion exports and Google Sheets, normalizes heterogeneous schemas into a unified database
- **REST API** — FastAPI backend with 5 endpoints for filtering by category, price, order status, and keyword search
- **AI Semantic Search** — Sentence-transformer embeddings + ChromaDB vector store for natural language queries
- **Image Pipeline** — Auto-fetches product images via Shopify JSON API and og:image metadata
- **Interactive Dashboard** — Streamlit UI with sidebar filters and dual search modes (keyword + AI semantic)

## Tech Stack

| Layer | Technology |
|-------|------------|
| Data Pipeline | Python, Pandas |
| Database | SQLite / PostgreSQL |
| API | FastAPI, Uvicorn |
| Vector Search | ChromaDB, Sentence-Transformers |
| Frontend | Streamlit |
| Deployment | Docker, ngrok |

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /materials | List materials with filters |
| GET | /materials/{id} | Single material detail |
| GET | /categories | All categories with counts |
| GET | /search?q= | AI semantic search |

## Data

- **227 material records** from 2 real interior design projects
- Sources: Alidoro ESB (Empire State Building) + Goodvets 540 Hudson
- Fields: name, category, manufacturer, unit cost, lead time, order status, product images, supplier links

## Background

Built to solve a real workflow problem: material data scattered across Notion, Google Sheets, and supplier PDFs with no unified search. This system consolidates everything into a queryable, AI-searchable library.
