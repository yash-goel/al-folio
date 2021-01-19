---
layout: page
title: learning MPC controller
description: Using deep network to learn control for tracking
img: /assets/img/mpc_intro.gif
importance: 2
---

*Robotics Research Centre, IIIT Hyderabad*

Investigate the use of deep networks for learning control to imitate the performance of MPC controller. The proposed network takes in the future desired states and the current state of the quadrotorto generate high level control commands of yaw rate, pitch, roll and thrust to do positional tracking. All the simulations were done in `ROS` using [RotorS](https://github.com/ethz-asl/rotors_simulator) simulator.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/deepmpc.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    The whole pipeline for imitating control.
</div>

### Data Collection

The expert control commands are generated using [mav_control_rw](https://github.com/ethz-asl/mav_control_rw) package. These control commands serve as the ground truth for the imitation learning scheme while the ground truth pose as the input.

<div class="row">
    <div class="col-sm mt-1 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/mpc_data.gif' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Various trajectories generated on ROS using RotorS simulator. The blue trajectories are the desired trajectories whereas the red ones represent the ground truth trajectories generated from the MPC controller.
</div>

### Network

Various network structures (MLP and recurrent networks) were tested for comparing the results. Though the final output remain the same producing yaw rate, roll, pitch and thrust.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/deep_net.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Initial MLP network used for learning control
</div>

### Results
Generated high-level commands from the network are sent to the low-level PID control for controlling the drone.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/deep_res.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
     Performance of the proposed deep network fortracking on unseen <em>sine</em> curve
</div>