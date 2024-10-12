# Egyptian National ID Detection and Data Extraction

## Project Overview
This project focuses on the detection and extraction of data from Egyptian National IDs using computer vision techniques. The system is capable of detecting the ID card from an image, extracting key information such as the national ID number, full name, date of birth, and other relevant details using Optical Character Recognition (OCR).

### Key Features:
- Detect the Egyptian National ID from an image.
- Extract personal data such as:
  - Full Name
  - National ID Number
  - Date of Birth
  - Gender
  - Governorate
- Use state-of-the-art models for image detection and text extraction.
- Preprocessing steps to enhance image quality for better OCR accuracy.

## Table of Contents
1. [Usage](#usage)
2. [Project Structure](#project-structure)
3. [Model Details](#model-details)
4. [Data Preprocessing](#data-preprocessing)
5. [OCR Process](#ocr-process)
6. [License](#license)


## Usage

1. Place an image of the Egyptian National ID in the `input_images` folder.
2. Run the main script to detect the ID and extract data:
    ```bash
    python detect_and_extract.py --image_path input_images/sample_id.jpg
    ```

3. The detected information will be displayed in the console and saved in a `results` folder.

### Arguments
- `--image_path`: Path to the image file of the National ID.
- `--output_format`: Specify the output format (`json`, `csv`). Default is `json`.

---



## Model Details

The project leverages a combination of object detection and OCR techniques:

1. **Object Detection**: A pre-trained deep learning model (YOLOv8 or similar) is used to detect the Egyptian National ID in the image.
2. **Optical Character Recognition (OCR)**: Tesseract OCR is employed to extract text from the detected ID. The extracted text is then processed to parse out relevant information like the National ID number, full name, date of birth, etc.
3. **Arabic number detection **: detect ID number and convert to English numbers.


---

## Data Preprocessing

Before applying OCR, several preprocessing steps are carried out on the image to improve the detection and extraction quality:
- **Grayscale Conversion**: The image is converted to grayscale.
- **Noise Reduction**: Techniques like Gaussian blur are applied to reduce noise.
- **Thresholding**: Adaptive thresholding is used to make the text more readable for OCR.
- **ROI Extraction**: The Region of Interest (ROI) containing the text is extracted from the image for OCR.

---

## OCR Process

Once the ID card is detected, the following data is extracted:
1. **National ID Number**: Extracted from the bottom of the card.
2. **Full Name**: Extracted from the name field.
3. **Date of Birth**: Parsed from the ID number (first 7 digits).
4. **Gender and Governorate**: Inferred from the ID number (digits 8–13).

The extracted data is outputted in a structured format, either as JSON or CSV.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- This project utilizes **Tesseract OCR** for text recognition.
- Pre-trained models for ID detection are based on **YOLO**.

---

