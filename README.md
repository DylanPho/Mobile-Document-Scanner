# Mobile Document Scanner

This project is a Python-based mobile document scanner that processes images to extract and transform them into a clean, top-down view suitable for use as scanned documents. The program implements image processing techniques such as edge detection, contour approximation, and perspective transformation to achieve this functionality.

## Features

- **Edge Detection**: Identifies the boundaries of the document in the image.
- **Contour Detection**: Locates the largest quadrilateral contour, assuming it represents the document.
- **Perspective Transformation**: Warps the identified document area into a top-down view.
- **Thresholding**: Converts the processed image into a clean black-and-white format for better readability.

## Requirements

To run the project, ensure the following Python libraries are installed:

- `numpy`
- `opencv-python`
- `imutils`
- `scikit-image`

You can install the dependencies using:

```bash
pip install numpy opencv-python imutils scikit-image
```

## Usage

### Command-Line Arguments
The program accepts a single command-line argument:

- `--image`: Path to the image to be scanned.

### Running the Program

1. Place the image you want to scan in your working directory.
2. Run the program using the following command:

```bash
python scan.py --image path/to/your/image.jpg
```

The program will display the following steps:

1. **Edge Detection**: Displays the edges detected in the image.
2. **Outline**: Shows the contour of the detected document.
3. **Scanned Document**: Presents the final processed image.

### Debugging
If no document contour is found, the program saves the edge-detected image as `debug_edges.jpg` for troubleshooting.

## File Structure

- `scan.py`: The main script for scanning the document.
- `transform.py`: Contains utility functions for ordering points and applying perspective transformation.

## How It Works

1. **Load and Resize Image**: The input image is loaded and resized for faster processing.
2. **Preprocessing**: The image is converted to grayscale, blurred, and edge-detected.
3. **Contour Detection**: Finds and approximates the largest contour with four points, representing the document.
4. **Perspective Transformation**: Uses the `four_point_transform` function to warp the document into a flat, top-down view.
5. **Thresholding**: Converts the warped image to black and white for a clean document look.

## Example Output

Before and after images of the document are displayed at various stages, providing a clear understanding of the process.

## Error Handling
- If the image cannot be loaded, the program raises an error with details.
- If no valid contour is found, a debug image is saved for inspection.

## License

This project is licensed under the MIT License.

---

For further questions or contributions, feel free to reach out!