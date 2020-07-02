---
layout: default
title: Crane Operation
parent: Demo Cases
---

# Crane Operation
The Gunnerus ship is fitted with a foldable knuckle boom crane for diverse lifting and loading tasks, Fig.1.
The Palfinger marine crane (PK 65002 M) has a compact design suitable for small vessels with limited space. Specifications of the model type is shown in Tab. 1.

{% include figure.html 
    img="/assets/images/palfinger.JPG" 
    num="1" 
    caption="Palfinger marine foldable knuckle boom crane" 
%}


**Table 1:** *PK 65002 M specifications*

|Crane Type|Outreach (m)|Lifting Capacity (kg)|Lifting Moment (kNm)|Total Moment (kNm)|Pedestal Outer Diameter (mm)|Slewing Angle (°)|Operating Pressure (bar)|Dead Weight (kg)|
| :---: | :---: | :---:| :---: |:---: |:---: | :---: | :---: | :---:|
|PK 65002 M|4-20.3|15100-2100|600-415.9|684.3|834|endless|300|4220-5960|

The demo simulation case of crane operation uses the following models of the Gunnerus twin, Tab.2. These includes all models in the DP case as crane operations can only be carried out when the ship is stable.
The crane operation case has also compensation controllers for the crane and winch. These compensation controllers are optional. The crane controller can compensate the crane tip motion in 3DOF within its reach limits. The winch controller compensates the vertical motion of the load. 

**Table 2:** *FMUs*

 |Model| FMU| Description |
 | --- | --- | ---| 
 | Hull | VesselFmu |6DOF hull model including the environment model |
 | Main Thruster| PMAzimuth | Two Azimuth thrusters as the main propulsion|
 | Tunnel Thruster| TunnelThruster | One tunnel thruster required for DP control |
 | Thruster Drive| ThrusterDrive | Thruster drive calculates the rmp of the thruster given the desired thrust command (propulsion force) |
 | Power Plant| PowerPlant | Provides power to the thruster drive|
 | DP Controller| DPController |DP control for the north-east-yaw motion of the ship |
 | Allocator| ControlAllocatorGIFixedAngles | Thrust allocation for DP control|
 | Observer| NonlinearPassiveObserver| Feedback position of the ship |
 | Waypoint Provider| WaypointProvider3DOF | Reference position of the ship  |
 | Crane| PalfingerCrane  |The palfinger crane model includes also the winch, wire and load |
 | Winch Controller| AHCController  |Load vertical motion compensation using the winch|
 | Crane Controller|TipController | Crane tip controller for compensation using the crane |
 | Crane Tip Setpoint|TipSetPoint | Crane tip reference speed for compensation using the crane |
 
 
 {% include figure.html 
     img="/assets/images/palfinger2.png" 
     num="2" 
     caption="Palfinger crane in subsea installation" 
 %}
 
 {% include figure.html 
     img="/assets/images/palfinger3.png" 
     num="3" 
     caption="Palfinger crane operation in digital twin simulator" 
 %}