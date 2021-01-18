---
layout: default
title: Trajectory Following
parent: Demo Cases
nav_order: 2
---
# Trajectory Following 
This case demostrates the trajectory following of the Gunnerus ship.

**Table 1:** *FMUs*

 |Model| FMU| Description |
 | --- | --- | ---| 
 | Hull | VesselFmu |6DOF hull model including the environment model |
 | Main Thruster| PMAzimuth | Two Azimuth thrusters as the main propulsion|
 | Thruster Drive| ThrusterDrive | Thruster drive calculates the rmp of the thruster given the desired thrust command (propulsion force) [1] |
 | Power Plant| PowerPlant | Provides power to the thruster drive [2]|
 | Waypoint Provider| WaypointProvider2DOF | Reference position of the ship  |
 | Trajectory controller | TrajectoryController.fmu | Calculates the propulsion force and and azimuth angle(s) based on the waypoints | 
 

[WebDemo](https://gunnerus-case.github.io/gunnerus-web-demo/)


### References
[1] S. Skjong, M. Rindarøy, L. T. Kyllingstad, V. Æsøy, and E. Pedersen, “Virtual prototyping of maritime systems and operations: applications of distributed co-simulations,” J. Mar. Sci. Technol., pp. 1–19, 2017.  
[2] S. Skjong and E. Pedersen, “A real-time simulator framework for marine power plants with weak power grids,” Mechatronics, vol. 47, pp. 24–36, Nov. 2017.  
