AI Virtual Keyboard

This is a project made by Lasya Sadubugga as part of an exploration into gesture-controlled input systems using computer vision and Python.

In this project, we aim to reduce the gap between real-world physical interactions and virtual input systems. The result is a gesture-based virtual keyboard that leverages computer vision techniques to detect and interpret hand gestures, allowing users to type using just their fingers in the air.

The system uses OpenCV for video processing, CVZone and MediaPipe for hand detection, and Pynput to simulate keyboard inputs. A webcam acts as the only required hardware, making this system accessible and hardware-independent.
💡 Problem Statement

As the variety of human-computer interfaces expands, especially for accessibility solutions, traditional keyboard and mouse interfaces prove limiting for many users. This project investigates a new approach—creating a functional virtual keyboard using just a webcam and computer vision.

The goal is to enable input through natural hand gestures, which can be useful in AR/VR environments, public kiosks, or for users with mobility limitations.
🚩 Objective

    Develop a virtual keyboard that detects finger movements to simulate keystrokes.

    Use OpenCV, CVZone, and MediaPipe for real-time hand tracking and gesture recognition.

    Utilize Pynput to simulate physical keyboard input from detected gestures.

    Enhance accessibility and interaction flexibility beyond physical keyboards.

🧠 Methodology
1. Keyboard Layout Model

We define a standard QWERTY layout using a grid of virtual buttons. These buttons are drawn on each video frame using OpenCV’s drawing functions (cv2.rectangle and cv2.putText). Button classes are used to manage their properties.
2. Hand Tracking & Landmark Detection

We use CVZone’s HandTrackingModule, which internally relies on MediaPipe to detect hand landmarks. The system identifies the 21 3D coordinates of hand joints in real time.
3. Click Detection

To simulate a keypress:

    The system checks if the index finger (landmark 8) is hovering over a button.

    If the index and middle finger tips (landmarks 8 and 12) are brought close together (distance < 28 pixels), a "click" is registered.

    The corresponding button is highlighted and its character is added to the output.

4. Output Display

The typed characters are shown in a designated rectangle on the screen. Pressing the < button deletes the last character.
🔧 Technologies Used

    Python

    OpenCV

    CVZone

    MediaPipe

    Pynput


🧩 Future Improvements

    Add support for numbers and special characters.

    Implement swipe gestures for space and enter keys.

    Provide speech feedback for visually impaired users.

    Add multi-language support.

🙌 Credits

    Lasya Sadubugga – Project Author

    Inspired by open-source work on gesture-controlled UIs and CVZone.
