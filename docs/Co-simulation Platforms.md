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

##  FMI based Co-simulation
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

In order to ease the creation of SSP archives, the NTNU developed tool [sspgen](https://github.com/NTNU-IHB/SSP-DSL) may be utilized.

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

 Distributed Co-simulation can be achived using the language and platform independent framework [FMU-proxy](./fmuproxy) developed by NTNU.
