# File extraction scripts

Scripts for extracting text from common document formats (PDF, DOCX, PPTX) into markdown for processing by the project brain.

---

## Quick start

```bash
# Navigate to scripts directory
cd 07_ops/scripts

# Create virtual environment
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Extract a single file
python process_files.py /path/to/document.pdf

# Extract all files in a directory
python process_files.py /path/to/folder/

# Output to specific location
python process_files.py /path/to/document.pdf --output ../../../_inbox/
```

---

## Supported formats

| Format | Extension | Notes |
|--------|-----------|-------|
| PDF | `.pdf` | Text-based PDFs extract directly; scanned PDFs fall back to OCR |
| Word | `.docx` | Extracts paragraphs and tables |
| PowerPoint | `.pptx` | Extracts slide text and notes |

---

## OCR setup (for scanned PDFs)

If you have scanned PDFs, you'll need Tesseract installed:

### macOS
```bash
brew install tesseract
```

### Ubuntu/Debian
```bash
sudo apt-get install tesseract-ocr
```

### Windows
Download installer from: https://github.com/UB-Mannheim/tesseract/wiki

---

## Output format

Extracted files are saved as markdown with source metadata:

```markdown
---
source_file: original-document.pdf
extracted: 2025-01-15
pages: 12
---

# original-document

[extracted content here]
```

---

## Troubleshooting

### "No text extracted from PDF"
The PDF might be scanned/image-based. Ensure Tesseract is installed for OCR fallback.

### "poppler not found" (pdf2image error)
Install poppler:
- macOS: `brew install poppler`
- Ubuntu: `sudo apt-get install poppler-utils`
- Windows: Download from https://github.com/osber/poppler-windows

### Permission errors
Ensure you have read access to source files and write access to output directory.

---

## Usage in project brain workflow

1. Drop raw documents into `_inbox/`
2. Run extraction: `python process_files.py ../../_inbox/`
3. Extracted `.md` files appear alongside originals
4. Use `process inbox` command to process the extracted content
5. Move originals to `_inbox/_processed/` when done

