# Research Paper Summarization Tool

## Overview
This Python script automates summarizing PDF research papers. It uses the Qwen - Long API to generate summaries and exports them to an Excel file. It has three main classes for processing PDFs, interacting with the API, and exporting results.

## Features
- Finds all PDFs in a given folder.
- Integrates with Qwen - Long API for summarization.
- Parses API responses into structured sections.
- Cleans text and formats dates.
- Exports data to Excel with formatted cells.
- Saves raw API responses as TXT files.

## Requirements
- Python 3.x
- Libraries: `os`, `datetime`, `typing`, `pandas`, `re`, `openai`, `openpyxl`
- Valid Qwen - Long API key

## Installation
```bash
pip install pandas openai openpyxl
```

## Configuration
Update the `CONFIG` dictionary in `main` with your API key, PDF folder path, output file name, and user prompt file path.

## Usage
1. Put PDFs in the specified folder.
2. Create a user prompt file.
3. Run the script:
```bash
python script_name.py
```
4. Results are saved in a timestamped Excel file, and raw responses in TXT files.

## Classes and Methods
### PDFProcessor
- `process_folder(folder_path)`: Returns a list of PDF file paths in a folder.

### QwenAPI
- `__init__(api_key, user_prompt_path)`: Initializes the API client.
- `upload_document(file_path)`: Uploads a PDF and returns its ID.
- `get_summary(file_id)`: Gets the summary of a document.

### ResultExporter
- `to_excel(data, output_path)`: Exports data to Excel.
- `parse_sections(content)`: Parses API response into sections.
- `clean_text(text)`: Cleans text.
- `format_date(date_str)`: Formats dates.

## Limitations
- Depends on Qwen - Long API availability.
- Text parsing may be inaccurate if API responses vary.
- Date formatting may not handle all formats.

## Troubleshooting
- Check API key and credits for API errors.
- Ensure PDF files are accessible and not corrupted for upload errors.
- Verify file path and data types for Excel export errors. 
