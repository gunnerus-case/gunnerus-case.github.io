---
layout: default
title: Open Simulation Platform
nav_order: 
permalink: docs/osp
has_toc: false
parent: Co-simulation Platforms
---

##  Open Simulation Platform
The Open Simulation Platform [(OSP)](https://opensimulationplatform.com/) project aims to create a maritime industry ecosystem for co-simulation of “black-box” simulation models and “plug and play” configuration of systems.
OSP relies on the FMI standard and the new OSP interface specification [(OSP-IS)](https://opensimulationplatform.com/specification/) for the simulation models interfaces. This facilitates the effective building of digital twins, which in turn can be used to solve challenges with designing, building, integrating, commissioning and operating complex, integrated systems.
With common tools, standards and specifications OSP seeks to foster co-simulation collaboration in the industry.

There is currently support for FMI 2.0 (including FMI 2.0.1) and FMI 1.0. FMI 3.0 will be supported when this standard becomes operational. The structure of the co-simulated system can be defined using the SSp standard or the new OSP System Structure format: OSP-IS.

The main benefit introduced with OSP-IS is the possibility to define FMU interconnections at a higher level, i.e. variable group connections rather than scalar connections. Additionally, it enables automatic unit conversions and provides the a priori validation of the system configuration utilizing an ontology that models the connection types.

### OSP-IS
The OSP system structure configuration format is based on the OSP Interface Specification OSP-IS and is used to configure the simulation system structure, including connections between FMUs and setting of initial values for input and parameter variables. The configuration format is XML according to schema [OspSystemStructure.xsd] (https://www.opensimulationplatform.com/xsd/OspSystemStructure-0.1.xsd).
The OSP-IS is an addition to the FMI 2.0 standard for co-simulation which provides a method for adding semantic meaning to model interface variables. OSP-IS enables faster construction of co-simulation simulators by simplifying the model connection process, and validation of semantically correct simulations.