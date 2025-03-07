# Real-Time Aircraft Speed Calculation System  

This project aims to develop a **real-time application** for calculating and displaying the speed of a **military aircraft** based on sensor data from an **accelerometer** and a **gyroscope**,. The system processes sensor data at fixed intervals and updates the velocity reading on a monitor every second.  

## Key Challenges  
- **Gravity Interference**: The accelerometer captures both motion-related acceleration and gravitational acceleration, which can distort speed calculations.  
- **Angle Compensation**: Aircraft inclination (roll, pitch) affects sensor readings, requiring correction.  
- **Data Processing**: Numerical integration and vector composition are used to determine velocity across all three movement axes.  

## Solution Approach  
- **Sensor Fusion**: Uses **complementary filtering** to separate gravitational acceleration from movement acceleration.  
- **Real-Time Processing**: Implemented on an **Arduino Mega 2560** using **FreeRTOS** for multitasking and resource management.  
- **Synchronization Mechanisms**:  
  - **Mutexes**, **timers**, and **semaphores** from FreeRTOS ensure data integrity in concurrent environments.  
  - Multiple tasks handle different operations, such as:  
    - `CitireAccelerometru` (Accelerometer Reading)  
    - `CitireGiroscop` (Gyroscope Reading)  
    - `IntegrareAccelerometru` (Accelerometer Integration)  
    - `IntegrareGiroscop` (Gyroscope Integration)  
    - `CalculareViteza` (Speed Calculation)  
    - `AfisareViteza` (Speed Display)  

## Technologies Used  
- **Arduino Mega 2560** for hardware implementation
- **MPU6050** accelerometer and gyroscope sensor.
- **FreeRTOS** for real-time task management  
- **Numerical integration** and **sensor fusion algorithms** for accurate velocity computation  

This project demonstrates efficient **real-time data processing** and synchronization techniques for avionics applications.
