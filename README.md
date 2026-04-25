# 📱 SmartApp — Real-Time Image Classification on Android

> 🤖 An Android application that leverages on-device machine learning to classify objects in real time through the device camera.

---

## 📌 Overview

SmartApp is a native Android application built with Kotlin that integrates a custom-trained TensorFlow Lite model to perform real-time image classification. The model was trained using Google Teachable Machine and optimized for mobile inference using quantization techniques.

The application processes live camera frames, runs inference on-device without any internet connection, and displays classification results with confidence scores — all in milliseconds.

---

## 🎬 Demo

```
📷 Camera Feed  →  🖼️ Frame Capture  →  ⚡ TFLite Inference  →  ✅ Result + Confidence Score
```

---

## ✨ Features

- 📷 Real-time object classification via device camera
- 🔒 On-device inference — no internet required
- 🧠 Custom AI model trained with Google Teachable Machine
- ⚡ GPU acceleration support via TensorFlow Lite GPU Delegate
- 🎯 Configurable inference parameters (threshold, max results, threads)
- 📱 Built with CameraX for reliable camera lifecycle management

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| 💻 Language | Kotlin |
| 🎨 UI | XML Layouts |
| 📷 Camera | CameraX |
| 🤖 ML Framework | TensorFlow Lite |
| 🏋️ Model Training | Google Teachable Machine |
| ⚙️ Build System | Gradle |
| 🛠️ IDE | Android Studio |

---

## 📁 Project Structure

```
app/
└── src/
    └── main/
        ├── assets/
        │   └── converted_tflite_quantized/
        │       ├── model.tflite       # Trained TFLite model
        │       └── labels.txt         # Classification labels
        ├── java/
        │   └── org.tensorflow.lite.examples.imageclassification/
        │       ├── ImageClassifierHelper.kt   # ML inference logic
        │       ├── MainActivity.kt            # App entry point
        │       └── fragments/
        │           └── CameraFragment.kt      # Camera & UI logic
        └── res/                               # Layouts & resources
```

---

## 🔑 Key Components

### `ImageClassifierHelper.kt`
Manages the TFLite model lifecycle. Handles model loading from assets, configures inference options (delegate, threads, threshold), and exposes a `classify()` method that accepts a bitmap and returns classification results.

### `CameraFragment.kt`
Integrates CameraX to capture live frames and passes them to `ImageClassifierHelper`. Handles camera permissions, rotation, and real-time display of results.

### `MainActivity.kt`
Entry point of the application. Sets up navigation and manages the overall UI structure.

---

## 🚀 Getting Started

### Prerequisites
- Android Studio Flamingo or newer
- Android device running Android 6.0+ (API 23+)
- Physical device recommended for camera functionality

### Installation

```bash
git clone https://github.com/zaydkassimi/SmartApp.git
```

1. Open the project in Android Studio
2. Wait for Gradle sync to complete
3. Connect a physical Android device with USB debugging enabled
4. Click **Run ▶**

---

## 🧠 Model Integration

The AI model was trained using **Google Teachable Machine**:

1. Collected image samples per class on Teachable Machine
2. Trained and exported as a **Quantized TFLite** model
3. Placed `model.tflite` and `labels.txt` inside `assets/converted_tflite_quantized/`
4. Configured `ImageClassifierHelper.kt` to load the custom model path

---

## 👨‍💻 Developer

**Zayd Kassimi**
GitHub: [@zaydkassimi](https://github.com/zaydkassimi)

---

## 🙏 Acknowledgements

This project is based on the [TensorFlow Lite Examples](https://github.com/tensorflow/examples) repository by Google, adapted and customized for academic purposes.
