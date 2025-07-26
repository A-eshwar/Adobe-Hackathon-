#📄 PDF Outline Extractor
This project extracts structured outlines (headings) from one or more PDF documents using font analysis, heading pattern recognition, and semantic rules. It supports Docker-based deployment for ease of use in various environments.

#🚀 Features
Extracts heading-level outlines (H1, H2, H3) from PDFs.

Supports multilingual and diverse heading patterns.

Outputs structured JSON files with detected outlines.

Dockerized and easy to run across platforms.

#🧱 Directory Structure
graphql
Copy
Edit
.
├── Dockerfile
├── pdf_extractor.py
├── requirements.txt
├── /app
│   ├── input/       # Place input PDFs here
│   └── output/      # JSON results are written here
📦 Setup
1. Clone the repository
bash
Copy
Edit
git clone <your-repo-url>
cd <your-repo-folder>
2. Add PDF files
Place all your PDF documents inside the /app/input/ folder (it will be created in the container automatically).

3. Add Python dependencies
Create a file called requirements.txt (or reuse the one below):

txt
Copy
Edit
PyMuPDF==1.22.5
4. Build the Docker Image
bash
Copy
Edit
docker build -t pdf-outline-extractor .
5. Run the Container
bash
Copy
Edit
docker run --rm -v $(pwd)/app/input:/app/input -v $(pwd)/app/output:/app/output pdf-outline-extractor
This mounts your local app/input/ and app/output/ folders into the container.

#🧪 Sample Output
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
#⚙️ File Descriptions
File	Description
Dockerfile	Builds the container image
pdf_extractor.py	Main logic to extract outlines from PDFs
requirements.txt	Python dependencies
app/input/	Folder to place your input .pdf files
app/output/	Output folder for extracted .json outline files

#🛠 Customization
You can modify the patterns in the heading_patterns and heading_keywords lists inside pdf_extractor.py to better match your expected document styles.


