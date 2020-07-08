---
layout: default
title: Demo Cases
nav_order: 4
has_children: true
permalink: docs/Demo Cases
has_toc: false
---

# Demo cases

NTNU's research vessel - [Gunnerus](https://www.ntnu.edu/gunnerus/gunnerus), is used as the basis for the development of the digital ship twin, Fig. 1. 
Several component models (FMUs) representing the Gunnerus hull and main propulsion system developed by NTNU and Sintef were recycled from the previous research project [ViProMa](https://viproma.no/). 
In 2019, the Gunnerus ship was elongated by 5 meters and a new crane was installed. The hull model was updated based on estimations using Sintef's software VeSim. Controllers, a tunnel thruster (for DP) and a crane model were developed and added to the Gunnerus component model library [gunnerus-fmus-bin](https://github.com/gunnerus-case/gunnerus-fmus-bin). 


The demo cases use NTNU's research vessel - Gunnerus, Fig. 1.

**Specifications of the Gunnerus vessel:**

{% include figure.html 
    img="/assets/images/gunnerus.png" 
    num="1" 
    caption="Gunnerus in subsea installation" 
%}


The following demo simulators are presented:
- [Dynamic Positioning](./Dynamic Positioning)
- [Trajectory Following](./Trajectory Following)
- [Docking](./Docking)
- [Crane Operation](./Crane Operation)

