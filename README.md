# 🔴 Crimson Eye – AI-Based Security Camera

## 📌 Project Overview

**Crimson Eye** is an AI-based security camera system that uses computer vision and facial recognition to identify known individuals from a camera feed. The project integrates a camera module, Python, OpenCV, and facial recognition libraries with Raspberry Pi hardware to support automated monitoring and alert mechanisms.

The system captures facial images, generates facial encodings, and compares detected faces against previously stored encodings. Its hardware-integrated implementation also uses a GPIO-controlled LED to indicate a configured recognition condition.

## 🎯 Objectives

* Develop an AI-based camera system for facial detection and recognition.
* Capture facial images and create a dataset for training.
* Generate and store facial encodings for known individuals.
* Recognize faces from a live camera feed.
* Integrate hardware-based indicators with facial recognition.
* Explore the use of AI-assisted surveillance in public safety applications.

## ⚙️ Technologies Used

| Technology       | Purpose                                              |
| ---------------- | ---------------------------------------------------- |
| Python           | Main programming language                            |
| OpenCV           | Image processing and video display                   |
| face_recognition | Facial detection, encoding, and comparison           |
| NumPy            | Numerical operations                                 |
| Raspberry Pi     | Embedded computing platform                          |
| Picamera2        | Camera interfacing on supported Raspberry Pi systems |
| GPIO Zero        | GPIO-controlled LED operation                        |
| Pickle           | Storage and retrieval of facial encoding data        |

## 🔧 Hardware Requirements

* Raspberry Pi compatible with Picamera2
* Compatible camera module
* LED indicator
* Appropriate GPIO connections
* Power supply for the Raspberry Pi
* Computer for development and testing

**Note:** The hardware configuration depends on the Raspberry Pi model and the camera and GPIO components used in the implementation.

## 🧠 How the System Works

The project follows a facial recognition workflow:

1. **Image Capture:** Capture facial images using the camera module.
2. **Dataset Creation:** Organize captured images into folders associated with individual labels.
3. **Model Training:** Process dataset images and generate facial encodings.
4. **Encoding Storage:** Save the generated encodings and corresponding names in `encodings.pickle`.
5. **Face Detection:** Capture video frames and detect faces using the facial recognition library.
6. **Face Matching:** Compare detected facial encodings with stored encodings.
7. **Visual Output:** Display detected faces with bounding boxes and labels.
8. **Hardware Integration:** In the hardware-integrated script, control a GPIO-connected LED according to the configured recognition condition.

**Important:** Recognition results are probabilistic and can be incorrect. A match should not be treated as proof of identity or criminal activity.

## 📂 Project Structure

```text
Crimson-Eye/
│
├── facial_recognition.py
├── facial_recognition_hardware.py
├── image_capture.py
├── image_capture1.py
├── model_training.py
├── encodings.pickle
├── requirements.txt
├── .gitignore
└── README.md
```

The structure above describes the main files. Add `encodings.pickle` only if it contains authorized test data and is appropriate to share. Otherwise, generate it locally using the training script.

## 📄 Description of Source Files

### 1. `image_capture.py`

Captures facial images through the camera and stores them in person-specific folders inside the `dataset` directory.

### 2. `image_capture1.py`

Contains another image-capture implementation. Check whether it serves a distinct purpose before maintaining both files.

### 3. `model_training.py`

Reads images from the dataset, extracts facial encodings, and saves the encodings and corresponding labels in `encodings.pickle`.

### 4. `facial_recognition.py`

Loads stored facial encodings, processes camera frames, compares detected faces with known encodings, and displays the recognition results.

### 5. `facial_recognition_hardware.py`

Extends the recognition workflow with GPIO integration. It controls an LED according to whether a recognized name matches the configured `authorized_names` list.

## 💻 Software Requirements

* Python
* OpenCV
* face_recognition
* NumPy
* imutils
* GPIO Zero
* Picamera2
* A compatible Raspberry Pi operating system and camera setup

Some dependencies, particularly `face_recognition`, may require additional system libraries and compatible Python versions.

## 🚀 Installation and Execution

### Step 1: Clone the Repository

```bash
git clone aravind16112005-pixel/Crimson-Eye
cd Crimson-Eye
```

Replace `aravind16112005-pixel/Crimson-Eye` with your actual GitHub repository URL.

### Step 2: Install Dependencies

On a compatible Raspberry Pi environment, install the required packages using the appropriate installation method for your operating system.

For example:

```bash
sudo apt update
sudo apt install python3-picamera2
```

Install the remaining Python dependencies according to their compatibility requirements.

### Step 3: Capture Facial Images

Run the image-capture script:

```bash
python image_capture.py
```

Follow the instructions displayed by the program to capture images.

### Step 4: Generate Facial Encodings

Run the training script:

```bash
python model_training.py
```

Ensure that the `dataset` directory contains valid images organized into person-specific subdirectories.

The script generates `encodings.pickle`.

### Step 5: Run Facial Recognition

Execute:

```bash
python facial_recognition.py
```

The camera feed should display detected faces and their associated labels when the required hardware and dependencies are configured correctly.

### Step 6: Run the Hardware-Integrated Version

Execute:

```bash
python facial_recognition_hardware.py
```

Ensure that the GPIO hardware is connected correctly and that the configured names and GPIO pin match your intended setup.

**Note:** These are execution instructions based on the supplied scripts. Successful execution depends on compatible hardware, dependencies, camera configuration, and valid dataset files.

## 🧪 Testing and Evaluation

The system can be evaluated using authorized test images and controlled camera conditions.

Suggested evaluation areas include:

* Face detection under different lighting conditions
* Recognition performance at different distances
* Processing speed during live video capture
* Recognition errors and false matches
* Hardware indicator operation
* System stability during continuous execution

Record actual measurements and test results before reporting accuracy, processing speed, or other performance figures.

## 🔐 Privacy and Responsible Use

Facial recognition involves sensitive biometric information. The system should be tested and deployed responsibly.

* Obtain appropriate authorization before collecting or processing facial images.
* Protect stored facial images and encodings.
* Avoid uploading personal biometric data to public repositories.
* Restrict access to recognition data.
* Evaluate false matches and missed detections.
* Do not use a facial recognition result alone to accuse someone of criminal activity.
* Follow applicable privacy, data-protection, and surveillance laws.

## 🔮 Future Enhancements

* Integrate a buzzer for configurable alerts.
* Add timestamped event logging.
* Develop a dashboard for monitoring system activity.
* Evaluate recognition performance under varied lighting and crowd conditions.
* Optimize processing for embedded hardware.
* Add secure storage and access controls.
* Integrate a verified, lawfully maintained database of persons of interest where legally permitted.
* Evaluate alternative face detectors and recognition models.

These are proposed enhancements and should not be interpreted as features already implemented.

## 🏁 Conclusion

Crimson Eye demonstrates an approach to AI-assisted camera monitoring by combining facial image capture, facial encoding, recognition, and embedded hardware integration. The project provides a foundation for exploring real-time computer vision applications and can be extended through systematic testing, performance optimization, improved alert mechanisms, and privacy-conscious design.

---

**Project Name:** Crimson Eye
**Domain:** Artificial Intelligence, Computer Vision, and Embedded Systems
**Programming Language:** Python
**Primary Platform:** Compatible Raspberry Pi system
**Project Type:** AI-Based Security Camera Prototype
