# Project 1: Introduction [![tests](../../../badges/submit-proj1/pipeline.svg)](../../../pipelines/submit-proj1/latest)

Q1: 
A node is a function in ROS that completes a specific task, such as different functions that control the car. These send messages through topics which are the channels that hold what messages are going in and out of each node.
A publisher is a type of node that is more dedicated to sending messages in a certain topic. They focus on "publishing" messages to a certain topic.
A subscriber is another type of node that "subscribes" to different topics to receive messages from. They receive messages once publishers send messages to the topics the subscriber node has chosen.

Q2: The purpose of a launch file is to allow launching the robot to be easily repeatable and understandable regardless of the amount of nodes within. Very similar use to a build file when compiling the code of large multifile projects. Can configure global parameters within the launch file so there is less need to edit code when testing different parameters. Additionally, allows for consistent startup of the system and switching between simulation and hardware easily.

Q3: RViz Screenshot of CSE2\
![CSE2 Rviz](introduction/writeup/cse2_rviz.png)

Q4: Euclidean Normalization Runtime Comparison\
![Runtime Comparison](introduction/writeup/runtime_comparison.png)

Q5: Figure 8 Location and Distance\
![Figure 8 Location](introduction/writeup/figure_8_locations.png)
![Figure 8 Distance](introduction/writeup/figure_8_distance.png)

Q6: Tight Figure 8 Location and Distance\
![Tight Figure 8 Location](introduction/writeup/tight_figure_8_locations.png)
![Tight Figure 8 Distance](introduction/writeup/tight_figure_8_distance.png)


