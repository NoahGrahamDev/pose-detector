# Body Language Detection using Mediapipe and Machine Learning

This project implements a real-time body language detection system using the Mediapipe Holistic model and a pre-trained machine learning model. The system captures live video from a webcam, processes it using Mediapipe, extracts relevant facial and body landmarks, and then uses a trained model to classify the user's body language based on these landmarks.

## Features

- **Real-time Detection:** Uses a webcam feed to detect face, hands, and pose landmarks in real-time.
- **Body Language Classification:** Classifies body language based on extracted landmarks using a pre-trained model.
- **Visual Landmark Rendering:** Visualizes detected landmarks (face, hands, pose) directly on the video feed.
- **Probability Output:** Displays the classification result with the associated probability of the prediction.

## Dependencies

To run this project, you will need the following dependencies:

- Python 3.x
- OpenCV (`opencv-python`)
- Mediapipe (`mediapipe`)
- Numpy (`numpy`)
- Pandas (`pandas`)
- Pickle (for loading the pre-trained model)

### Install the required packages:

```bash
pip install mediapipe opencv-python numpy pandas
```

## Files in the Repository

- `main.py`: The main script that runs the body language detection system using the webcam.
- `body_language.pkl`: The pre-trained machine learning model used for body language classification.
- `coords.csv`: (Optional) If uncommented in the script, this file can be used to store the extracted pose and face landmarks as CSV data for further analysis.
- `requirements.txt`: A list of all the required dependencies (can be generated if not already included).

## How it Works

1. **Capturing Webcam Feed**: The system uses OpenCV to capture video from the webcam.
2. **Landmark Detection**: Mediapipe Holistic is used to detect face, hand, and pose landmarks from the video feed.
3. **Data Preprocessing**: The extracted landmarks are flattened into a single array and prepared for prediction.
4. **Classification**: The pre-trained `body_language.pkl` model classifies the extracted landmarks into a body language class.
5. **Result Display**: The detected class and probability are overlaid on the video feed using OpenCV drawing utilities.

## Usage

1. Clone this repository:

```bash
git clone https://github.com/your-username/body-language-detection.git
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Ensure that the `body_language.pkl` file is available in the repository. This file is the trained model used for prediction.

4. Run the script:

```bash
python main.py
```

5. Press `q` to quit the webcam feed.

## Model Training

The pre-trained model (`body_language.pkl`) is used for body language classification. If you wish to retrain the model or use a different dataset, follow these steps:

- Capture landmark data using the provided script.
- Train a machine learning model (e.g., Random Forest, SVM, etc.) using this data.
- Save the trained model using the `pickle` module.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contributing

If you would like to contribute, feel free to fork the repository and submit a pull request. Any enhancements, bug fixes, or improvements are welcome.

---

Enjoy using this real-time body language detection system!
