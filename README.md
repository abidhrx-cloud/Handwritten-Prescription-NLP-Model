# Handwritten Prescription NLP Model

## Overview
This project extracts structured medical information from handwritten doctor prescriptions using Computer Vision (OCR) and Natural Language Processing (NLP).

The system converts prescription images into readable text and identifies key entities such as patient name, doctor name, medicines, dosage, frequency, duration, and timing.

## Features
- Image input (handwritten prescriptions)
- Text extraction using OCR
- NLP-based entity recognition
- Medicine, dosage, and frequency extraction
- Structured output (JSON/CSV)

## Tech Stack
- Python
- OpenCV (image preprocessing)
- Pytesseract (OCR)
- NLTK / spaCy (NLP)
- Pandas (data handling)
- Regex (pattern extraction)

## Project Structure
Prescription-NLP/
│── data/
│   ├── images/              
│   └── annotations/         
│
│── notebooks/
│   └── exploration.ipynb    
│
│── src/
│   ├── preprocessing.py     
│   ├── ocr.py               
│   ├── nlp.py               
│   └── utils.py             
│
│── outputs/
│   └── results.json         
│
│── requirements.txt
│── README.md

## Installation

1. Clone the repository
git clone https://github.com/your-username/prescription-nlp.git
cd prescription-nlp

2. Install dependencies
pip install -r requirements.txt

3. Install Tesseract OCR
Download from: https://github.com/tesseract-ocr/tesseract  
Add it to system PATH.

## Usage

1. Place prescription images inside:
data/images/

2. Run the pipeline:
python src/main.py

3. Output will be saved in:
outputs/results.json

## Workflow

1. Image Preprocessing
- Grayscale conversion
- Noise removal
- Thresholding

2. OCR Extraction
- Convert image to raw text

3. Text Cleaning
- Remove noise
- Normalize text

4. NLP Processing
- Tokenization
- Named Entity Recognition (NER)
- Pattern matching for dosage, frequency, duration

5. Structured Output
- Convert extracted data into JSON or CSV

## Results

Due to the small and noisy dataset (10 images), the model performance is limited and contains OCR errors.

- Total medicines extracted: 10  
- Unique prescriptions: 9  

### Sample Extracted Data

| file | name | dosage | frequency | duration | timing |
|------|------|--------|----------|----------|--------|
| Sonali-1_page1.pdf | V CBPlcpp V X A Suab HN_ Forv | 51751 G | - | - | - |
| Sonali-12_page1.pdf | KI] M.G.A. HOSPITAL No. 96, Ma | 27 G | - | - | - |
| Sonali-13_page1.pdf | “oO if } pe] x 10g | 10g | - | - | - |
| Sonali-14_page1.pdf | CASESEENBY: Ais. 97 G PP. Lowe | 97 G | - | - | - |
| Sonali-3_page1.pdf | ENT . ge DNS @ mh 10g | 10g | - | - | - |
| Sonali-3_page1.pdf | % 7993366823 0 Gerd: : | 0 G | - | - | - |
| Sonali-31_page1.pdf | CAP ZYCEL | 200 MG | - | FOR 10 DAYS | - |
| Sonali-42_page1.pdf | T Menoctyl | 40 mg | - | 15 days | - |
| Sonali-6_page1.pdf | Nami Mim; SC)NAI.I PAIIR() Aga | 17 G | - | - | - |
| SonaliPrescription_page1.pdf | Apply 1.0 ml to affected area | 0 ml | twice a day | - | - |

## Challenges
- Poor handwriting quality
- OCR inaccuracies and noise
- Small dataset size
- Medical abbreviations and inconsistent formats

## Future Improvements
- Use deep learning-based handwriting recognition models
- Train domain-specific NLP models (BioBERT, ClinicalBERT)
- Increase dataset size and quality
- Improve preprocessing for better OCR accuracy

## License
This project is licensed under the MIT License.

## Author
Syed Abid
