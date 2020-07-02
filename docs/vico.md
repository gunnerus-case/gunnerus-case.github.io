---
layout: default
title: Vico
nav_order: 
permalink: docs/vico
has_toc: false
parent: Co-simulation Platforms
---

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