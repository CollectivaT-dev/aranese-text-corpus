# Aranese text corpus creation pipeline

This repository provides a complete pipeline for extracting text from PDFs, performing OCR, correcting the OCR output using a commercial LLM, and generating a large text corpus of Occitan Aranese from the [Universitat Autònoma de Barcelona's digital repository of Aranese Press](https://ddd.uab.cat/collection/honsaran).

## Features

- Parse publication record URLs from a specified text file
- Download all associated PDFs of each publication
- Extract each page in the PDFs as an image
- Perform optical character recognition (OCR) using Tesseract
- Correct orthographic and formatting errors using Claude LLM (needs API key but can be skipped)
- Extract sentences from each document, save them for each publication, and merge them into a single corpus file (general and with full sentences only)

## Installation

### Prerequisites

Make sure you have the following software installed:

- Python 3.7+
- Tesseract OCR (installation instructions below)

### Install Dependencies

Clone this repository and install the required dependencies:

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
pip install -r requirements.txt
```

### Tesseract OCR Installation

#### macOS

Use Homebrew to install Tesseract OCR:

```bash
brew install tesseract
brew install tesseract-lang
```

#### Ubuntu (not verified)

Use apt-get to install Tesseract OCR:

```
sudo apt-get update
sudo apt-get install tesseract-ocr
sudo apt-get install tesseract-ocr-oci
```

#### Setting Up the Anthropic API Key

Create a `.env` file in the root directory of your repository and add your Anthropic API key:

```
ANTHROPIC_API_KEY=your_api_key_here
```

## Usage

1. Prepare the Publication List: Create a text file listing the URLs of the publication records from Premsa Aranesa line by line (see `uab_repo_urls.txt`).

2. Open the notebook `Aranese text corpus.ipynb` and execute cell by cell.

## Disclaimer

This work is solely for research purposes, and Col·lectivaT does not hold any responsibility for its use. The material collected by running this source code is subject to the licenses specified in UAB's repository:

```
Còpia permesa amb finalitat d'estudi o recerca, citant la font: "Universitat Autònoma de Barcelona. Biblioteca de Comunicació i Hemeroteca General. CEDOC". Per a qualsevol altre ús cal demanar autorització.
```

Users must verify compliance with all applicable licenses and regulations. It is the user's responsibility to ensure that their use of this repository and the generated corpus complies with all relevant laws and policies.
