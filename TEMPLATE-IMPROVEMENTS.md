# Template Improvements

Reflections on what could be improved in this project brain template for future projects.

---

## Backlog

_No pending improvements._

---

## Completed

### ✅ 1. Robust file processing pipeline
**Implemented**: 2025-12-29

Created unified file extraction scripts in `07_ops/scripts/`:
- `process_files.py` — auto-detects PDF/DOCX/PPTX and extracts to markdown
- `requirements.txt` — all dependencies with version pinning
- `README.md` — setup instructions including OCR (Tesseract) installation

Features:
- Single script handles all common formats
- OCR fallback for scanned PDFs
- Frontmatter with source metadata
- Clear error handling and logging

---

### ✅ 2. Timestamp filenames for generated documents
**Implemented**: 2025-12-29

Updated `.cursorrules` file conventions to require date prefixes:
- Generated docs must use `YYYY-MM-DD-slug.md` format
- Template files and living documents are exempt
- Added examples to make convention clear

---

### ✅ 3. Cursor rule for knowledge audits
**Implemented**: 2025-12-29

Added `audit brain` command to `.cursorrules` with:
- Checklist of what to scan (empty files, thin profiles, pending ADRs, etc.)
- Risk-level grouping (🔴 🟠 🟡)
- Time estimates and recommended actions
- Discussion questions for team alignment
- Timestamped output to `07_ops/`

---

## Notes

- This file tracks improvements to the **template**, not this specific project
- When starting a new project from this template, delete this file or archive it
- Consider maintaining a separate "template" repo that gets improvements merged back

---

_Last updated: 2025-12-29 (all backlog items implemented)_

