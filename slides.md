---
marp: true
title: Product Documentation — Data Analyst Agent
author: Mahesh · 22f2000199@ds.study.iitm.ac.in
theme: docx-pro
paginate: true
math: katex
footer: "© 2025 ExampleSoft · 22f2000199@ds.study.iitm.ac.in"
---

<!-- _class: lead -->

![bg cover](images/bg-grid.png)

# Data Analyst Agent
## Technical Product Documentation (Marp)

**Author:** Mahesh · <22f2000199@ds.study.iitm.ac.in>  
**Export targets:** HTML · PDF · PPTX · Images

---

## 1) Overview

The **Data Analyst Agent** accelerates analysis with natural-language prompts, Python execution, and reproducible notebooks.

- Built for data teams who need *explainable* results
- Version-controlled documentation via **Markdown + Marp**
- One source → many formats: **HTML, PDF, PPTX**

> This deck itself is the documentation source of truth.

---

## 2) Getting Started

**Requirements**

- Node.js 18+
- Marp CLI

```bash
npm install -g @marp-team/marp-cli
# or
npx @marp-team/marp-cli@latest
```

**Preview**

```bash
marp -s . --theme-set themes/custom.css
```

---

## 3) Architecture Snapshot

- Ingestion: CSV, Parquet, SQL
- Compute: Python runtime (pandas, duckdb)
- Orchestration: Task graph with caching
- Exports: Markdown → (HTML | PDF | PPTX | PNG/JPEG)

**Complexity note (math enabled):**  
Worst-case schedule length for a balanced task DAG is
\( T(n) = \Theta(n \log n) \).  
Example: Merge-based composition runs in \( O(n \log n) \).

---

<!-- _backgroundColor: #0f172a -->
<!-- _color: #e2e8f0 -->
<!-- _header: **ExampleSoft · Data Analyst Agent** -->
<!-- _footer: *v1.0 · 22f2000199@ds.study.iitm.ac.in* -->

## 4) Usage — CLI

```bash
# Run an analysis plan
daa run --plan plans/weekly.yaml

# Render a report
daa report --input reports/retention.md --out dist/retention.html
```

- Supports `--seed` for reproducible runs
- Deterministic caching via content hashing

---

## 5) Configuration

```yaml
# config.yaml
runtime:
  python: "3.11"
  packages:
    - duckdb
    - pandas
logging:
  level: INFO
outputs:
  dir: dist/
```

**Table example**

| Output      | Format | Notes            |
|-------------|--------|------------------|
| dashboard   | HTML   | share on web     |
| slide-deck  | PPTX   | exec review      |
| paper       | PDF    | archival quality |

---

## 6) Theming & Branding

This deck uses a **custom Marp theme** named `docx-pro` (see `themes/custom.css`).  
Use `--theme-set themes/custom.css` during export.

```bash
marp slides.md -o dist/slides.html --theme-set themes/custom.css
marp slides.md --pdf --allow-local-files --theme-set themes/custom.css
marp slides.md --pptx --theme-set themes/custom.css
```

---

## 7) Code Samples

```python
def top_k(df, col, k=10):
    return df.sort_values(col, ascending=False).head(k)
```

```javascript
console.log("Hello from Marp + JS");
```

```css
.card { border-radius: 16px; padding: 16px; }
```

---

## 8) Operational Guarantees

- **Idempotent** runs via content-addressed artifacts
- **Time complexity** of topological planning: \( O(V + E) \)
- **Space complexity** of cache index: \( O(N) \)

Inline math example: \( E = mc^2 \)

---

## 9) Support & Contact

Questions, bugs, or requests?  
**Email:** <22f2000199@ds.study.iitm.ac.in>

**Keyboard shortcuts (VS Code Preview):** `Ctrl+Shift+V`, `Ctrl+K V`

---

## 10) License & Attribution

- © 2025 ExampleSoft. All rights reserved.
- Built with **Marp** — Markdown Presentation Ecosystem.