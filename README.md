# Coral Reef Health Classification

A mobile application that classifies coral reef health using image analysis powered by a Support Vector Machine (SVM) model. Built as a Final Year Project for Bachelor of Computer Science (Hons.) at UiTM.

## 📱 Overview

This system allows users to upload or capture coral reef images via a Flutter mobile app, which sends the image to a Flask API for real-time classification. The model predicts whether the coral is **Healthy** or **Bleached**, along with a confidence score.

## Tech Stack

| Layer | Technology |
|---|---|
| Mobile App | Flutter (Dart) |
| Backend API | Python Flask |
| ML Model | Support Vector Machine (SVM) |
| Image Processing | OpenCV |
| Model Serialization | Pickle |

## How It Works

1. User uploads or captures a coral reef image via the Flutter app
2. Image is sent to the Flask API via a POST request to `/predict`
3. The image is preprocessed — converted to grayscale, resized to 200×200, and normalized
4. The SVM model predicts the class and confidence scores
5. Result is returned as JSON and displayed in the app

### Example API Response
```json
{
  "Prediction": "Healthy",
  "Confidence": {
    "Healthy": 0.87,
    "Bleached": 0.13
  }
}
```

## Model Performance

- **Algorithm:** Support Vector Machine (SVM)
- **Accuracy:** 77.86%
- **Classes:** Healthy, Bleached
- **Dataset:** Public coral reef image dataset from [Kaggle](https://www.kaggle.com/)

## Getting Started

### Flask API
```bash
pip install flask numpy opencv-python scikit-learn
python app.py
```

### Flutter App
```bash
cd "Coral Classification/coralclassify"
flutter pub get
flutter run
```

## Author

**Nur Athirah** — Bachelor of Computer Science (Hons.), UiTM