# 📄 PDF Outline Extractor
This project extracts structured outlines (headings) from one or more PDF documents using font analysis, heading pattern recognition, and semantic rules. It supports Docker-based deployment for ease of use in various environments.

# 🚀 Features
Extracts heading-level outlines (H1, H2, H3) from PDFs.

Supports multilingual and diverse heading patterns.

Outputs structured JSON files with detected outlines.

Dockerized and easy to run across platforms.

# 🧱 Directory Structure
graphql
Copy
Edit
.
├── Dockerfile

├── pdf_extractor.py

├── requirements.txt

├── /app

│   ├── input/ 

│   └── output/     

# 🧪 Sample Output
For a PDF like Learn Acrobat - Edit_1.pdf, it will generate an output JSON in app/output/Learn Acrobat - Edit_1.json like:

json

Copy

Edit

{

  "title": "Learn Acrobat: Editing PDFs",

  "outline": [
  
    { "level": "H1", "text": "Introduction to Editing", "page": 1 },
    
    { "level": "H2", "text": "Rearranging Pages", "page": 2 },
    
    { "level": "H2", "text": "Editing Text Fields", "page": 3 }
    
  ]
  
}

# ⚙️ File Descriptions
File	Description
Dockerfile	Builds the container image
pdf_extractor.py	Main logic to extract outlines from PDFs
requirements.txt	Python dependencies
app/input/	Folder to place your input .pdf files
app/output/	Output folder for extracted .json outline files

# 🛠 Customization
You can modify the patterns in the heading_patterns and heading_keywords lists inside pdf_extractor.py to better match your expected document styles.


