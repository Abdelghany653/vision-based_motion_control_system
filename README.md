# Motion Control-Based on Vision

## Abstract
This project presents a computer vision-based motion control system that estimates the angular position of a rotating disk using a camera instead of conventional rotary encoders. Image processing algorithms are employed to detect a reference marker on the disk and calculate its angular displacement in real time. The measured angle is displayed through a graphical user interface developed using MATLAB App Designer, allowing users to monitor the system, visualize the disk orientation, and command the disk to move to a desired angular position.

The project demonstrates the integration of computer vision, real-time image processing, motion control, graphical user interface (GUI) development, and embedded communication within a single application.


## MATLAB Application
  <p align="center">
    <img src="docs/app_design" alt="Application Design" width="40%">
  </p>
A custom MATLAB App Designer application was developed to monitor and control the vision-based positioning system. The interface integrates computer vision, serial communication, PI control, and real-time data visualization, allowing users to set the desired angle, monitor the live camera feed, tune controller parameters, and evaluate the system's performance through live measurements and response plots.

#### Application Components
##### 1. Control Panel
The control panel provides the main interaction with the system.

It includes:
- Serial Port Selection to choose the communication port.
- Connect Button to establish serial communication with the microcontroller.
- Desired Angle Input for specifying the target angular position.
- Start Button to begin the control process.
- Stop Button to terminate the control loop safely.
- Save Data Button to store experimental data for later analysis.
- HSV Button to open the HSV calibration tool used for color segmentation.

##### 2. Live Annotated Camera View
The live camera window continuously captures images of the rotating disk and processes them in real time.
Using color-based image processing, the application detects predefined colored markers attached to the rotating disk and calculates its current angular position. The detected markers, reference vectors, and measured angle are overlaid on the live video, allowing the user to visually verify the tracking accuracy.

##### 3. Live Measurements
The live measurement panel displays the current operating parameters of the control system, including:
- Current measured angle
- Position error
- PWM output
- Motor rotation direction
- System status
- Sampling time
These values are updated continuously throughout system operation.

##### 4. PI Controller Parameters
The application allows online adjustment of the PI controller gains without modifying the program.
The user can configure:
- Proportional Gain (Kp) – Determines the controller's response to the current position error.
- Integral Gain (Ki) – Eliminates steady-state error by accumulating past errors.
- Derivative Gain (Kd) – Reserved for PID control and set to zero in the current implementation.
- Tolerance – Defines the acceptable angular error for considering the desired position reached.
This functionality simplifies controller tuning and enables rapid performance optimization.

##### 5. HSV Calibration Panel
The HSV calibration section stores the lower and upper HSV thresholds used for color detection.
Separate HSV ranges are defined for each colored marker, allowing reliable object detection under different lighting conditions. These values can be adjusted to improve tracking accuracy.

##### 6. Desired vs Actual Position Plot
The lower panel displays the system response in real time.
The graph compares:
- Desired Position (red dashed line)
- Actual Measured Position (blue solid line)
This visualization allows the user to evaluate important control characteristics such as:
- Rise time
- Tracking accuracy
- Steady-state error
- Response smoothness
- Position convergence







## Demonstration Video

<p align="center">
  <img src="docs/line_following_robot.gif" alt="Line Following Robot Demo" width="15%">
</p>





