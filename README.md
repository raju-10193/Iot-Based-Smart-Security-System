[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)  
[![Python 3.x](https://img.shields.io/badge/python-3.x-blue.svg)](https://www.python.org/downloads/)
Overview

This project implements an IoT-based smart security system using a Raspberry Pi, PiCamera, and AI-powered face recognition. The system enhances security by:

Detecting and recognizing faces.

Estimating the age and gender of detected individuals.

Identifying unauthorized individuals ("Imposters").

Providing real-time alerts through buzzer activation and email notifications.

This system is suitable for home security, office access control, and other applications requiring enhanced surveillance.

Features

Face Recognition: Identifies known individuals from a database of faces.

Age and Gender Detection: Estimates the age and gender of detected faces using deep learning.

Imposter Detection: Flags unknown individuals as imposters.

Real-time Alerts:

Buzzer activation upon imposter detection.

Email notifications with attached image of the detected person.

Modular Code Design: Well-structured and documented Python code for easy maintenance and extension.

Known Person's Friend Identification: If a known person is detected, unknown faces are labeled as their friend.

Hardware Components

Raspberry Pi (e.g., Raspberry Pi 4)

PiCamera

Buzzer

GPIO Modules (for buzzer control)

Software Components

Python 3.x

OpenCV (cv2)

face_recognition library

Deep Learning Models (Caffe) for Age and Gender Detection

RPi.GPIO

smtplib, ssl, email (for email functionality)

matplotlib (for displaying the processed image)

Installation

Clone the repository:

git clone https://github.com/raju-10193/Iot-Face-Recognition-Security.git

Navigate to the project directory:

cd iot-security-system

Install the dependencies:

pip install -r requirements.txt

Download Pre-trained Models:

Download the pre-trained Caffe models for age and gender detection and place them in the models/ directory.

Ensure the paths in the code (AGE_PROTO, AGE_MODEL, GENDER_PROTO, GENDER_MODEL) point to the correct locations of your model files.

Prepare Known Faces:

Place images of known individuals in the known_faces/ directory.

Name the image files with the names of the individuals (e.g., john_doe.jpg).

Configure Email Settings:

In the main Python script, update the following variables with your email credentials:

SENDER_EMAIL

RECEIVER_EMAIL

EMAIL_PASSWORD (Use an app password if you have 2-Step Verification enabled for your Gmail account.)

Hardware Setup:

Connect the PiCamera and buzzer to your Raspberry Pi according to the appropriate GPIO pinout.

Modify the BUZZER_PIN variable in the code to match the GPIO pin you are using.

Usage

Ensure all hardware components are connected correctly.

Verify that the required software (Python, OpenCV, etc.) is installed on your Raspberry Pi.

Run the main script:

python code/main.py

The system will capture an image, detect faces, predict age and gender, and provide alerts if an imposter is detected.

Project Structure

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

Results

The system has been tested to successfully:

Recognize known faces with reasonable accuracy.

Detect imposters and trigger alerts (buzzer and email).

Estimate age and gender with acceptable accuracy.

Note: Face recognition accuracy may vary depending on lighting conditions, image resolution, and the quality of images in the known_faces/ directory.

Future Work

Enhance Face Recognition Accuracy: Implement techniques to improve face recognition under different lighting and angle variations.

Cloud Integration: Store captured images, logs, and recognized face data in a cloud database for remote access and scalability.

Mobile App Integration: Develop a mobile application to provide real-time notifications and remote monitoring capabilities.

Additional Biometrics: Integrate other biometric authentication methods such as voice recognition or fingerprint recognition for multi-factor authentication.

Optimize Performance: Improve the system's processing speed and efficiency for real-time applications.

Author

Raju Raccha

License

This project is licensed under the MIT License.

Acknowledgments

OpenCV documentation: https://opencv.org

Face Recognition library: https://github.com/ageitgey/face_recognition

Raspberry Pi official site: https://www.raspberrypi.org

Caffe model for age and gender prediction: https://github.com/tringn/AgeGenderPrediction

Dlib Face Recognition Library - http://dlib.net/

Email Automation with Python (smtplib) - https://docs.python.org/3/library/smtplib.html

Raspberry Pi GPIO Library Documentation - https://gpiozero.readthedocs.io/en/stable/

Face Detection with Deep Learning (MTCNN) - https://github.com/ipazc/mtcnn

└── .gitignore            # Specifies intentionally untracked files

