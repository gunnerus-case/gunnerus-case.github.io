---
layout: default
title: FMU proxy
nav_order: 
permalink: docs/fmuproxy
has_toc: false
parent: Co-simulation Platforms
---

# FMU-proxy

[FMU-proxy](https://github.com/NTNU-IHB/FMU-proxy) is a completely standalone project that provides the
infrastructure required to invoke FMI compatible models,
such as FMUs, remotely using RPCs. Multiple RPC systems
over several network protocols are supported. Time stepping,
variable routing, plotting, and tasks typically performed by a
master tool are left implemented by the integrating tool. This
creates a lightweight framework that is easy to use and is reusable.
Rather than having several tools implementing their own,
perhaps non-modular or internal, distribution mechanism,
we hope that the solution offered here can be considered as
an alternative or drop-in replacement for existing solutions.
However, this work can only be integrated into simulation
masters with a centralized design. Data must flow through
the master, and not directly between slaves.