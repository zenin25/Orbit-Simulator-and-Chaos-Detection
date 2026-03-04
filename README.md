# Orbital Chaos Simulator

## Overview

This project explores **stability and chaos in a simplified three-body gravitational system** using numerical simulation.

The system consists of:

* A **central star (Sun)**
* An **Earth-like planet**
* A **second massive planet**

The goal of the project is to investigate **how the mass of the second planet affects the long-term stability of the system**.

By running many simulations with different mass ratios, we can observe when the system remains stable and when it becomes unstable through:

* planetary collisions
* gravitational scattering
* orbital chaos

The project combines **physics, numerical simulation, and computational experimentation** to explore how chaotic behavior emerges in gravitational systems.


# Scientific Goal

The main objective is to determine **where the transition from stable to unstable orbital behavior occurs**.

To do this, the project performs a **parameter sweep** over many possible masses of the second planet.

For each simulation we record:

* the planet mass
* whether the system stayed stable
* whether the planets collided
* whether a planet escaped the system
* how long the system lasted before failure

From this data we can identify:

* **stable regions**
* **metastable regions**
* **chaotic transition zones**
* possible **islands of stability**

These structures commonly appear in real celestial mechanics problems such as:

* asteroid belt dynamics
* exoplanet system stability
* three-body gravitational systems



# Files in This Project

## orbit_animation.py

This script runs a **visual simulation of the orbital system**.

Features:

* Displays the Sun and planets
* Shows real-time orbital motion
* Draws fading orbit trails
* Detects events such as:

  * planet collision
  * planet escaping the system

Users can enter the masses of the planets and observe how the system evolves.

This script is primarily used for **visual exploration of the system**.


## sweep_simulation.py

This script performs the **main scientific experiment**.

It automatically runs **many simulations across a range of planet masses** to determine how stability changes as the system parameters vary.

For each simulation it records:

* planet mass
* outcome (stable / collision / escape)
* time before instability occurred

The results are saved to a CSV file for further analysis.

This script is designed to run **without graphics so that large numbers of simulations can be executed quickly**.


## classify_results.py

This script processes the raw simulation results and **classifies system behavior based on failure time**.

It separates the simulations into:

* **Stable** – system survived the entire simulation
* **Metastable** – system lasted a long time before failing
* **Unstable** – system failed quickly

This makes it easier to identify regions where **chaos begins to emerge**.


## stability_scan.csv

This file contains the **raw results from the parameter sweep experiment**.

Each row corresponds to one simulation run.

The columns record:

* Earth mass
* second planet mass
* simulation result
* failure time



## classified_stability_scan.csv

This file contains the **processed results** after classification.

It adds an additional column indicating whether the system is:

* stable
* metastable
* unstable

This makes it easier to analyze the stability structure of the system.



# Physics Background

Gravitational systems with three interacting bodies are known to produce **chaotic behavior**.

Unlike the two-body problem, which has an exact solution, the **three-body problem generally has no closed-form solution**.

Small changes in initial conditions or system parameters can produce dramatically different outcomes.

As a result, stability boundaries often contain:

* chaotic regions
* metastable behavior
* small islands of stability

The simulations in this project attempt to **map these structures numerically**.


# Technologies Used

Python

Libraries:

* numpy
* matplotlib

# Author

Siddharth S
