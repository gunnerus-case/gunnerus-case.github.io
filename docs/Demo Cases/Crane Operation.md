---
layout: default
title: Crane Operation
parent: Demo Cases
nav_order: 4
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

This demo case of crane operation uses the following models of the Gunnerus twin, Tab.2. These includes all models in the DP case as crane operations can only be safely carried out when the ship is stable.
The crane operation case has also compensation controllers for the crane and winch, although compensation systems are not available in the real systems. Use of the compensation controllers are optional. The crane controller can compensate the crane tip motion in 3DOF within its reach limits. The winch controller compensates the vertical motion of the load. 
Interfaces and connections of these FMUs can be found in the configuration file [SSP definitions](https://github.com/gunnerus-case/sspgen-definitions). 

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
 | Waypoint Provider| WaypointProvider3DOF | Reference position of the ship  |
 | Observer| NonlinearPassiveObserver| Feedback position of the ship |
 | Crane| PalfingerCrane  |The palfinger crane model includes winch, wire and load |
 | Winch Controller| AHCController  |Load vertical motion compensation using the winch|
 | Crane Controller|TipController | Crane tip controller for compensation using the crane |
 | Crane Tip Setpoint|TipSetPoint | Crane tip reference speed for compensation using the crane |
 
 
 {% include figure.html 
     img="/assets/images/palfinger2.png" 
     num="2" 
     caption="Palfinger crane in subsea installation" 
 %}
 
Palfinger crane operation in digital twin ship simulator, visualized by Offshore Simulation Center [(OSC)](https://osc.no/).
<video src="/assets/videos/OSPv03.mp4" width="640" height="400" controls preload></video>
 
## References
- Yingguang Chu, Guoyuan Li, Lars Ivar Hatledal, and Houxiang Zhang: Coupling of Dynamic Reaction Forces of a Heavy Load Crane and Ship Motion Responses in Waves, journal of Ships and Offshore Structures, accepted, 2020.
- Yingguang Chu, Guoyuan Li and Houxiang Zhang: Incorporation of ship motion prediction into active heave compensation for offshore crane operation, in 15th IEEE Conference on Industrial Electronics and Applications (ICIEA), accepted, 2020.
- Yingguang Chu, Birger Skogeng Pedersen, and Houxiang Zhang. "Virtual prototyping for maritime winch design and operations based on functional mock-up interface co-simulation." Ships and Offshore Structures 14, no. sup1 (2019): 261-269.
- Yingguang Chu, Lars Ivar Hatledal, Houxiang Zhang, Vilmar Æsøy, and Sören Ehlers. "Virtual prototyping for maritime crane design and operations." Journal of marine science and technology 23, no. 4 (2018): 754-766.