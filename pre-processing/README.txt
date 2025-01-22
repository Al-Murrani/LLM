https://unstructured.io/

Parse many data format require normalisation 
Maintain record of original data and enrich it as metadata
Improve down stream RAG result hyper search, chunk content more meaningful with semantic search 
Content similarity element: metadata changes such as page or section
Problems:
Too many matches
Most recent information 
Loss of important information 

To solve the problems:
Hybrid search semantic search + filtering on metadata

Document analysis to normalise output:
Detect
Chunk
1.
Input format: HTML, Word, Markdown
Method: Rules-based parsers using formatting information
Chunk Rules:
structure On tags (h1, p), unstructured data such as single sentence in a p tag that is capital is more like to be a title
Preprocessing output:
Document Elements such as title, narrative text, list item, table, image, useful for RAG filtering and chunking
Element metadata such as file name, file type, page number, section 

Example of JSON:
{
	"type": "Document type",
	"element_id": 1,
	"metadata":
		{
			"page_no": 1,
			"language": "English",
			"file_name": "Otis",
			"file_type": "pdf"
		
		}
}

2.
Input format: PDF, images
Method: Document Image Analysis (DIA), document layout detection using visual information
Chunk Rules:
Document layout detection:
Method: object detection model (directly)
Process:
Vision detection: 
Identify and classify boundary boxes using vision models such as YOLOX or Detectron2
Extraction:
text from boundary boxes using object character recognition (OCR) 
Output: labelled boundary boxes around layout elements

Vision transformers:
Method: viT models
Process:
Visual translation: image to encoder, decoder to text, such as Donut architecture 
Output: JSON text representation
 
Table Extraction: 
Method:
Table transformers
Vision transformers
OCR post-processing 
layout detection model - OCR - rule based method
Output: HTML
