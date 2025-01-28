## Overview
This document outlines the process and methodology for parsing various data formats, normalizing them. https://unstructured.io/

### Input Formats and Methods

1. **HTML, Word, Markdown**
	- **Method:** Rules-based parsers utilising formatting information.
	- **Chunk Rules:**
  		- Structured data: Based on tags (e.g., h1, p).
  		- Unstructured data: Single sentences in a p tag, especially if capitalized, are likely titles.
	- **Output:**
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

2. **PDF, Images**
	- **Method:** Document Image Analysis (DIA) utilising visual information.
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

Objectives
- Parse many data format require normalisation 
- Maintain record of original data and enrich it as metadata
- Improve down stream RAG result hyper search, chunk content more meaningful with semantic search 
- Content similarity element: metadata changes such as page or section

Problems:
- Too many matches
- Most recent information 
- Loss of important information 

To solve the problems:
- Hybrid search semantic search + filtering on metadata
