---
layout: default
title: Co-simulation Platforms
nav_order: 2
permalink: docs/Co-simulation Platforms
has_toc: false
has_children: true
---

A digital twin for cyber-physcal systems as complex as a ship comprises for components in several different domains. As much significant as the evolvement of modeling and simulation technologies in the product development lifecycle, no one simulation tool is suitable for all purposes.
Co-simulation refers to an enabling technique, where different sub-systems making up a global
simulation are being modeled and run in a distributed fashion. Each sub-system is a simulator and is broadly defined
as a black box capable of exhibiting behavior, consuming
inputs, and producing outputs. A crucial point is that it allows users to simulate models exported from different tools together.
Compared to more traditional monolithic simulations, co-simulation encourages
re-usability, model sharing and fusion of simulation domains.
Figure 1 illustrates a possible co-simulation scenario for a vessel, which requires models from several different domains.
Co-simulation is absolutely imperative for this scenario to
succeed, not only because models from different domains
need to be coupled, but also because the models may originate
from different, perhaps competing companies that would not
be willing to share their models in any other form than as a
black-box model.
{% include figure.html
    img="/assets/images/cosim-cyberphysical.png"
    num="1"
    caption="Simulation of a complex cyber-physical system in the maritime domain. The complete vessel model is
             constituted by the individual sub-modules connected through FMI for Co-simulation."
%}

##  FMI Co-simulation
The Functional Mock-up Interface standard [(FMI)](https://fmi-standard.org/) is a tool independent standard that
supports both model exchange (ME) and co-simulation (CS)
of dynamic models. A model implementing the FMI standard
is known as a Functional Mock-up Unit (FMU). Many tools
support FMUs, and it has become the de-facto standard for
ME and CS.
The main goal of the Functional Mock-up Interface (FMI) standard is to allow the sharing
of simulation models across tools. To accomplish this, FMI relies on a combination of XML-files and
compiled C-code packaged in a zip archive. This archive is called a Functional Mock-up Unit (FMU).

### SSP
As an extension of the FMI standard, the System Structure and Parameterization [(SSP)](https://ssp-standard.org/) standard aims to facilitate the need to design, simulate and execute a network of components (e.g., FMUs)
It is a tool independent standard to define complete systems consisting of one or more FMUs including its parameterization that can be transferred between simulation tools.
The main use of this standard are:

- Define a standardized way to store and apply parameters to these components.
- Define a standardized format for the connection structure for a network of components.

##  Open Simulation Platform
The Open Simulation Platform [(OSP)](https://opensimulationplatform.com/) project aims to create a maritime industry ecosystem for co-simulation of “black-box” simulation models and “plug and play” configuration of systems.
OSP relies on the FMI standard and the new OSP interface specification [(OSP-IS)](https://opensimulationplatform.com/specification/) for the simulation models interfaces. This facilitates the effective building of digital twins, which in turn can be used to solve challenges with designing, building, integrating, commissioning and operating complex, integrated systems.
With common tools, standards and specifications OSP seeks to foster co-simulation collaboration in the industry.

There is currently support for FMI 2.0 (including FMI 2.0.1) and FMI 1.0. FMI 3.0 will be supported when this standard becomes operational. The structure of the co-simulated system can be defined using the SSp standard or the new OSP System Structure format: OSP-IS.

The main benefit introduced with OSP-IS is the possibility to define FMU interconnections at a higher level, i.e. variable group connections rather than scalar connections. Additionally, it enables automatic unit conversions and provides the a priori validation of the system configuration utilizing an ontology that models the connection types.

### OSP-IS
The OSP system structure configuration format is based on the OSP Interface Specification OSP-IS and is used to configure the simulation system structure, including connections between FMUs and setting of initial values for input and parameter variables. The configuration format is XML according to schema [OspSystemStructure.xsd] (https://www.opensimulationplatform.com/xsd/OspSystemStructure-0.1.xsd).
The OSP-IS is an addition to the FMI 2.0 standard for co-simulation which provides a method for adding semantic meaning to model interface variables. OSP-IS enables faster construction of co-simulation simulators by simplifying the model connection process, and validation of semantically correct simulations.

##  Vico

Vico is a novel open-source co-simulation framework based on the [Entity-Component-System](https://en.wikipedia.org/wiki/Entity_component_system) software architecture.
Vico allows co-simulation between not only FMI slaves, but between physics engines, FMI masters and generic systems. Furthermore, 3D visulisation and 2D plotting is integrated into the framework. And of course, simulation data can be exported as CSV files. Some of the highlights for this framework are as follows:

* Support for FMI 1.0 & 2.0 for co-simulation.
* Support for SSP 1.0.
* Optionally distrubuted execution of FMUs though FMU-proxy.
* Integrated (implementation independent) 3D visulisation.
* Integrated 2D plotting.
* Integrated (implementation independent) physics.
* Command line interface (CLI) with scripting support.
* Cross-platform (Windows and Linux)
* CSV export of simulation results. 
* MIT license.

Vico can be used both as a Java library or as an application through the available CLI. The CLI can be used to run single FMUs, system of FMUs described using SSP and generic Vico simulations defined by Kotlin scripting.   
Vico is written in Kotlin, ensuring 100% compatiability with the Java platform. 

### Distributed Co-simulation

 Distributed co-simulation refers to the idea that a
 co-simulation can be distributed not only logically, but physically across a network. There are several reasons to perform
 a co-simulation with one or more remote simulators. For
 instance, a simulator may impose one or more requirements
 onto the simulation environment, such as a platform, software, or license requirement, that is for some reason impossible to meet. In such a case, the simulator can run in a
 compatible environment and accessed remotely. Also, if the
 overall simulation is suited for parallelization, it may be more
 efficient to balance the workload over several computation
 nodes. Another use-case is to prevent the execution of malicious code on a sensitive system by accessing it from a sandboxed environment. Physically distributed co-simulation is
 also an excellent way of protecting intellectual property,
 as clients would not have direct access to the simulation
 model. It’s also worth noting that distributed co-simulations
 are vital for enabling digital twin technology, which requires
 the integration of industrial internet of things devices.

 [(More)](./fmuproxy)
