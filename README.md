# Currency Recognition Program

This is a Python-based Currency Recognition program that uses ORB (Oriented FAST and Rotated BRIEF) keypoint detection to identify currency denominations from live camera input.

## Features
- Real-time detection of currency denominations using a webcam.
- ORB feature detection and matching with a training set of images.
- Provides visual feedback of the detected denomination and match confidence.

## Requirements
- Python 3.x
- OpenCV
- NumPy
- Matplotlib

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/akshayamin62/Currency-Recognition
   ```

2. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

3. Place images of the currency denominations to be recognized in the `currency_images` directory. Each image should be named according to its denomination (e.g., `10.jpg`, `50.jpg`, etc.).

## Usage
1. Run the program:
   ```bash
   python index.py
   ```

2. Allow the program to access your webcam.

3. Present a currency note in front of the webcam. The program will process the live video feed and display the detected denomination.

4. Press `q` to exit the program.

## How It Works
1. The program initializes the ORB detector and loads the training images from the `currency_images` directory.
2. It captures frames from the webcam and preprocesses them.
3. Keypoints and descriptors are computed for both the live frame and each training image.
4. Matches are found using a brute-force matcher with Lowe's ratio test to filter good matches.
5. The denomination with the highest number of matches and sufficient match confidence is displayed as the detected denomination.
6. If no good matches are found, it displays the closest match for reference.

## Configuration
- **MIN_MATCH_COUNT**: Minimum number of matches required to confirm a denomination. Default is `5`.
- **KERNEL_SIZE**: Kernel size for preprocessing (if applicable). Default is `11`.

## Directory Structure
```
.
├── index.py   # Main program file
├── currency_images/          # Directory containing training images
├── utils.py                  # Utility functions (optional, include preprocessing logic here)
├── requirements.txt          # Required Python packages
```

## Customization
- **Training Set**: Add or replace images in the `currency_images` directory to support new currencies or improve detection accuracy.
- **Preprocessing**: Modify the `preprocess` function in the code to apply custom preprocessing steps like resizing, grayscale conversion, or filtering.

## Example Output
When a currency note is detected successfully, the program will display:
```
Match Found!
50 has maximum matches of 42 (60%)
Detected denomination: 50
```

If no good matches are found:
```
No Good Matches, closest one has 12 matches (20%)
```

## Dependencies
- OpenCV
- NumPy
- Matplotlib

