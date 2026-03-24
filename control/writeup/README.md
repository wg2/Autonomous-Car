# Project 3: Control [![tests](../../../badges/submit-proj3/pipeline.svg)](../../../pipelines/submit-proj3/latest)

Q1:
Increasing the _Kp_ gain makes the controller more responsive to deviations in the path, such as turns. However, having too high ove a _Kp_ can cause it to overshoot and have oscillations. On the other hand, having too low of a _Kp_ makes it less sensitive to turning, making it overshoot less but have a slower response to the path.

Q2:
To tune the PD controller, we first increased the _Kp_ in order to make the car respond to turns quicker. However, it started overcorrecting during sharp turns. To counteract this, we increased the _Kd_ by a small amount. This led us to our final values of 2.5 and 1 for _Kp_ and _Kd_ respectively. As seen in the plots below, these values are able to follow turns closely and accurately. 
![pid circle](control/writeup/pid_circle.png)\
![pid left](control/writeup/pid_left.png)\
![pid wave](control/writeup/pid_wave.png)

Q3: To tune the lookahead for Pure Pursuit, we started with a small lookahead value and noticed that the vehicle was oscillating along the circular path. We then incremented the lookahead value to 0.5 and noticed that the robot then follows the path on rviz but stays inside the path drawn in rviz. We slowly dropped the lookahead value to 0.4 and got a good balance between oscillations and staying along the path.
![pp wave](control/writeup/pp_wave.png)

Q4: We noticed that when the lookahead is too small, the robot will oscillate more when following the circular path. If the lookahead distance is too large, this will smooth out the oscillations when the robot is moving along the path, but the robot will stay inside the path drawn in rviz.\
PP Small:\
![pp small wave](control/writeup/pp_small.png)\
PP Large:\
![pp large wave](control/writeup/pp_large.png)


Q5: We noticed that the Pure Pursuit controller would make our robot track the path more smoothly, but the robot would cut inwards inside the circular path. The robot would be more prone to oscillations for smaller radii.


Q6: To tune the lookahead for MPC, we noticed that the initial values were far too small. We increased both _K_ and _T_ significantly however, this resulted in the car not going near obstacles. To fix this, we lowered the _T_, reaching our final values of 100 and 30 for _K_ and _T_ respectively. These values predict enough turning angles and look far enough to follow the path without being afraid to go near obstacles.\
Circle path:\
![mpc circle](control/writeup/mpc_circle.png)\
Wave path:\
![mpc wave](control/writeup/mpc_wave.png)\
The saw path has sudden, sharp turns that can be difficult to predict for. The MPC controller handles these turns better than the other controllers but still needs to correct.  
![mpc saw](control/writeup/mpc_saw.png)

Q7:\
Slalom path for 1-1:\
![mpc slalom 1-1](control/writeup/mpc_slalom_1.png)

Slalom path for 1-2:\
![mpc slalom 1-2](control/writeup/mpc_slalom_2.png)

Q8: We can add velocity to track speed, which would give us helpful evidence that helps determine whether the robot can get to its destination faster without issue. Power consumption can be used to penalize a path when the energy cost is too high (e.g sharp turns vs. gradual path).


Q9: We observed that the MPC controller was the most robust controller at slower speeds. It is able to avoid obstacles such as walls, and generally follows the path smoothly. It is also able to predict upcoming curves and adjust for them. At higher speeds, the PID controller performed better as it was smoother and more responsive.


Q10:\
PID:\
![pid circle rviz](control/writeup/pid_circle_rviz.png)\
PP:\
![pp circle rviz](control/writeup/pp_circle_rviz.png)\
MPC:\
![mpc circle rviz](control/writeup/mpc_circle_rviz.png)
