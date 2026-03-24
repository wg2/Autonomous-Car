# Final Project

Q1:
We are using MPC because it is the only controller that can avoid mapped barriers in the environment as well as unmapped obstacles. PID and PP simply try to follow the calculated path and do not avoid things that are in the way.

Q2: 
We used 3000 vertices with a connection radius of 3 and curvature of 1. We found that these values were able to find the optimal route without taking too much time calculating. This is mainly due to the low connection radius in combination with high vertex count. We found that decreasing the vertices lead to a unoptimal route even if the connection radius was increased. The kept the default curvature because it is pretty accurate to the maximum turning radius of the car.

Q3:
While our code worked with multiple waypoints, the parameters we had did not. Thus, the biggest challenge to make multiple waypoints work was tuning the MPC and costmap. We found that the MPC collision weight was far too high and made the car very afraid of getting near objects and walls. By reducing this value, the MPC was able to drive more confidently and move smoother toward the goal. We also adjusted many of the costmap parameters to detect obstacles earlier and with more accuracy. The biggest change we made to the costmap was to disable the static layer and rely fully on the LIDAR scan since the lab layout does not match the static map in many places.

See no_obstacles.bag for recording.