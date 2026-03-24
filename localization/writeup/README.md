# Project 2: Localization [![tests](../../../badges/submit-proj2/pipeline.svg)](../../../pipelines/submit-proj2/latest)

Q1: 
There are more particles within a 10cm radius of the noise-free model prediction because in Figure 2, the car has barely moved, meaning there is not much variation since the time delta is small. Meanwhile in Figure 3, the car has moved a more significant amount, meaning there is much more variation in our estimates, making the paraticles much more spread out.

Q2:
The initial particles had far too much variation and appeared to be going everywhere as they turned left. So, I reduced the standard deviation (std) of the action noise, resulting in mm1.png.\
![mm1 plot](localization/writeup/mm1.png)\
mm1.png (vel_std: 0.01, delta_std:  0.1, x_std: 0.05, y_std: 0.05, theta_std: 0.05)

Then, it looked like the particles had the correct banana shape but there was deviation in all directions are the noise free particle. Thus, I reduced the x and y model noise to get closer results to noise free, resulting in mm2.png.\
![mm2 plot](localization/writeup/mm2.png)\
mm2.png (vel_std: 0.01, delta_std:  0.1, x_std: 0.01, y_std: 0.01, theta_std: 0.05)

Finally, these particles looked pretty close to the tuned parameters but there was still more deviation in the turn angle, so I reduced the model noise theta. This reached the fully tuned parameters in mm3.png.\
![mm3 plot](localization/writeup/mm3.png)\
mm3.png (vel_std: 0.01, delta_std:  0.1, x_std: 0.01, y_std: 0.01, theta_std: 0.02)

Q3: Since the sensor model assumes that the laser beams are conditionally independent, this can cause the Bayesian Filter to be overly confident when multipling all of the smaller probabilities together. This also doesn't account for sensor failures since conditional independence would ignore multiple beam failures. This is mitigated by using every N-th beam instead of all 360 beams, reducing overlap and also overconfidence. The weights are also reduced to reduce overconfidence which in turn flattens the weight distribution. Finally, we exclude potentially invalid readings such as noisy readings and readings from max range where the sensor doesn't detect anything.

Q4:
z_hit: 0.5, z_rand: 0.5, hit_std: 1.0\
The inital values had a short peak at the expected distance. Since z_rand is higher, this means that there is more noise attributed in this model which results in sm1.png.\
![sm1 graph](localization/writeup/sm1.png)

z_hit: 0.7, z_rand: 0.3, hit_std: 1.0\
By lowering z-rand to 0.3, this introduces less noise to our sensor model. We also increase z_hit which raises the peak at the expected distance. This allows us to get results that are closer to being noise free which is shown in sm2.png.\
![sm2 graph](localization/writeup/sm2.png)

z_hit: 0.85, z_rand: 0.15, hit_std: 1.0\
Since we have raised z_hit to 0.85, the peak that we get from expected distance is very high (0.3). This also means that by lowering z_rand, there is even less noise in the system. This results in fully tuned paramters which can be seen in sm3.png.\
![sm3 graph](localization/writeup/sm3.png)

Q5:\
![maze_0 graph](localization/writeup/maze_0.png)

Q6:\
![60 second drive graph](localization/writeup/60_sec_drive.png)

Q7: See localization.bag file.
