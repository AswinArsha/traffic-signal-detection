## Traffic Signal Detection using OpenCV

This README provides an overview of the Python code designed for real-time traffic signal detection using the OpenCV (cv2) library. The code processes video frames from a camera feed to identify traffic signals by analyzing circular shapes through the Hough Circle Transform.

### Main Function: `get_dominant_color`

The primary function in the code is `get_dominant_color`, which leverages the K-means clustering algorithm to determine the dominant color within an image. This function is crucial for identifying the color of specific regions within the detected traffic signal.

### User Interaction

The code sets up a graphical window named "camera" and includes a mouse callback function (`onMouse`). This callback enables the user to gracefully exit the program by simply clicking on the camera window.

### Frame Processing Loop

Within the main loop, the code follows these steps for each frame from the camera:

1. Converts the frame to grayscale using `cv2.cvtColor`.
2. Applies median blur (`cv2.medianBlur`) to reduce noise and achieve a smoother image.
3. Utilizes the Hough Circle Transform (`cv2.HoughCircles`) to spot circular shapes representing traffic signals.
4. If circles are detected, it selects the largest circle as the main traffic signal, focusing on its radius.
5. Extracts a square Region of Interest (ROI) around the detected signal.
6. The `get_dominant_color` function is employed to calculate the dominant color within the ROI.
7. Based on the dominant color and specific color zones within the ROI, the code determines the traffic signal type.
8. It displays the identified zones and the recognized traffic signal type on separate windows using `cv2.imshow`.
9. The `last_symbol` variable keeps track of the previously identified signal, and it's updated accordingly.
10. When a new signal is identified, it prints the symbol to the console.
11. Draws circles around the detected signals on the original frame using `cv2.circle`.
12. The processed frame is shown in the "camera" window using `cv2.imshow`.

### User Interaction and Program Termination

To end the loop, the user can click on the "camera" window. This action triggers the loop to exit, and the program takes care of closing the windows and releasing the camera resources.

### Potential Enhancements

This code provides a solid foundation for traffic signal detection applications. It can serve as a starting point for more advanced projects related to traffic management and autonomous vehicles. It's important to note that proper lighting conditions and clear visibility of the traffic signals are crucial for accurate detection and recognition.

Feel free to build upon and improve this code to suit your specific requirements and use cases.
