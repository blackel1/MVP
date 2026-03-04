# Cellular Automata Project

## Overview
This project explores the fascinating world of cellular automata, including foundational concepts and specific implementations. Two main models are demonstrated in this project:

1. **Conway's Game of Life**
   - A zero-player game where patterns evolve according to specific rules.
   - This model illustrates emergent phenomena from simple initial configurations.

2. **SIRS Epidemic Model**
   - A model that simulates the spread of diseases through a population.
   - SIRS stands for Susceptible, Infected, Recovered, and Susceptible again, showcasing the lifecycle of disease spread in a population.

## Implementations
The code for these implementations can be found in their respective directories, complete with visualizations and experiments that show the dynamics of cellular automata in action.




#### **1. Game of Life**



###### **Default Parameters:**

&nbsp;	-init random

&nbsp;	-sweeps 10000

&nbsp;	-size 50



###### **Animation:**

Run animations of different initial configurations:

python gameoflife.py --measurement animation --init random

python gameoflife.py --measurement animation --init blinker

python gameoflife.py --measurement animation --init glider



###### **Equilibration:** 

Runs multiple simulations to determine the time taken for the system to reach a stable or repeating configuration

python gameoflife.py --measurement equilibration --steps 400



###### **Glider Speed:**

Measures the velocity of the glider by tracking the centre of mass of the live cells over time

python GOL.py --measurement glider\_speed --sweeps 400



###### **Output files:**

Results are stored in the directory: Results/

This directory contains the plots and the raw .dat files used to generate them



###### **Data File Key:**

Equilibration

equilibration\_data.dat

columns: time

equilibration\_hist\_random.png



Glider Speed

glider\_speed\_data.dat

columns: time, x\_com, y\_com, r

where: x\_com = x coordinate of centre of mass, y\_com = y coordinate of centre of mass, r = distance from origin

glider\_speed\_plots\_dim\_50.png



#### **2. SIRS**



###### **Defaults:**

-sweeps 1000

-size 50



###### **Animation:**

Different behaviours can be observed depending on the transition probabilities

Absorbing State: p1=0.1, p2=0.9, p3=0.1



Dynamic Equilibrium: p1=0.5, p2=0.5, p3 =0.5



Cyclic Wave of Infections: p1=0.8, p2=0.1, p3=0.01



###### **Phase Diagram:**

Computes the average infected fraction <I>/N over parameter space

python SIRS.py --dim 50 --measurement phase\_space --sweeps 1000



###### **Variance Measurement:**

Measures the variance of the infected population across the transition region

python SIRS.py --dim 50 --measurement variance --sweeps 10000



###### **Vaccination Experiment:**

Measures the effects of permanent immunity on infection spreading

Standard parameter set: Vaccination with p1 = p2 = p3 = 0.5:

python SIRS.py --dim 50 --measurement vaccine --p1 0.5 --p2 0.5 --p3 0.5



Cyclic wave regime: Vaccination with p1 = 0.8 p2 = 0.1 p3 = 0.02:

python SIRS.py --dim 100 --measurement vaccine --p1 0.8 --p2 0.1 --p3 0.02



###### **Output files:**

Results are stored in the directory: Results/

This directory contains the plots and the raw .dat files used to generate them



###### **Datafiles Key:**



phase\_diagram\_mean\_p2\_0p5 columns: p1, p3, <I>/N

phase\_diagram\_mean\_L50\_dp0.05.png



variance\_cut\_L50\_p2\_0p5\_p3\_0p5 columns: p1, variance, err\_bootstrap, err\_block

variance\_cut\_L50\_block.png

variance\_cut\_L50\_bootstrap.png



vaccine\_L50\_p0p5: fIm, <I>/N

vaccine\_curve\_L50.png







