# Data Parsing and Normalization for Enhanced Semantic Search

## Overview
This document outlines the process and methodology for parsing various data formats, normalizing them, and improving downstream Retrieval-Augmented Generation (RAG) results using semantic search. It also addresses common challenges and proposes solutions.

## Objectives
1. Parse multiple data formats and normalize the content.
2. Maintain records of original data while enriching it as metadata.
3. Improve downstream RAG results by hyper-searching and chunking content more meaningfully with semantic search.
4. Incorporate content similarity elements such as metadata changes (e.g., page or section).

## Challenges
1. Too many matches.
2. Difficulty in accessing the most recent information.
3. Loss of important information.

## Proposed Solution
Hybrid search combining semantic search with filtering on metadata.

---

## Document Analysis and Normalization Process
### Steps:
1. **Detection**
2. **Chunking**

### Input Formats and Methods
#### 1. **HTML, Word, Markdown**
- **Method:** Rules-based parsers utilizing formatting information.
- **Chunk Rules:**
  - Structured data: Based on tags (e.g., `<h1>`, `<p>`).
  - Unstructured data: Single sentences in a `<p>` tag, especially if capitalized, are likely titles.
- **Preprocessing Output:**
  - Document elements: Title, narrative text, list items, tables, images.
  - Element metadata: File name, file type, page number, section, etc.

**Example JSON Representation:**
```json
{
    "type": "Document type",
    "element_id": 1,
    "metadata": {
        "page_no": 1,
        "language": "English",
        "file_name": "Otis",
        "file_type": "pdf"
    }
}
```

#### 2. **PDF, Images**
- **Method:** Document Image Analysis (DIA), document layout detection using visual information.
- **Chunk Rules:**
  - **Document Layout Detection:**
    - **Method:** Object detection model (e.g., YOLOX, Detectron2).
    - **Process:**
      - **Vision Detection:** Identify and classify boundary boxes using vision models.
      - **Extraction:** Extract text from boundary boxes using Object Character Recognition (OCR).
      - **Output:** Labelled boundary boxes around layout elements.

  - **Vision Transformers:**
    - **Method:** viT models (e.g., Donut architecture).
    - **Process:** Visual translation from image to text using encoder-decoder architecture.
    - **Output:** JSON text representation.

  - **Table Extraction:**
    - **Method:**
      - Table transformers.
      - Vision transformers.
      - OCR post-processing.
      - Layout detection model + OCR + rules-based method.
    - **Output:** HTML representation.

---

## Example Outputs
### JSON Representation for Document Analysis:
```json
{
    "type": "Document type",
    "element_id": 2,
    "metadata": {
        "page_no": 3,
        "language": "English",
        "file_name": "Sample",
        "file_type": "docx"
    }
}
```

### HTML Representation for Table Extraction:
```html
<table>
    <tr>
        <th>Header 1</th>
        <th>Header 2</th>
    </tr>
    <tr>
        <td>Data 1</td>
        <td>Data 2</td>
    </tr>
</table>
```

---

## Tools and Models Used
1. **Rules-Based Parsing**
2. **Object Detection Models:** YOLOX, Detectron2
3. **OCR:** Tesseract or equivalent
4. **Vision Transformers:** Donut architecture
5. **Table Transformers**

## Summary
By combining semantic search with metadata filtering and leveraging advanced document analysis techniques, this methodology ensures enhanced RAG results while mitigating challenges like excessive matches, outdated information, and loss of critical content.
