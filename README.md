# OCVF – Open Curriculum Vitae File

> OCVF is an open, binary-encoded résumé format designed for reliable parsing, multilingual content, and easy export to PDF, HTML, or JSON. Write your information once, generate any layout you need, and let software handle the rest.

-------------------------------------------------------------------------------

## WHY OCVF?

* Existing PDF\/DOCX résumés break automated parsers.
* Job seekers retype the same data for every application.
* Recruiters lack a consistent, searchable database of candidates.

> OCVF stores structured data instead of presentation, so both humans and machines share a single, loss-free source of truth.

-------------------------------------------------------------------------------

## KEY FEATURES

* Binary-compact core – Length-prefixed blocks for predictable parsing and small files
* Multilingual fields – Each text value can include any number of language variants
* Hashtag tagging – Inline #Python tags are extracted as structured skills; hashes are hidden in exports
* Versioned schema – Every file declares its spec version; the encoder migrates older files automatically
* CLI and SDKs – Rust core (ocvf-core), Python bindings (ocvf-py), JavaScript/WASM bindings (ocvf-js)
* Search & rank – Filter thousands of files and score matches with a single command
* Web formatter – Real-time editor that exports .ocvf, PDF, or HTML

-------------------------------------------------------------------------------

## ARCHITECTURE OVERVIEW

(ocvf-core ⟶ Rust encoder/decoder + CLI)
(Python backend ⟶ FastAPI + WebSocket)
(Web frontend ⟶ Vue or React interface)
(Bindings ⟶ Python via pyo3, JS/WASM via wasm-pack)

-------------------------------------------------------------------------------

## QUICK START

*Prerequisites*
- Rust 1.78 or newer
- Python 3.10 or newer
- Node.js \/ npm for web tools

*Istallation*
```sh
cargo install ocvf-core          # Rust encoder/decoder
pip install ocvf                 # Python CLI and bindings
npm install -g ocvf-js           # JavaScript / WASM bindings
```

*Common commands*
`ocvf encode resume.json -o resume.ocvf`
`ocvf validate resume.ocvf`
`ocvf export resume.ocvf --lang en --theme modern -o resume.pdf`
`ocvf rank resume.ocvf --filters filters.json --explain`

-------------------------------------------------------------------------------

## REPOSITORY LAYOUT
```
core/      # Rust crate
bindings/py/        # Python bindings and CLI
bindings/js/        # JavaScript / WASM bindings
web/       # Front-end client
api/       # FastAPI backend
docs/      # Specification and design notes
examples/  # Sample .ocvf files, filters, themes
```
-------------------------------------------------------------------------------

## ROADMAP

1. Publish spec v0.1 and reference Rust implementation
2. Release Python and JS\/WASM bindings
3. Deliver CLI \(encode, decode, validate, export, rank\)
4. Launch web formatter with real-time preview
5. Add search server and .well-known\/ocvf discovery endpoint
6. Provide VS Code and Word plugins
7. Pilot ATS and LinkedIn integrations

-------------------------------------------------------------------------------

## CONTRIBUTING

1. Fork the repository and create a feature branch.
2. Run tests \(cargo test, pytest, npm test\) before opening a pull request.
3. Follow the style guidelines in CONTRIBUTING.md.
