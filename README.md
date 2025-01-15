# Apple Detection and Classification Project

## Overview
This project is designed to detect apples from an image, crop them, and classify them into three color categories: **Red**, **Yellow**, and **Green**. The detection is performed using a pre-trained YOLOv8 model, and the classification is done using the HSV (Hue, Saturation, Value) color space. The goal is to prepare images of apples with appropriate labels, helping a human data labeling team to validate the results and improve the model's performance.

## Requirements
To run this project, you will need the following dependencies and setup:

### 1. **Libraries**:
   - **Ultralytics YOLO**: Used for object detection.
   - **OpenCV**: For image processing and saving results.
   - **NumPy**: For numerical operations like matrix manipulation and array handling.
   - **Python**: Version 3.6 or later.

### 2. **Python Libraries**:
You can install the necessary Python libraries using the following commands:
   ```bash
   pip install ultralytics
   pip install opencv-python
   pip install numpy
   ```

## Dataset to Detection Apple
https://universe.roboflow.com/105-recycler/apple-ruajr/dataset/1 (I only used some of them).

## Steps Involved

### 1. **Apple Detection and Cropping**
   - **Image Input**: A test image containing apples (e.g., a photograph of apples in different colors) is provided as input to the model.
   - **YOLOv8 Model**: The YOLOv8 model is used to detect the apples in the input image. YOLO (You Only Look Once) is a real-time object detection algorithm that locates apples within the image using bounding boxes.
   - **Cropping**: Each detected apple is cropped using its bounding box coordinates. These cropped images are saved for further processing.

### 2. **Classifying Apples by Color**
   - **Color Classification**: Once the apples are cropped, they are classified by color using the HSV color space. The three color categories considered are:
     - **Red Apples**
     - **Yellow Apples**
     - **Green Apples**
   - **Color Detection Logic**: A color mask is created for each color (red, yellow, green) based on predefined ranges in the HSV color space. The image's pixels are analyzed, and the apple is classified by the color that occupies the majority of the image.
   - **Improvement for Green Apples**: To avoid misclassification, especially for green apples which may appear next to red or yellow apples, the algorithm includes a boost factor for the green color to ensure it is detected accurately.

### 3. **Saving the Results**
   - **Organizing the Results**: After classification, the images are saved into separate folders for each color category (red, yellow, green). The images are named sequentially (e.g., red_1.jpg, yellow_1.jpg) to ensure they are uniquely identifiable.
   - **Final Output**: The classified and cropped apples are saved in the respective directories, making it easier for the human data labeling team to review and validate the results.

## Output
- **Cropped Apple Images**: Each cropped apple is saved as an individual image for further analysis.
- **Classified Apple Images**: The cropped images are sorted into directories based on their color (red, yellow, green).

### Example of Output Files:
- **Red Apples**: red_1.jpg, red_2.jpg, red_3.jpg
- **Yellow Apples**: yellow_1.jpg, yellow_2.jpg, yellow_3.jpg
- **Green Apples**: green_1.jpg, green_2.jpg, green_3.jpg

## Applications
This approach can be used for:
- **Agricultural Monitoring**: Identifying and counting apples in orchards.
- **Quality Control**: Sorting apples based on their color for packaging or sale.
- **Research**: Analyzing the distribution of apple colors in different environments or conditions.

## Conclusion
By automating the detection, cropping, and classification of apples based on color, this project streamlines the workflow for data collection and analysis. The combination of YOLO for detection and HSV for color classification ensures accurate and efficient processing, making it a useful tool for various agricultural and research applications.

--
