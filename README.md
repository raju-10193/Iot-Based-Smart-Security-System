#   IoT-Based Smart Security System Using Face Recognition, Age, and Gender Detection

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.x](https://img.shields.io/badge/python-3.x-blue.svg)](https://www.python.org/downloads/)

##   Overview

This project implements an IoT-based smart security system leveraging a Raspberry Pi, PiCamera, and AI-powered face recognition. The system enhances security through:

* Detecting and recognizing faces.
* Estimating the age and gender of detected individuals.
* Identifying unauthorized individuals ("Imposters").
* Providing real-time alerts via buzzer activation and email notifications.

This system is well-suited for applications such as home security, office access control, and other scenarios requiring enhanced surveillance.

##   Features

* **Face Recognition:** Identifies known individuals by comparing detected faces against a database of faces.
* **Age and Gender Detection:** Estimates the age and gender of detected faces using deep learning techniques.
* **Imposter Detection:** Flags unknown individuals as imposters, triggering security protocols.
* **Real-time Alerts:**
    * Buzzer activation upon imposter detection for immediate local notification.
    * Email notifications with attached images of detected individuals for remote monitoring.
* **Modular Code Design:** Employs well-structured and documented Python code to facilitate easy maintenance and future extension of the system.
* **Known Person's Friend Identification:** Enhances contextual awareness by labeling unknown faces as "friends" when a known person is also detected.

##   Hardware Components

* Raspberry Pi (e.g., Raspberry Pi 4) - Serves as the system's processing unit.
* PiCamera - Captures images for facial recognition and analysis.
* Buzzer - Provides audible alerts for imposter detection.
* GPIO Modules - Enables control of hardware components, specifically the buzzer.

##   Software Components

* Python 3.x - The primary programming language used for system implementation.
* OpenCV (cv2) - A powerful library utilized for image processing and face detection.
* `face_recognition` library - Facilitates the identification of known faces.
* Deep Learning Models (Caffe) - Pre-trained models employed for age and gender classification.
* RPi.GPIO - A Python library enabling interaction with Raspberry Pi GPIO pins.
* `smtplib`, `ssl`, `email` - Python libraries used for email functionality, enabling alert notifications.
* `matplotlib` - A plotting library used for displaying the processed image output.

##   Installation

1.  **Clone the repository:**

    ```bash
    git clone [https://github.com/raju-10193/Iot-Face-Recognition-Security.git](https://github.com/raju-10193/Iot-Face-Recognition-Security.git)
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
    * Ensure the paths defined in the code (`AGE_PROTO`, `AGE_MODEL`, `GENDER_PROTO`, `GENDER_MODEL`) accurately point to the locations of your model files.

5.  **Prepare Known Faces:**

    * Place images of known individuals in the `known_faces/` directory.
    * Name the image files using the names of the individuals (e.g., `john_doe.jpg`).

6.  **Configure Email Settings:**

    * Within the main Python script, update the following variables with your specific email credentials:
        * `SENDER_EMAIL`
        * `RECEIVER_EMAIL`
        * `EMAIL_PASSWORD` (If using Gmail, utilize an app password if 2-Step Verification is enabled.)

7.  **Hardware Setup:**

    * Connect the PiCamera and buzzer to your Raspberry Pi, adhering to the appropriate GPIO pinout.
    * Modify the `BUZZER_PIN` variable within the code to correspond to the GPIO pin you have utilized for the buzzer.

##   Usage

1.  **Ensure** that all hardware components are correctly connected and functional.
2.  **Verify** that the required software (Python, OpenCV, etc.) is installed and configured on your Raspberry Pi.
3.  **Execute** the main script to initiate the security system:

    ```bash
    python code/main.py
    ```

4.  The system will then capture images, detect faces, predict age and gender, and provide alerts upon the detection of an imposter.

##   Project Structure
iot-security-system/
├── code/
│   ├── main.py                # Main script
│   ├── ...                    # Other Python modules (if any)
├── models/
│   ├── deploy_age.prototxt      # Age detection model
│   ├── age_net.caffemodel       # Age detection model
│   ├── deploy_gender.prototxt   # Gender detection model
│   ├── gender_net.caffemodel    # Gender detection model
├── known_faces/
│   ├── person1.jpg            # Images of known individuals
│   ├── person2.jpg
│   ├── ...
├── docs/
│   └── project_report.pdf     # (Optional) Project documentation
├── requirements.txt           # Python dependencies
└── README.md                  # Project overview and instructions
└── .gitignore                 # Specifies intentionally untracked files
##   Results

The system has undergone testing and successfully demonstrates the ability to:

* Recognize known faces with a reasonable degree of accuracy.
* Detect imposters and effectively trigger alerts through both buzzer and email notifications.
* Estimate age and gender with acceptable accuracy based on the test cases performed.

**_Note:_** Face recognition accuracy can be influenced by factors such as lighting conditions, image resolution, and the quality of the images provided in the `known_faces/` directory.

##   Future Work

* **Enhance Face Recognition Accuracy:** Implement advanced techniques to improve face recognition performance under varying lighting and angle conditions.
* **Cloud Integration:** Integrate cloud-based services to enable storage of captured images, logs, and recognized face data, facilitating remote access and improved scalability.
* **Mobile App Integration:** Develop a dedicated mobile application to provide users with real-time notifications, remote monitoring capabilities, and system control.
* **Additional Biometrics:** Explore the integration of other biometric authentication methods, such as voice recognition or fingerprint recognition, to implement multi-factor authentication for enhanced security.
* **Optimize Performance:** Focus on improving the system's processing speed and overall efficiency to ensure optimal performance in real-time applications.

##   Author

* Raju Raccha

##   License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

##   Acknowledgments

* OpenCV documentation: [https://opencv.org](https://opencv.org)
* Face Recognition library: [https://github.com/ageitgey/face_recognition](https://github.com/ageitgey/face_recognition)
* Raspberry Pi official site: [https://www.raspberrypi.org](https://www.raspberrypi.org)
* Caffe model for age and gender prediction: [https://github.com/tringn/AgeGenderPrediction](https://github.com/tringn/AgeGenderPrediction)
* Dlib Face Recognition Library - [http://dlib.net/](http://dlib.net/)
* Email Automation with Python (smtplib): [https://docs.python.org/3/library/smtplib.html](https://docs.python.org/3/library/smtplib.html)
* Raspberry Pi GPIO Library Documentation: [https://gpiozero.readthedocs.io/en/stable/](https://gpiozero.readthedocs.io/en/stable/)
* Face Detection with Deep Learning (MTCNN): [https://github.com/ipazc/mtcnn](https://github.com/ipazc/mtcnn)
