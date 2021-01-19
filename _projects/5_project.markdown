---
layout: page
title: RL based navigation
description: bachelor thesis at IIT Roorkee
img: /assets/img/quad_nav_intro.gif
importance: 3
---

*with Akshay Walvekar and Anuj Jain*


The project aimed at navigation of a quadcopter in **AirSIM** where the control policy was learned using *DQN* algorithm with depth image as input to the policy. The quadcopter learned to navigate in an urban environment to reach the destination point. We trained the policy for two cases: **2D** and **3D** action space to compare the performance. A [paper](https://ieeexplore.ieee.org/document/9033244) summarising the work was published at `IEEE AUTEEE`.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/quad_nav_rl.gif' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Quadcopter training to navigate in AirSIM environment
</div>

### Network Architecture

A CNN based network was used as our RL policy where the input to the network was *depth image* of the front view of the quadcopter. For the **2D** action space, there were three final outputs of the network - *straight*, *yaw left* and *yaw right*. While for the **3D** action space, there were six - *straight*, *yaw left*, *yaw right*, *move up*, *move down* and *pass(do nothing)*.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/quad_nav_net.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Network Architecture
</div>

### Rewards

The reward was set up such that the target position reaching for the drone is encouraged. While for collision, a reward of `-100` is given. For our destination a curb limit of *400* was set i.e. if the drone takes more than *400* steps to reach the goal then a reward of `-100` is given. Finally, reaching the goal before *400* steps, gives a reward of `+100`. Reward setting for both **2D** and **3D** cases have been discussed in the paper in depth.

### Results
The quadcopter learned to navigate in **2D** and **3D** action space to reach the final destination position. The trained *DQN* policy was then tested in AirSIM. A detailed analysis of the results and training of the *RL* agent has been discussed in the paper.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/final_avoid.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Obstacle avoidance: (a) The house is in the way of the quadcopter so (b) it slows down and (c) starts initiating the turn to avoid the collision. (d) Finally, the turn is accomplished and (e) the quadcopter starts moving along the house (f) until it reaches the end where it will move back to its original direction.
</div>
