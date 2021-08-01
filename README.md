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
