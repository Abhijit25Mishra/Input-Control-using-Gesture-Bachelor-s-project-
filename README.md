# Gesture Controlled Mouse

Control your computer mouse remotely using hand gestures.

This is for controlling the computer mouse using hand gestures captured through a webcam. It relies on computer vision techniques to detect and interpret these hand gestures.

## Introduction

The objective of this project is to enable remote mouse control through hand gestures. It utilizes hand detection technology provided by [Mediapipe](https://google.github.io/mediapipe/) and mouse control capabilities offered by [Autopy](https://pypi.org/project/autopy/).

## Getting Started

Before you begin, make sure you have the required dependencies installed in your development environment.

```bash
pip install -r requirements.txt
```

### Formal Explanation:

#### Import Necessary Libraries:

The code begins by importing required libraries, including HandDetectionModule for hand detection, cv2 for computer vision, numpy for numerical operations, math for mathematical functions, autopy for mouse control, and time for timing operations.

#### Set Up the Camera:

It initializes the webcam capture using OpenCV (cv2.VideoCapture), setting the camera resolution.

#### Initialize Variables:

Variables like holdFlag, reducedFrame, smoothening, plocX, and plocY are initialized to manage different aspects of the mouse control.

#### Define Functions:

Several functions are defined to handle different gesture cases, such as 
1. mouse movement (caseMovement), 
2. left-click (caseLeft), 
3. right-click (caseRight), 
4. left button toggle (leftToggleOn and leftToggleOff), 
5. and a default case (caseDefault).

#### Main Loop:

The code enters a continuous loop where it captures frames from the webcam using cap.read().

#### Hand Detection:

The code detects and processes hand gestures using HandDetectionModule. It identifies the positions of different finger points and stores them in variables like thumb, index, middle, ring, and pinky.

#### Gesture Handling:

Based on the number of detected fingers and their positions, the code determines which gesture is being made:
- For one finger, it moves the mouse cursor.
- For two fingers, it checks if they are touching and interprets them as left or right clicks.
- For three fingers, it triggers a hold and drag action.
- If no specific gesture is detected, it defaults to a standard gesture.

#### Mouse Control:

The code utilizes autopy to control the mouse pointer's movement and clicks based on the detected gestures.

#### Display the Video:

It displays the video stream with overlays to visualize the detected hand points and actions using OpenCV.

#### Termination:

The code runs until the user presses the 'Esc' key, at which point it releases the camera and terminates the program.

In summary, this code captures webcam frames, detects hand gestures, and controls the mouse cursor based on the gestures recognized. It offers features like moving the mouse, left and right clicks, and hold-and-drag actions, all controlled by hand movements.
