# Hand Gesture Controlled LEDs

This project allows you to control LEDs using hand gestures detected by a webcam. It uses OpenCV and the HandTrackingModule from cvzone to detect hand gestures, and it controls LEDs connected to an Arduino board using the pyFirmata library.

## Requirements

- Python 3.x
- OpenCV
- cvzone (install using `pip install cvzone`)
- pyFirmata
- Arduino board
- LEDs (5 in this case)

## Setup

1. Connect your Arduino board to your computer.
2. Install the required Python packages using pip:
pip install opencv-python
pip install cvzone

markdown
Copy code
3. Upload the StandardFirmata firmware to your Arduino board. You can find this in the Arduino IDE under `File > Examples > Firmata > StandardFirmata`.
4. Update the `comport` variable in the Python code to match the COM port your Arduino is connected to (e.g., 'COM4' for Windows, '/dev/ttyUSB0' for Linux).
5. Connect your LEDs to the digital pins of your Arduino board. In this code, LEDs are connected to pins 8 through 12.

## Usage

1. Run the Python script.
2. Hold your hand in front of the webcam. The code will detect your hand and fingers.
3. Depending on the number of fingers you raise, the corresponding LEDs will light up.
4. Press 'k' to exit the program.

## Code Explanation

- `controller.py`: This file contains the function `led(fingerUp)`, which controls the LEDs based on the finger count.
- `main.py`: This is the main script. It captures video from the webcam, detects hand gestures, and calls the `led()` function to control the LEDs accordingly.

## Notes

- Make sure your hand is well-lit and visible to the webcam for accurate gesture detection.
- Adjust the `detectionCon` parameter in `HandDetector` to change the hand detection sensitivity.
- Modify the `led()` function in `controller.py` to customize LED behavior based on finger
