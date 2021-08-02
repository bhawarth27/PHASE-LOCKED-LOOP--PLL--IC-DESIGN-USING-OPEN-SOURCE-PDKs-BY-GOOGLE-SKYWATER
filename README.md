# PHASE-LOCKED-LOOP-(PLL)-IC-DESIGN-USING-OPEN-SOURCE-PDKs-BY-GOOGLE-SKYWATER


![Screenshot (1066)](https://user-images.githubusercontent.com/35188692/127750108-df95ef4c-b283-4c7a-b14e-1d5fd7333671.png)


*31 July 2021 - 1 August 2021*

## Contents


### --> Day-1 - PLL Theory and lab setup

* Introduction to PLL
* Introduction to Phase Frequency Detector
* Introduction to Charge Pump
* Introduction to VCO and Frequency Divider
* Tool setup and design flow
* Introduction to PDK, specifications and pre-layout circuits
* Circuit design simulation tool - Ngspice Setup
* Layout design tool - Magic Setup

### --> Day-2 - PLL Labs and Post-Layout Simulations

* PLL components circuit design
* PLL components circuit simulations
* Steps to combine PLL sub-circuits and PLL full design simulation
* Troubleshooting steps
* Layout design
* Layout Walkthrough
* Parasitics extraction
* Post Layout simulations
* Steps to combine layouts
* Tapeout theory
* Tapeout labs

# Day-1 PLL Theory and lab setup

The agenda of Day-1 was to get fimiliar with PLL and its building blocks. The instructor of the course one by one explained each component of the PLL. Later in the day we also got the falvour of various open source tools (like- ngspice , magic) which we will be using during the workshop.

## Introduction to PLL

Phase locked loop is used to get a precise clock signal without frequency or phase noise

![Screenshot (1067)](https://user-images.githubusercontent.com/35188692/127751553-1465a43d-2117-4b3a-a290-a2f9c40505f5.png)

![Screenshot (1068)](https://user-images.githubusercontent.com/35188692/127751577-783a5904-0fa7-45bb-9dd2-b4a8a81c0ab7.png)


## COMPONENTS OF PLL

### 1) Phase Frequency Detector 

### 2) Charge Pump

Converts the digital measure of phase/frequency diffrence into a analog control signal to vcontrol voltage controlled oscillator

![Screenshot (1069)](https://user-images.githubusercontent.com/35188692/127752104-58a0c83e-132e-4866-a08b-ec44b805f3aa.png)

* Operation of charge pump

![Screenshot (1070)](https://user-images.githubusercontent.com/35188692/127752131-03cba342-a3d6-45b7-b458-f1961a9d5df1.png)

![Screenshot (1071)](https://user-images.githubusercontent.com/35188692/127752158-1f4670fb-172e-44c0-ab0a-ca28a1eca086.png)

### 3) Loop filter

![Screenshot (939)](https://user-images.githubusercontent.com/35188692/127752245-2660aec8-66d2-47d9-a36c-5d03afa42e73.png)

### 4) Voltage controlled oscillator

![Screenshot (1077)](https://user-images.githubusercontent.com/35188692/127763215-7cb48909-e2c9-41fe-bfa0-1e002a2ccbbc.png)

### 5) Frequency dividoer

![Screenshot (1078)](https://user-images.githubusercontent.com/35188692/127763246-0e894de9-ac72-4e10-8659-78dccd38cbd9.png)

# Day-2 PLL labs and Post-Layout Simulations

This day mainly focuses on the prelayout and postlayout simulations and weather they were as per our expectations or not. 

## PRE-LAYOUT SIMULATIONS:-

Pre-layout simulation we do to check weather weather we are meeting the specifications before be actually go into the layout phase. This stage is crucial because if our circuit is not logically correct than what is the point of layout of the that circuit. These simulations are not close to real-world because we are here using ideal wires which are free from all parasitics.

The command to obtain the pre-layout simulation is:
```ngspice circuitname.cir```


### VCO:

![Screenshot (1088)](https://user-images.githubusercontent.com/35188692/127853698-5b548717-c0c4-47d9-99b5-051350b17ad3.png)


### Frequency Divider:

![image](https://user-images.githubusercontent.com/35188692/127853471-c95d6f21-7802-49db-923e-b5197ea56083.png)


### PLL:

![image](https://user-images.githubusercontent.com/35188692/127854002-1cadf739-bb94-454b-bfd9-809d8e9737a8.png)


## How to manipulate .cir/.spice file to get our desired output

Here the task for us was to make changes in the .cir file of the perticular block to get the desired result

* 1) First we  'git clone https://github.com/lakshmi-sathi/avsdpll_1v8' this directory
* 2) Then we change the tran parameters so that we can get the output (here, leakage current of charge pump) at 20us

![Screenshot (1081)](https://user-images.githubusercontent.com/35188692/127775250-fc303770-2d6b-4d46-94ae-62acff02a9e2.png)


* 3) Then we gave ngspice CP.cir command in the terminal to see the prelayout output waveforms of Charge Pump

![Screenshot (1083)](https://user-images.githubusercontent.com/35188692/127775502-a98cdf81-8cc5-4333-8073-fa59cf8a6c7a.png)


## LAYOUTS :-
The command to obtain the layout is:
```magic -T sky130A.tech circuitname.mag```

### Frequency Divider:

![Screenshot (1089)](https://user-images.githubusercontent.com/35188692/127854829-1920527c-e487-4a89-a453-9b188bf5a429.png)

* For calculation of area of the layout we just have to draw a rectangle overlapping the layout and then enter "box" command in the magic tool's command window
* similarly we can find area of all the blocks

### VCO:

![image](https://user-images.githubusercontent.com/35188692/127855527-e655f208-b6ef-4587-9ea8-12e0eed7bc4b.png)
AREA- 57.72um square

### Charge Pump:

![image](https://user-images.githubusercontent.com/35188692/127855612-1466417e-3849-47b6-b295-fcf72318cbde.png)
AREA- 132.27um square

### PLL:

![image](https://user-images.githubusercontent.com/35188692/127855722-314ce7bb-4440-4652-b867-b557d0d74864.png)
AREA- 496um square

## POST-LAYOUT SIMULATIONS :- 

Post-layout simulation is done to check weather after after layout the circuit is meeting the specifications or not. These simulation results are much closer to real-world because layout has real wires which have finite amount of resistance,capacitance and even inductance which might as well effect our results. 

The command to obtain the pre-layout simulation is:
```ngspice circuitname.cir```

### VCO:
![Screenshot (1090)](https://user-images.githubusercontent.com/35188692/127856431-44278b88-d8b3-4d2e-9259-39aa94c5179c.png)


### Frequency divider:
![image](https://user-images.githubusercontent.com/35188692/127856463-d9427bd7-fac7-446d-8c88-df15e2cc4804.png)


### PLL:
![image](https://user-images.githubusercontent.com/35188692/127856494-da2e722d-c805-40c2-a8a7-b92221585616.png)

