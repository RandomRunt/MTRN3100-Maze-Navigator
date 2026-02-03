# MTRN3100-Maze-Navigator

Designed and built an autonomous maze navigating robot using Solidworks, Fusion 360, 3D printing for the robot chassis and C++ code on Arduino Nano for preset and autonomous navigation of a maze.

Picture of the robot:
![Maze Nav Bot](https://github.com/RandomRunt/MTRN3100-Maze-Navigator/blob/main/MazeNavBot.jpg)

Picture of the maze:
![Perspex Maze](https://github.com/RandomRunt/MTRN3100-Maze-Navigator/blob/main/Perspex%20Maze.jpg)


Problems Experienced

Issue 1: Motors would whine trying to reach a desired distance and never reach it.\
Solution 1: Calibrate a motor deadzone that ensures the motor stops when desired distance is reached

Issue 2: MPU6050_light sensor library was dependant on shortest possible loop time to produce accurate accelerometer readings.\
Solution 2.1: Round Robin approach for lidar sensor reading retireval to reduce loop time. This is due to lidar readings taking a disproportionately long time to retrieve a lidar reading.\
Solution 2.2: Always and only retrieve the accelerometer reading once per loop to keep loop times consistent.

Issue 3: Small, but sudden protrusion in perspex maze walls due to aluminium extrusions.\
Solution 3: During navigation, reduce the impact of sudden changes in left and right wall distance on the PID controlled navigation.

Issue 4: Shiny perspex maze walls caused distorted lidar readings.\
Solution: Reduce the robot speed and filter wall readings.
