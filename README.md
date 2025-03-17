[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)  
[![Python 3.x](https://img.shields.io/badge/python-3.x-blue.svg)](https://www.python.org/downloads/)
## Overview

This project implements an IoT-based smart security system using a Raspberry Pi, PiCamera, and AI-powered face recognition. [cite: 2, 3, 4] The system enhances security by:

* Detecting and recognizing faces. [cite: 14]
* Estimating the age and gender of detected individuals. [cite: 14]
* Identifying unauthorized individuals ("Imposters"). [cite: 15]
* Providing real-time alerts through buzzer activation and email notifications. [cite: 15]

This system is suitable for home security, office access control, and other applications requiring enhanced surveillance. [cite: 7]

## Features

* **Face Recognition:** Identifies known individuals from a database of faces. [cite: 14, 18]
* **Age and Gender Detection:** Estimates the age and gender of detected faces using deep learning. [cite: 14, 17]
* **Imposter Detection:** Flags unknown individuals as imposters. [cite: 15]
* **Real-time Alerts:**
    * Buzzer activation upon imposter detection. [cite: 9, 15]
    * Email notifications with attached image of the detected person. [cite: 12, 15, 19]
* **Modular Code Design:** Well-structured and documented Python code for easy maintenance and extension.
* **Known Person's Friend Identification**: If a known person is detected, unknown faces are labeled as their friend.

## Hardware Components

* Raspberry Pi (e.g., Raspberry Pi 4) [cite: 8]
* PiCamera [cite: 8]
* Buzzer [cite: 9]
* GPIO Modules (for buzzer control) [cite: 9]

## Software Components

* Python 3.x [cite: 10]
* OpenCV (cv2) [cite: 10]
* face\_recognition library [cite: 11, 18]
* Deep Learning Models (Caffe) for Age and Gender Detection [cite: 11]
* RPi.GPIO
* smtplib, ssl, email (for email functionality) [cite: 12]
* matplotlib (for displaying the processed image)

## Installation

1.  **Clone the repository:**

    ```bash
    git clone <your_repository_url>
    ```

2.  **Navigate to the project directory:**

    ```bash
    cd iot-security-system
    ```

3.  **Install the dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4.  **Download Pre-trained Models:**

    * Download the pre-trained Caffe models for age and gender detection and place them in the `models/` directory.  
        * You can find suitable models at the provided link in the document [cite: 36] or search for alternatives.
    * Ensure the paths in the code (`AGE_PROTO`, `AGE_MODEL`, `GENDER_PROTO`, `GENDER_MODEL`) point to the correct locations of your model files.

5.  **Prepare Known Faces:**

    * Place images of known individuals in the `known_faces/` directory.
    * Name the image files with the names of the individuals (e.g., `john_doe.jpg`). [cite: 40]

6.  **Configure Email Settings:**

    * In the main Python script, update the following variables with your email credentials:
        * `SENDER_EMAIL`
        * `RECEIVER_EMAIL`
        * `EMAIL_PASSWORD` (Use an app password if you have 2-Step Verification enabled for your Gmail account.)

7.  **Hardware Setup:**

    * Connect the PiCamera and buzzer to your Raspberry Pi according to the appropriate GPIO pinout.
    * Modify the `BUZZER_PIN` variable in the code to match the GPIO pin you are using.

## Usage

1.  **Ensure all hardware components are connected correctly.**
2.  **Verify that the required software (Python, OpenCV, etc.) is installed on your Raspberry Pi.**
3.  **Run the main script:**

    ```bash
    python code/main.py
    ```

4.  The system will capture an image, detect faces, predict age and gender, and provide alerts if an imposter is detected.

## Project Structure
iot-security-system/
├── code/
│   ├── main.py           # Main script
│   ├── ...               # Other Python modules (if any)
├── models/
│   ├── deploy_age.prototxt   # Age detection model
│   ├── age_net.caffemodel    # Age detection model
│   ├── deploy_gender.prototxt # Gender detection model
│   ├── gender_net.caffemodel  # Gender detection model
├── known_faces/
│   ├── person1.jpg       # Images of known individuals
│   ├── person2.jpg
│   ├── ...
├── docs/
│   └── project_report.pdf  # (Optional) Project documentation
├── requirements.txt      # Python dependencies
└── README.md             # Project overview and instructions
## Results

The system has been tested to successfully:

* Recognize known faces with reasonable accuracy. [cite: 20, 25, 26, 27]
* Detect imposters and trigger alerts (buzzer and email). [cite: 22, 26]
* Estimate age and gender with acceptable accuracy. [cite: 21, 27]

**_Note:_** Face recognition accuracy may vary depending on lighting conditions, image resolution, and the quality of images in the `known_faces/` directory. [cite: 28]

## Future Work

* **Enhance Face Recognition Accuracy:** Implement techniques to improve face recognition under different lighting and angle variations. [cite: 29, 32]
* **Cloud Integration:** Store captured images, logs, and recognized face data in a cloud database for remote access and scalability. [cite: 33]
* **Mobile App Integration:** Develop a mobile application to provide real-time notifications and remote monitoring capabilities. [cite: 34]
* **Additional Biometrics:** Integrate other biometric authentication methods such as voice recognition or fingerprint recognition for multi-factor authentication. [cite: 35]
* **Optimize Performance:** Improve the system's processing speed and efficiency for real-time applications.

## Author

* Ramasoujanya9

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

## Acknowledgments

* OpenCV documentation: [https://opencv.org](https://opencv.org) [cite: 36]
* Face Recognition library: [https://github.com/ageitgey/face\_recognition](https://github.com/ageitgey/face_recognition) [cite: 36]
* Raspberry Pi official site: [https://www.raspberrypi.org](https://www.raspberrypi.org) [cite: 36]
* Caffe model for age and gender prediction: [https://github.com/tringn/AgeGenderPrediction](https://github.com/tringn/AgeGenderPrediction) [cite: 36] (or other sources for models)
* Dlib Face Recognition Library - [http://dlib.net/](http://dlib.net/) [cite: 36]
* Email Automation with Python (smtplib) - [https://docs.python.org/3/library/smtplib.html](https://docs.python.org/3/library/smtplib.html) [cite: 36]
* Raspberry Pi GPIO Library Documentation - [https://gpiozero.readthedocs.io/en/stable/](https://gpiozero.readthedocs.io/en/stable/) [cite: 36]
* Face Detection with Deep Learning (MTCNN) - [https://github.com/ipazc/mtcnn](https://github.com/ipazc/mtcnn) [cite: 36]
└── .gitignore            # Specifies intentionally untracked files
