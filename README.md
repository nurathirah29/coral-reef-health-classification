# Coral Reef Health Classification

A mobile application that classifies coral reef health using image analysis powered by a Support Vector Machine (SVM) model. Built as a Final Year Project for Bachelor of Computer Science (Hons.) at UiTM.

---

## Features

- **Image capture or upload** — Users can take a photo or select one from the gallery via the Flutter app
- **Real-time classification** — Image is sent to the Flask API and results are returned instantly
- **Three-class prediction** — Classifies coral as Healthy, Partially Bleached, or Fully Bleached
- **Confidence scores** — Returns per-class probability alongside the prediction
- **OpenCV preprocessing** — Grayscale conversion, resizing, and normalization before inference
- **REST API** — Lightweight Flask backend with a single `/predict` endpoint

---

## Tech Stack

| Layer | Technology |
|---|---|
| Mobile App | Flutter (Dart) |
| Backend API | Python, Flask |
| ML Model | Support Vector Machine (SVM) |
| Image Processing | OpenCV |
| Model Serialization | Pickle |
| Dataset | Public coral reef dataset from Kaggle |


## How It Works

1. User uploads or captures a coral reef image via the Flutter app
2. Image is sent to the Flask API via a POST request to `/predict`
3. The API preprocesses the image — converted to grayscale, resized to 200×200, and normalized
4. The SVM model predicts the class and returns confidence scores
5. Result is displayed in the Flutter app

### Example API Response

```json
{
  "Prediction": "Healthy",
  "Confidence": {
    "Healthy": 0.87,
    "Bleached": 0.04
  }
}
```

---

## Model Performance

| Metric | Value |
|---|---|
| Algorithm | Support Vector Machine (SVM) |
| Accuracy | 77.86% |
| Classes | Healthy, Partially Bleached, Fully Bleached |
| Input Size | 200 × 200 px (grayscale) |
| Dataset | Public coral reef image dataset from Kaggle |

---

## API Endpoint

| Method | Route | Description |
|---|---|---|
| POST | `/predict` | Accept an image file, return classification result and confidence scores |

**Request:** `multipart/form-data` with an image file field

**Response:** JSON with `Prediction` (string) and `Confidence` (object with per-class scores)

---

## License

Nur Athirah
