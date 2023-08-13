# OCR_on_Invoices
Extacting text from invoice images using Paddle OCR

**1. Installation and Setup:**
Installed necessary packages using pip, including PaddlePaddle OCR and Faiss.
Cloned the PaddleOCR repository from GitHub.

**Document Layout Analysis:**
Loaded an image using OpenCV.
Used PaddleOCR's layout model to detect document structure.
Extracted coordinates of different structural elements (table, text, title, etc.).

**Text Extraction and OCR:**
Used PaddleOCR to perform Optical Character Recognition (OCR) on the extracted title image.
Extracted text and confidence scores from the OCR results.

**Horizontal and Vertical Line Detection:**
Detected horizontal and vertical lines in the extracted image.
Applied non-maximum suppression to filter out redundant lines.

**Cell Detection and Text Association:**
Used intersection over union (IoU) to associate OCR-detected text with table cells.
Created a 2D array to store text associated with each cell based on row and column indices.

**Data Preprocessing and Categorization:**
Saved the cell data into a CSV file for further analysis.
Cleaned the data by removing commas and converting the 'BALANCE' column to numeric.
Calculated the average balance for each category.

**Category Assignment Based on Balance:**
Assigned 'Category' values to rows with 'None' based on balance comparisons.
Categorized rows with 'None' based on whether their balance is above or below the average.

**Categorization Based on Balance Comparison:**
Reassigned 'Category' values to rows with 'None' based on balance comparisons.
Categorized 'None' rows based on whether their balance is above or below the average.

Overall, this project takes an input image containing a document, extracts its structural elements and associated text, performs OCR, detects table lines, associates text with cells, and finally categorizes the data based on certain criteria. It's a comprehensive example of document processing and data analysis using various libraries and techniques.
