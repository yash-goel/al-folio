---
layout: page
title: Bebop Navigation
description: collision cone based optimization for dynamic obstacles
img: /assets/img/bebop_intro.gif
# redirect: https://unsplash.com
importance: 1
---

*Robotics Research Centre, IIIT Hyderabad*


This project comprised of implementing dynamic obstacle avoidance on `Bebop` drone. The goal reaching was an optimization scheme with obstacle avoidance done using collision cone constraints. This was done for *holonomic* and *non-holonomic* setting in two different ways. 


### Holonomic Setting
For this setting a new variant of velocity obstacle was implemented - **Inverse Velocity Obstacle** where we construct the collision cone in the ego-centric frame which showed improvement for real time implementation. We eliminate the need to know the robot position and velocity for obstacle avoidance - thus eliminating the associated noise. It was shown to work for multi-agent setting as well. This [work](https://arxiv.org/pdf/1905.01438.pdf) was published at `AIR 2019`.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/ivo_gif.gif' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Real world implementation of <em>IVO</em> on bebop drone. 
</div>

### Non-Holonomic Setting
In this the drone was constricted to move like a `fixed-wing` aircraft. To implement this, the optimised path was decomposed into `dubin paths`. This scheme was tested in real life. All the detailed video results are available [here](https://youtu.be/0fk0RPp73UE)

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/dubins_vid.gif' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Simulation for multiple obstacle avoidance in <em>non-holonomic</em> setting.
</div>