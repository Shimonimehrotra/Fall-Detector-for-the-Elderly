# Fall-Detector-for-the-Elderly

Commonly, fall detection systems use a gyroscope and an accelerometer. A gyroscope is used to determine an orientation and an accelerometer provides the information about the angular parameter as three-axis data. But we also need to decide a threshold so that the system can differentiate between a fall and normal activity. For this purpose of Fall Detection, a 3D-axis accelerometer and Gyroscope (MPU6050) is used with Arduino Uno device wearable is used, which is responsible for collecting data from movements of elderly people in real-time.


## Algorithm

We use the threshold-based detection system and check whether a parameter is above a certain threshold value within a time interval. In a fall situation, there is a large change in acceleration within a split second and then after the fall, the person lies still for some time, showing no change in orientation. Knowing these details allows us to create the algorithm.

First, we will collect data from the accelerometer and then calculate the acceleration magnitude. Acceleration magnitude tells us about how quickly velocity changes while acceleration tells us the rate of change in velocity.

After calculating the acceleration magnitude, we need to know if its value breaks the lower threshold. The lower threshold is the minimum threshold in the range decided by us and the value gradually increases up to the high threshold. Then we need to check that it breaks the high threshold in some milliseconds for example 500ms.

If all of these are detected as true conditions, then we check whether there is a change in orientation within 500ms and usually, it's true if the above conditions are true. After that, we check to see if orientation remains the same for some time. If yes, then there was a fall. There is a loop, meaning that if a condition is false at any stage, the process goes back to start and re-executes.\

## Circuit

The circuit is built around an Arduino UNO and an MPU6050 accelerometer and gyroscope breakout module. For collecting data, we rely on the MPU6050 module to give analog input to the Arduino UNO. The MPU6050 module provides six values as output, three values of an accelerometer, and three values of a gyroscope. It is a sensor-based on MEMS (microelectro mechanical systems) technology and uses I2C protocol for communication. Sensors like this are widely used in smartphones, robotics, 3D modeling, UAVs, and more.

The MPU6050 consists of a three-axis gyroscope, a three-axis accelerometer, a digital motion processor, and an on-chip temperature sensor. We are using A4 and A5 pins of the Arduino UNO for data reception.

![Picture1](https://user-images.githubusercontent.com/58876793/125948052-7d789a7c-dabb-4681-991c-794ed0356c1d.jpg)


