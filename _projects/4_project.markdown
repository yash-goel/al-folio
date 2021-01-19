---
layout: page
title: Hydrogen Fuel Cell Vehicle
description: modelling, simulation and control of subsystems
img: /assets/img/tata_whole.png
importance: 5
---

*Tata Motors Research Centre Bangalore - Big thanks to <b>Mr. Anand Vasappanavara</b>*

The work involved modelling systems, simulating and designing controller
for various sub-systems of a fuel cell vehicle. This work gave me an overview of the hydrogen fuel cell vehicle and its working in depth. A detailed analysis of all the work done is given [here](https://drive.google.com/file/d/1XRUzs_zOVsMAxC2frRLH15_kd77dZKQP/view).

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/tata_whole.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    General hydrogen fuel cell vehicle powertrain
</div>

### Performance Simulation
This involved primarily performance simulation of the vehicle to set the parameters and formulate if the vehicle is meeting all the design criteria. Also, the fuel economy of the vehicle was simulated on a drive cycle provided by ARAI to see how much the vehicle will run once all the tanks are filled.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/tata_perform_1.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Performance simulation of vehicle
</div>

### Thermal Simulation
Thermal simulation for the cell stack was done to predict the temperature of the cell stack and controlling it via `PI` controller. The
PI controller controlled the fan speed to change the rate of convection ultimately causing the change in temperature of the fuel cell. A part of
hydrogen refuelling station was also simulated.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/tata_thermal_1.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    PI control of fuel cell stack temperature
</div>

### Battery Design
To solve the problem of SOC determination, a state space model of the battery was created to calculate the SOC and it incorporated the Extended Kalman Filter for the observer design.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/tata_bat_1.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Part of battery model in simulink
</div>
