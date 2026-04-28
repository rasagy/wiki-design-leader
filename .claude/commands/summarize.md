Summarize a book or document file (PDF, EPUB, or Markdown) into structured notes in the `notes/` folder.

## Instructions

The user will provide a file path or file name. Follow these steps exactly:

### Step 1: Locate the file

If the user gave a full path, use it directly. If they gave only a filename, search for it under the current working directory (check `ref/` and subdirectories first). Confirm the file exists before proceeding.

### Step 2: Extract the text

Choose the extraction method based on file type:

**EPUB:**
```bash
mkdir -p /tmp/summarize_epub
cp "<path>" /tmp/summarize_epub/book.epub
cd /tmp/summarize_epub && unzip -o book.epub -d extracted/
```
Then read the HTML files in `extracted/` (usually under `OEBPS/` or `OPS/`). Use Python to strip HTML tags:
```bash
python3 -c "
import re, glob, os
files = sorted(glob.glob('/tmp/summarize_epub/extracted/**/*.html', recursive=True))
# skip cover/toc/copyright/colophon pages
skip = ['cover', 'toc', 'copyright', 'colophon', 'titlepage', 'dedication']
for f in files:
    if any(s in os.path.basename(f) for s in skip):
        continue
    with open(f) as fh:
        text = fh.read()
    text = re.sub(r'<[^>]+>', '', text)
    text = re.sub(r'\s+', ' ', text).strip()
    print(f'=== {os.path.basename(f)} ===')
    print(text[:4000])
    print()
"
```

**PDF:**
Use `pdftotext` if available (`pdftotext "<path>" -`), otherwise try:
```bash
python3 -c "
import subprocess
result = subprocess.run(['pdftotext', '<path>', '-'], capture_output=True, text=True)
print(result.stdout[:20000])
"
```
If `pdftotext` is unavailable, read the PDF using the Read tool directly (it supports PDFs).

**Markdown:**
Read the file directly using the Read tool.

### Step 3: Read thoroughly

Read enough of each chapter to understand its central argument and concrete ideas. For each chapter, look for:
- The main thesis or problem being addressed
- Specific frameworks, models, or named concepts
- Memorable quotes from practitioners or the author
- Concrete advice or actionable takeaways

### Step 4: Produce the summary

Create a markdown file at `notes/<original-filename>.md` (preserve the exact original filename, just change/add the `.md` extension and place it in `notes/`).

Use this exact structure:

```markdown
# <Full Title>
**<Author(s)>** | <Publisher>, <Year>

> <Two-sentence summary of the whole book/document — what it argues and why it matters.>

---

## Chapter N: <Chapter Title>

<Two sentences on the central idea of this chapter.>

- Key idea 1
- Key idea 2
- Key idea 3
- ...

> "<Memorable quote if there is one>" — Attribution

---

## Cross-cutting Themes

| Theme | How it appears across chapters |
|---|---|
| **Theme 1** | Ch1: ..., Ch3: ..., Ch6: ... |
| **Theme 2** | ... |
```

Rules for the content:
- The two-line book summary should state *what* the book argues and *why* it matters to the reader
- Each chapter's two-sentence summary should name the central problem or argument, not just describe the topic
- Key ideas should be concrete and specific — avoid generic statements like "culture is important"
- Include quotes only when they are genuinely memorable or surprising
- The cross-cutting themes table should have 4–7 rows; each theme should appear in at least 3 chapters
- Do not add any preamble or explanation outside the markdown structure

### Step 5: Save and confirm

Write the file to `notes/`. Report the path to the user when done.
