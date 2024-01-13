import PyPDF2
import os
from typing import List
def extract_text_from_pdf(pdf_path: str) -> str:
    with open(pdf_path, 'rb') as file:
        pdf_reader = PyPDF2.PdfFileReader(file)
        text = ""
        for page_num in range(pdf_reader.numPages):
            text += pdf_reader.getPage(page_num).extractText()
    return text
def extract_text_from_multiple_pdfs(directory_path: str) -> List[str]:
    text_data = []
    for filename in os.listdir(directory_path):
        if filename.endswith('.pdf'):
            pdf_path = os.path.join(directory_path, filename)
            text_data.append(extract_text_from_pdf(pdf_path))
    return text_data
def main():
    directory_path = 'C:\Users\alfian\Downloads\Documents'
    text_data = extract_text_from_multiple_pdfs(directory_path)
    for index, text in enumerate(text_data):
        with open(f'output_text_{index}.txt', 'w') as output_file:
            output_file.write(text)
    print("Data extraction complete.")

if __name__ == "__main__":
    main()
