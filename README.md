# FaceLock: Home Security with Facial Recognition
<!-- Insert FaceLock Logo Here -->

FaceLock is a home security concept that utilizes facial recognition technology to unlock or lock a door based on the detected faces. This project uses a Raspberry Pi 4 camera, OpenCV's Haar Cascade Classifier model for face detection, and a servo motor-controlled door lock. By integrating these components, FaceLock provides a secure and convenient way to control access to your home.

## Features
- Facial recognition using OpenCV's Haar Cascade Classifier model
- Automatic door lock control with a servo motor
- Real-time face detection and recognition
- Easy setup and configuration
- Hardware Requirements

To build the FaceLock system, we used the following hardware components:

- Raspberry Pi 4
- Raspberry Pi camera module
- Servo Motor (for door lock control)

As for the software & AI components we used:
- Python 3
- OpenCV library
- imutils library
- face_recognition library
- gpiozero library (for servo control)

## Project Demo
You can have a look at our final project demo here: [FaceLock in Action](https://drive.google.com/file/d/1MSJXx8kaxo2CHHl3j4GoGNeAMdz5Siov/view?usp=drive_link)

## Installation
1. **Clone** the FaceLock repository from GitHub:

```bash
git clone https://github.com/Hamza-Mos/FaceLock.git
```
2. **Install** the required Python packages:

```bash
pip install opencv-python imutils face_recognition gpiozero
```
3. **Download** the pre-trained Haar Cascade Classifier model for face detection from OpenCV:

```bash
wget https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_frontalface_default.xml
```
4. **Place** the downloaded haarcascade_frontalface_default.xml file in the FaceLock directory.

5. **Add** the necessary details for servo control in the facial_recognition.py file:

```python
from gpiozero import AngularServo
servo = AngularServo(18, initial_angle=90, min_pulse_width=0.0006, max_pulse_width=0.0023)
```
6. **Train** the facial recognition model by running the train_model.py script. This script will process the images in the dataset folder and generate face encodings:

```bash
python train_model.py
```
7. **Run** the facial_recognition.py script to start the FaceLock system:

```bash
python facial_recognition.py
```

## Usage
- Ensure that the Raspberry Pi is connected to the camera module.
- Run the ```facial_recognition.py``` script.
- The system will start the video stream and display the live feed with face bounding boxes.
- When a recognized face is detected, the system will unlock the door by controlling the servo motor.
- To lock the door, simply remove the recognized face from the camera's view.

## Contributing
Contributions to the FaceLock project are welcome! If you have any ideas, improvements, or bug fixes, please submit a pull request. For major changes, please open an issue first to discuss your proposed changes.

## Acknowledgments
 - **OpenCV** - Open source computer vision library
 - **imutils** - A series of convenience functions for computer vision tasks
 - **face_recognition** - Recognize and manipulate faces using Python and the dlib library
 - **gpiozero** - A simple interface to GPIO devices with Raspberry Pi

<!-- ## Troubleshooting
If you encounter any issues while setting up or using FaceLock, please try the following steps:

Make sure all the required hardware components are connected properly.

Check that the software dependencies are installed correctly.

Verify that the face encodings file (encodings.pickle) is generated after running the train_model.py script.

Ensure that the camera is working and capturing the video feed.

If the problem persists, please open an issue on the GitHub repository with detailed information about the error and steps to reproduce it.
 -->
## FAQ
- **Q: How many faces can FaceLock recognize?**
  - A: FaceLock can recognize multiple faces. The number of faces it can handle depends on the available system resources and the accuracy of the facial recognition model.

- **Q: Can I use a different servo motor for the door lock?**
  - A: Yes, you can use a different servo motor as long as it is compatible with the Raspberry Pi and can be controlled using the gpiozero library.

- **Q: How secure is FaceLock?**
  - A: FaceLock provides an additional layer of security by using facial recognition technology. However, it is important to note that facial recognition systems can have limitations and vulnerabilities. FaceLock should be considered as a part of a comprehensive home security system and not solely relied upon for security.

- **Q: Can I customize the behavior of FaceLock?**
  - A: Yes, you can modify the facial_recognition.py file to add or change the functionality of FaceLock. For example, you can integrate it with other smart home devices or add additional actions based on face recognition events.

## Credits
This project was created by **[Hamza Mostafa](https://github.com/Hamza-Mos)**, **[Shaikh Ayman Abdul-Majid](https://github.com/sabdulmajid)**, **Darsh Patel**, **[Abdur-Rahman Shoaib](https://github.com/a3shoaib)**, and **Sparsh Patel**.
