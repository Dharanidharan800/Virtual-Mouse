### Virtual Mouse using Hand Tracking

This code utilizes the Mediapipe library to perform hand tracking and control a virtual mouse using OpenCV, Mediapipe, and PyAutoGUI.

### Prerequisites

- Python 3.x
- OpenCV (`pip install opencv-python`)
- Mediapipe (`pip install mediapipe`)
- PyAutoGUI (`pip install pyautogui`)

### Instructions

1. **Install Dependencies:**

   Make sure to install the required dependencies using the commands mentioned in the prerequisites.

2. **Run the Code:**

   Execute the script using the following command:

   ```bash
   python virtual_mouse.py
   ```

3. **Hand Tracking:**

   The script captures video from the default camera (usually the webcam). It uses the `mediapipe` library to detect and track hands in the video stream.

4. **Virtual Mouse Control:**

   The index finger and thumb are used to control the virtual mouse. The code maps the positions of the index finger and thumb in the camera frame to the screen dimensions.

   - The yellow circle represents the position of the index finger.
   - The green circle represents the position of the thumb.

   If the thumb is close to the index finger:
   - If the distance is less than 20 pixels, it simulates a click using `pyautogui.click()`.
   - If the distance is less than 100 pixels but more than 20 pixels, it moves the mouse cursor using `pyautogui.moveTo()`.

5. **Adjusting Sensitivity:**

   You can modify the threshold values (20 and 100) in the code to adjust the sensitivity of the virtual mouse control based on your preferences.

6. **Exit the Program:**

   Press `Ctrl+C` in the terminal to exit the program.

### Code Explanation

- `cv2.VideoCapture(0)`: Opens the default camera (usually the webcam).

- `mp.solutions.hands.Hands()`: Initializes the hand tracking model from Mediapipe.

- `pyautogui.size()`: Retrieves the screen resolution.

- The code continuously captures video frames, processes them for hand tracking, and updates the virtual mouse position accordingly.

- The `pyautogui.click()` and `pyautogui.moveTo()` functions are used to simulate mouse clicks and cursor movement.

- The `cv2.imshow('Virtual Mouse', frame)` displays the processed video frame with hand landmarks.

- `cv2.waitKey(1)`: Waits for a key event, allowing the script to be interrupted with a `Ctrl+C` command.

Feel free to customize the code and parameters to suit your needs.
