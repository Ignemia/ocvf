# OCVF – Open Curriculum Vitae File Format

OCVF is an open, binary-encoded résumé format designed for reliable parsing, multilingual content, and easy export to PDF, HTML, or JSON. Write your information once, generate any layout you need, and let software handle the rest.

---

## Why OCVF?

- **Automated and Reliable Parsing:** Avoid inconsistent layouts with traditional PDF/DOCX résumés.
- **Data Consistency:** Eliminate repetitive data entry—update once, apply everywhere.
- **Searchable and Structured:** Store information as structured data for seamless integration with automated systems.

By separating content from presentation, OCVF provides a single, loss-free source of truth usable by both machines and humans.

---

## Key Features

- **Binary-Compact Core:** Utilizes length-prefixed blocks for predictable parsing and small file sizes.
- **Multilingual Support:** Each text field supports multiple language variants.
- **Hashtag Tagging:** Inline hashtag skills (e.g., `#Python`) are extracted into structured tags; they remain hidden in exports.
- **Versioned Schema:** Each file declares its specification version; older files are automatically migrated.
- **Extensive Tooling:**
  - **CLI and SDKs:**
    - Rust core (`ocvf-core`)
    - Python bindings (`ocvf-py`)
    - JavaScript/WASM bindings (`ocvf-js`)
- **Smart Search & Ranking:** Filter and score thousands of files with a single command.
- **Web Formatter:** Real-time editor that exports to .ocvf, PDF, or HTML.

---

## Architecture Overview

- **ocvf-core:** Rust-based encoder/decoder and CLI.
- **Python Backend:** FastAPI coupled with WebSocket for seamless server communication.
- **Web Frontend:** Built using Vue or React for an intuitive interface.
- **Bindings:**
  - Python integration via pyo3.
  - JavaScript/WASM integration via wasm-pack.

---

## Quick Start

### Prerequisites

- **Rust:** Version 1.78 or newer.
- **Python:** Version 3.10 or newer.
- **Node.js/npm:** Required for web tooling.

### Installation *(Not implemented yet)*

```sh
cargo install ocvf-core          # Rust encoder/decoder
pip install ocvf                 # Python CLI and bindings
npm install -g ocvf-js           # JavaScript/WASM bindings
```

### Common Commands *(Not ready yet)*

```sh
ocvf encode resume.json -o resume.ocvf
ocvf validate resume.ocvf
ocvf export resume.ocvf --lang en --theme modern -o resume.pdf
ocvf rank resume.ocvf --filters filters.json --explain
```

---

## Repository Layout

- **core/** – Rust crate
- **bindings/py/** – Python bindings and CLI
- **bindings/js/** – JavaScript/WASM bindings
- **web/** – Front-end client
- **api/** – FastAPI backend
- **docs/** – Specification and design notes
- **examples/** – Sample .ocvf files, filters, and themes

---

## Roadmap

1. Publish specification v0.1 along with a reference Rust implementation.
2. Release Python and JavaScript/WASM bindings.
3. Deliver the CLI featuring encode, decode, validate, export, and rank commands.
4. Launch the web formatter with real-time preview capabilities.
5. Add a search server and a dedicated `.well-known/ocvf` discovery endpoint.
6. Provide plugins for VS Code and Microsoft Word.
7. Pilot integrations with ATS systems and LinkedIn.
