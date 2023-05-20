# Text Extraction from Images using EasyOCR

This code demonstrates the extraction of text from images using the EasyOCR library. EasyOCR is a Python package that allows for easy integration of optical character recognition (OCR) capabilities into your projects.

## Prerequisites

Before running the code, make sure you have the following libraries installed:

- OpenCV (`cv2`)
- Matplotlib (`matplotlib`)
- NumPy (`numpy`)
- Imutils (`imutils`)
- EasyOCR (`easyocr`)

You can install these libraries using pip:

```shell
pip install opencv-python matplotlib numpy imutils easyocr
```

## Usage

1. Import the required libraries: `cv2`, `matplotlib.pyplot`, `numpy`, `imutils`, and `easyocr`.
2. Apply bilateral filtering and edge detection to the input image to enhance the text regions.
3. Find the contours in the edged image using `cv2.findContours()`.
4. Sort the contours based on their area in descending order and select the top 10 contours.
5. Iterate over the contours and check if each contour has four vertices (a rectangular shape).
6. If a contour with four vertices is found, store its location and break the loop.
7. Create a mask using `cv2.drawContours()` with the location of the selected contour.
8. Apply the mask to the original image using `cv2.bitwise_and()`.
9. Find the coordinates `(x, y)` where the mask is nonzero.
10. Crop the gray image based on the minimum and maximum coordinates obtained.
11. Create an instance of the `easyocr.Reader` class, specifying the desired language(s).
12. Use the `readtext()` method of the reader instance to extract text from the cropped image.
13. Retrieve the extracted text from the result.
14. Use `cv2.putText()` to draw the extracted text on the original image.
15. Use `cv2.rectangle()` to draw a rectangle around the detected text region on the original image.
16. Display the resulting image using `matplotlib.pyplot.imshow()`.
17. The extracted text can be accessed as `result[0][-2]`.

## Demo
[**Project Youtube Link**](https://youtu.be/SDVWV4csGWY)

## License

This code is licensed under the [MIT License](LICENSE).

## Acknowledgments

- EasyOCR is a user-friendly and powerful OCR library that simplifies text extraction from images.
- OpenCV provides various image processing functions and computer vision algorithms.
- Matplotlib is a popular data visualization library in Python.
- NumPy provides efficient array operations and mathematical functions.
- Imutils is a package that simplifies common image processing tasks.
