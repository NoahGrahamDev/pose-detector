# Body Language Detection using Mediapipe and Machine Learning

This project implements a real-time body language detection system using the Mediapipe Holistic model and a machine learning classifier. The system captures live video from a webcam, processes it using Mediapipe to extract facial and body landmarks, and then uses a trained model to classify body language based on these landmarks.

## Features

- **Real-time Detection:** Uses a webcam feed to detect face, hand, and pose landmarks in real time.
- **Custom Body Language Classification:** Uses a machine learning model for body language classification.
- **Visual Landmark Rendering:** Visualizes the detected landmarks (face, hands, pose) on the video feed.
- **Probability Output:** Displays classification results with the associated prediction probability.

## Dependencies

To run this project, you will need the following dependencies:

- Python 3.x
- OpenCV (`opencv-python`)
- Mediapipe (`mediapipe`)
- Numpy (`numpy`)
- Pandas (`pandas`)
- Pickle (for loading/saving machine learning models)

### Install the required packages:

```bash
pip install mediapipe opencv-python numpy pandas
```

## Files in the Repository

- `main.py`: The main script that captures video from the webcam, extracts landmarks, and runs the body language detection.
- `requirements.txt`: A list of the required dependencies (can be generated if not already included).

## Important: Model Not Included

This repository **does not include the pre-trained machine learning model (`body_language.pkl`)**. You will need to either:

1. **Train your own model**: Use a dataset of body language and facial/pose landmarks, then train a classifier (e.g., Random Forest, SVM, etc.) to recognize different body language types. The model should accept Mediapipe landmarks as input.
2. **Use an existing model**: If you already have a body language classification model, ensure it is compatible with the landmark data produced by Mediapipe and save it in `.pkl` format using Python’s `pickle` module.

### How to Train Your Own Model:

1. **Capture Data**: Use the provided script to capture body language landmarks (pose, face, hands) from the webcam. Save these landmarks to a `.csv` file.
2. **Train a Classifier**: Use machine learning algorithms such as Random Forest, SVM, or K-Nearest Neighbors to classify body language based on the landmarks.
3. **Save the Model**: Once you’ve trained your classifier, save it as a `.pkl` file using `pickle`:

   ```python
   import pickle

   # Save model to a .pkl file
   with open('body_language.pkl', 'wb') as f:
       pickle.dump(your_trained_model, f)
   ```

   The model should output both the predicted class and the probability of the prediction.

4. **Modify the Script**: Replace the prediction part in the `main.py` script with your trained model.

## How It Works

1. **Capturing Webcam Feed**: The system uses OpenCV to capture video from the webcam.
2. **Landmark Detection**: Mediapipe Holistic is used to detect face, hand, and pose landmarks.
3. **Data Preprocessing**: The extracted landmarks are flattened into a single array and passed to the classifier.
4. **Classification**: Your trained model will classify the user's body language based on the extracted landmarks.
5. **Result Display**: The predicted class and the associated probability are displayed on the video feed.

## Usage

1. Clone this repository:

```bash
git clone https://github.com/your-username/body-language-detection.git
```

2. Install the dependencies:

```bash
pip install -r requirements.txt
```

3. **Train your own model** or **use an existing `.pkl` model** for body language classification. Place the `.pkl` file in the same directory as the script.

4. Run the script:

```bash
python main.py
```

5. Press `q` to quit the webcam feed.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contributing

Contributions are welcome! Feel free to fork the repository, make your changes, and submit a pull request.

---

Enjoy building your own body language detection system!
