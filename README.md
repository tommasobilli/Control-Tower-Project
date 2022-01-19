# Performance Evaluation of Computer Systems and Network

## _Project 10 -- Control Tower (1)_
This repository contains the final group project carried out as part of the Performance Evaluation of Computer Systems and Networks course in the MSc in Computer Engineering at the University of Pisa.

## Problem description
Consider  a  system  that  mimics  an  airport.   The  airport  consists  of  one runway, a  parking  area  and  a  control tower. The runway is used for landing/take-off and can be occupied by only one plane at a time, whereas the parking area has infinite capacity. The control tower manages the air traffic of the airport; each airplane follows the following steps to enter and leave the airport:
1. it queues for landing;
2. it lands on the runway;
3. it moves in the parking lot and stay here for a certain amount of time;
4. it queues for take-off;
5. it takes-off and leave the airport.

Landing and take-off operations, as well as parking, require a specific time for each airplane. In particular, for each plane we have:
- t<sub>l</sub>= time necessary to perform the landing operation;
- t<sub>p</sub>= time that the airplane will spend in the parking area;
- t<sub>o</sub>= time necessary to perform the take-off operation.

When the runway is occupied, planes that are required to land or take off are placed respectively in the landing queue or in the take-off queue. 
The queues are FIFO, and their capacity is assumed to be unlimited. When therunway is unoccupied instead, the control tower serves one airplane from a queue, prioritizing take-off over landing; planes in the landing queue are served only when the take-off queue is empty. Whenever a plane takes off, it leaves the system.

## Implementation
After an initial modeling of the system, we implemented our model using the open source Discrete Event Simulator [OMNeT++](https://omnetpp.org/). The source code can be found in the `src` directory.

## Analysis of collected results
At the end of each batch of simulations, a CSV file containing the set of output values is produced. To analyze and study such data, we took advantage of the moost popular data analysis libraries available in Python, including [pandas](https://pandas.pydata.org/), [NumPy](https://numpy.org/) and [SciPy](https://scipy.org/).
The `simulations/jupyter` directory contains the Jupyter Notebooks that were used to carry out our studies.

## How to run simulations
To automate the process of running multiple simulations with different set of parameters, we developed a simple bash script (`run_simulations.sh`, found in the `simulations` directory).
To run it, simply follow these steps:
- define first the set of factors to be used by the simulator in the `omnetpp.ini` file;
- `cd` into the `simulations` directory;
- either run the script with no arguments to run all configurations in the `omnetpp.ini` file, or specify a single configuration(s) to run.
