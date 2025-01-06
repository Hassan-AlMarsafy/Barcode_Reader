# Barcode Processing with OpenCV

This project provides a comprehensive pipeline to process and decode barcodes from images. It addresses common issues like rotation, noise, and non-standard bar widths. The implementation leverages OpenCV and NumPy for image processing and includes techniques to enhance image quality, detect noise, and accurately read barcodes.

## Features

- **Noise Detection and Removal**: Identifies sine wave noise in images and applies adaptive thresholding to mitigate it.
- **Automatic Rotation Correction**: Detects and rotates skewed barcodes to ensure horizontal alignment.
- **Gray Pixel Filtering**: Removes non-gray pixels to simplify barcode extraction.
- **Sharpness Adjustment**: Dynamically adjusts sharpness for optimal decoding.
- **Barcode Decoding**: Supports Code 11 barcode format with narrow and wide bar widths.
- **Test Suite**: Includes predefined test cases to verify barcode decoding accuracy.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/barcode-processing-opencv.git
   cd barcode-processing-opencv
   ```

2. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. Place the images containing barcodes in the `images` directory.
2. Run the script:
   ```bash
   python barcode_processing.py
   ```
3. The script will process each image, display intermediate results, and print test outcomes.

## Code Overview

### Main Functions

1. **rotate_barcode(image):**
   - Rotates the image to correct skewed barcodes.

2. **detect_sine_wave(image):**
   - Detects sine wave noise in the image using FFT.

3. **delete_non_gray(image, tolerance):**
   - Removes non-gray pixels based on a specified tolerance.

4. **read_barcode(stripe):**
   - Decodes a stripe of the barcode based on predefined widths for narrow and wide bars.

### Barcode Format
The decoding logic supports the Code 11 barcode format, where:
- `0` represents a narrow bar.
- `1` represents a wide bar.

### Test Cases
The script includes a list of test cases to validate decoding results against expected values. Each test checks if the decoded barcode matches the predefined pattern.

## Directory Structure

```
barcode-processing-opencv/
|-- images/             # Directory containing input images
|-- barcode_processing.py  # Main script
|-- requirements.txt    # Python dependencies
|-- README.md           # Project documentation
```

## Examples

### Input Image
An example image with noise and rotation:

![Input Image](path/to/input-image.png)

### Output Image
Processed barcode after rotation correction and noise removal:

![Output Image](path/to/output-image.png)

### Decoded Barcode
```plaintext
['Stop/Start', '1', '0', '4', '-', '1', '1', '6', '-', '1', '1', '6', 'Stop/Start']
```

## Dependencies

- Python 3.7+
- OpenCV
- NumPy
- Matplotlib (optional, for visualization)

## Contributing

1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add feature-name"
   ```
4. Push to the branch:
   ```bash
   git push origin feature-name
   ```
5. Open a pull request.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments

- [OpenCV](https://opencv.org/) for providing powerful image processing tools.
- Contributors and users who helped test and improve this project.

Feel free to raise issues or contribute to enhance the barcode decoding pipeline!

