# American Sign Language Recognition Using Machine Learning

This project implements a real-time American Sign Language (ASL) alphabet recognition system using computer vision and deep learning. It leverages OpenCV, MediaPipe, and Keras (TensorFlow backend) to collect hand gesture data, train an LSTM-based neural network, and perform live sign detection via webcam.

## Features

- Collects hand gesture images for each ASL alphabet letter (A-Z, except K and Z)
- Extracts hand landmarks using MediaPipe
- Trains an LSTM neural network to classify sign language gestures
- Real-time sign detection and visualization using webcam

## Project Structure

- `collectdata.py`: Collects raw hand gesture images for each letter using your webcam.
- `data.py`: Processes collected images, extracts hand landmarks, and saves them as numpy arrays for model training.
- `trainmodel.py`: Trains an LSTM model on the extracted keypoints and saves the trained model.
- `app.py`: Runs the real-time sign language recognition app using your webcam and the trained model.
- `function.py`: Contains utility functions for MediaPipe detection, keypoint extraction, and configuration.
- `model.json`, `model.h5`: Saved model architecture and weights after training.

## Setup

1. **Clone the repository**
2. **Create and activate a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   # On Windows:
   venv\Scripts\activate
   # On Unix/Mac:
   source venv/bin/activate
   ```
3. **Install dependencies:**
   ```bash
   pip install opencv-python mediapipe numpy keras tensorflow scikit-learn
   ```

## Usage

### 1. Data Collection

- Run `collectdata.py` to collect hand gesture images for each letter:
  ```bash
  python collectdata.py
  ```
  - Press the corresponding key (a-z) to save an image for that letter.
  - Images are saved in the `Image/` directory, organized by letter.

### 2. Keypoint Extraction

- Run `data.py` to extract hand landmarks from the collected images and save them as numpy arrays:
  ```bash
  python data.py
  ```
  - This will create a directory `MP_Data/` with extracted keypoints for each letter and sequence.

### 3. Model Training

- Run `trainmodel.py` to train the LSTM model:
  ```bash
  python trainmodel.py
  ```
  - The trained model will be saved as `model.h5` and `model.json`.

### 4. Real-Time Recognition

- Run `app.py` to start the real-time sign language recognition app:
  ```bash
  python app.py
  ```
  - The webcam feed will open, and detected signs will be displayed on the screen.
  - Press `q` to quit.

## Requirements

- Python 3.7+
- opencv-python
- mediapipe
- numpy
- keras
- tensorflow
- scikit-learn

## License

This project is licensed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [MediaPipe](https://mediapipe.dev/) for hand landmark detection
- [Keras](https://keras.io/) and [TensorFlow](https://www.tensorflow.org/) for deep learning
- Inspired by open-source sign language recognition projects
