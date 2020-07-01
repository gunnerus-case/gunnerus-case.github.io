---
layout: default
title: Onboard Support
nav_order: 3
permalink: docs/Onboard Support
has_children: true
has_toc: false
---

# Development tools for early warning, prediction, and optimization
The digital twin of autonomous ship is the virtual representation of its physical
counterpart. It possess four fundamental functionalities.
- First, the digital twin can store millions of data points from the physical vessel for different types of
operations. A meaningful usage is model based sensitivity analysis - to model the relevant data and
compute how much the model inputs contribute to its output. Developing such a supporting tool makes
sense, for example, for energy consumption, one can analyze what the main factor is during the operation
and take alternative solutions to save the consumption.
- Second, the digital twin plays the role in modelling and simulation in the virtual world before executing
any onsite operations, for a comprehensive understanding of certain specific operations such as mooring,
dynamic positioning and heavy lifting. This will be helpful for cutting cost and increasing operational
efficiency as well, taking advantage of repeatable simulation towards optimization.
- Third, data based prediction is available in the digital twin. In a broad sense, prediction includes both
internal and external status of the vessel. On the one hand, prediction on the internal status such as
temperature in the engine room provides an early warning ability, which can detect if an asset is failing or
is about to fail. On the other hand, prediction on the external status, especially the ship motion including
position, heading and rolling, is of great importance for ship safety.
- Fourth, ideally, the digital twin provides the feasibility of dynamic autonomy among two extremes, i.e.,
the ship can be remotely operated by human via either the land based communication network or the high
bandwidth satellite communication systems, depending on the availability, quality and price of the
autonomous ship; or the ship can be operated on its own pace using onboard sensor information. In order
to understand how the digital twin performs autonomous shipping, a controller for simple tasks such as
path following that has fewer limits given for the decision making tolerance will be implemented. 

Figure 1 illustrates a possible scheme of the supporting system for maritime operations. 
Note that the data sensitivity analysis module is the basis of the scheme. It takes the ship status, the operational commands and
the environmental data as input and the designated metric, e.g., ship position, as output, to quantify how
much the input contributes to the output. The result can benefit both the optimizing and the prediction phase.
For example, if the ocean current accounts for one of the main factors for maneuvering, this element will be
considered in the path optimizer or the motion predictor as a cost function or an input of the predictive
model. Dynamic optimization refers to the state of the ship and the mission being executed. It considers
constraints and generates optimized references for auto-control; meanwhile it formulates the references as
prior knowledge for prediction of future operation—as far as the auto-control couples with the optimization
module. Similar couplings exist between the prediction module and the auto-control module, as they are in
essence a complete closed-loop system.

As a result, the information from the four modules will be gathered together to establish an onboard
supporting center, forming various tools ranging from risk assessment, maneuvering evaluation, sensor
diagnosis to real-time planning. Note that, the onboard supporting tools can feed back to each module, to
force it update. If a predictive path shows a potential failure of path following by the auto-control due to
environmental condition change, a feedback to the optimization module will enforce it to re-plan. 

{% include figure.html 
    img="/assets/images/onboardsupport.png" 
    num="1" 
    caption="Digital twins for maritime prediction and maintenance" 
%}

## Approximation-based model approach for sensitivity analysis

Sensitivity Analysis (SA) investigates how the variation in the output of a numerical model can be attributed
to variations of its input factors. The SA is subsequently performed to quantify the individual or collective
importance of each input variable on the model outputs. SA is increasingly being used in industrial modelling
for a variety of purposes, including uncertainty assessment, model calibration and diagnostic evaluation,
dominant control analysis and robust decision-making. In general, SA could be implemented in either a local
or a global manner. The difference is that the former analyzes the effect of a single input on the output and
treats the other inputs as deterministic values; whereas the latter examines the sensitivity from the perspective
of the entire range of each input’s variation. Considering the huge amount of unstructured data stored in the
digital twin, it is suggested to run SA on surrogate models like neural networks instead of on the pure data
directly. To this end, we will focus on approximation model based SA and take the following aspects into account:
- Theoretical analysis and comparison between model based and non-model based SA
- The trade-off between local- and global SA (first-order- and higher-order sensitivity index)
- The selection of surrogate models, which refers to the type and the dimension of the model
- Application oriented analysis and modelling, such as SA on ship engine energy consumption and
maneuvering.

## Data-driven adaptive observer for ship component predictive maintenance
Ship component state is one of the most important elements that need to be supervised during maritime
operations. To validate the collected data from the real life physical system, an adaptive observer in the
digital twin is substantial. It provides a calibrated model which can give real time values for double checking
the current situation of the plant. This is crucial for a high availability of the whole plant, as comparing 
side 10/15
Kompetanseprosjekt for næringslivet, mal for prosjektbeskrivelse 09.12.2010
simulated and real values, systematic analysis of the system can be maintained in order to provide a valuable
condition based monitoring system.
Predictive maintenance is a further activity that comprise opportunities for high cost savings by transparent
and efficient management. Taking the propulsion system for example, the predictive maintenance gives the
operator on board an overview of all system relevant measurements, from generators to switchboards,
transformers, converters and all other components. By integrating expertise into the maintenance scheme,
especially the failure experiences of ship components, anomaly detection determining the anomaly
originating from either a true physical component or from a failure of sensor, can be realized. This process
will maximize the useful life span and reduce cost by avoiding early replacement of functional components.
In this work package, we aim to develop a standard process from data collection, model selection to training
and testing, so as to make the observer versatile for various ship component prediction:
- Acquire knowledge necessary for data consistency and reorganization
- Analyze correlation of related measurements for systems on board of the digital twin
- Apply machine learning, and artificial intelligence to develop predictive models
- Test the predictive models on systems of the digital twin.


## Optimization tools for operational efficiency on vessels

The digital twin allows ship operators to optimize the instantaneous and transient control of the ship for
efficiency or performance, make informed decisions regarding performance versus part life, assign loads and
lineups through time, and perform the right maintenance tasks at the ideal time. Refer to onboard operations,
it is demanded to use an online performance model in conjunction with real-time optimization capabilities to
give periodic recommendations for asset operation. However, how to seek ways to optimize within many key
performance indicators (KPIs) and balance things such as revenue against the remaining life of the system or
maintenance costs is challenging. This package aims to design efficiency optimizers to handle many
variables, adhere to constraints that are imposed, and seamlessly account for interconnected aspects of the
problem to be solved that cannot be grasped on the basis of the individual parts alone:
- Investigate possible optimization demands in maritime operation domain
- Determine the physical constraints and rules for maritime operations
- Implement optimizing algorithms and verify them in simulation
- Evaluate the applicable range of each optimizer in different working conditions
- Full scale test on the real vessel after verification in simulation



## Auto-control for certain full autonomy operations

In connection with the prediction and the optimization modules, certain maritime operations can be achieved
in an autonomous manner, such as operations for trajectory tracking, adaptive docking and anti-rolling.
Nevertheless, auto-control has to be implemented from vessel to vessel, due to the difference between ship
dimension, configuration and application scope. A hierarchical control scheme may decouple the situation to
some extent and make the higher-level control universal to most types of vessels. Our industrial partners
have denoted efforts to this area and realizing model/model-free control algorithms for various maritime
operations. Therefore, in this package we will focus on:
- Organic combination of the optimization module
- Enhance prediction results by integrating control feedback into the predictor
- Case study of ship maneuvering in close range areas, taking path planning, prediction and auto-control as
a complete system
