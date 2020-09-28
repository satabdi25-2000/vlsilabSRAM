# 6T SRAM

## Table Of Contents
- [SRAM Design](https://github.com/satabdi25-2000/vlsilabSRAM#sram-design)
- [Block Diagram Of SRAM](https://github.com/satabdi25-2000/vlsilabSRAM#block-diagram-of-sram)
- [SRAM Blocks](https://github.com/satabdi25-2000/vlsilabSRAM#sram-blocks)
  - [BitCell Array](https://github.com/satabdi25-2000/vlsilabSRAM#bitcell-array)
  - [Sense Amplifier](https://github.com/satabdi25-2000/vlsilabSRAM#sense-amplifier)
  - [Write Driver](https://github.com/satabdi25-2000/vlsilabSRAM#write-driver)
  - [Precharge Circuit](https://github.com/satabdi25-2000/vlsilabSRAM#precharge-circuit)

- [Circuit Diagram](https://github.com/satabdi25-2000/vlsilabSRAM#circuit-diagram)
- [Simulation on NgSpice](https://github.com/satabdi25-2000/vlsilabSRAM#simulation-on-ngspice)
  - [6T SRAM Cell](https://github.com/satabdi25-2000/vlsilabSRAM#6t-sram-cell)
  - [Bit Cell Array](https://github.com/satabdi25-2000/vlsilabSRAM#bit-cell-array)
  - [Sense Amplifier](https://github.com/satabdi25-2000/vlsilabSRAM#sense-amplifier)
  - [Write Driver](https://github.com/satabdi25-2000/vlsilabSRAM#write-driver)
  - [Precharge Circuit](https://github.com/satabdi25-2000/vlsilabSRAM#prechrage-circuit)



# SRAM Design
This Project prioritizes on the design of SRAM using an OpenSource Compiler for SRAM known as **OpenRAM**. Design of the SRAM writing Spice netlist and simulating with **NgSpice**,also used a Schematic Editor-**Sue2** and **CppSim**.Layout of cells through OpenSource Layout Tool-**Magic**.

SRAM Specs - Memory Size of **1k-32bit** with Supply voltage of **5.0v** with 
*scn4m_subm* technology that is 0.5um. 
 

## Block Diagram
![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/SRAM.png)







# SRAM Blocks

## BitCell Array

It is a Static Memory cell to store data where two cross-coupled CMOS inverters are connected storing DATA(**Q**) and complement of data(**Qbar**).It permits the modification(write) of data bits,as well as their retrieval(read) when needed.

**Circuit Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/CircuitDiagram/BitCellAray-precharge-pulldown.png)

**Simulation**

**DC Simulation**

The DC Simulation was done to do the write and read sanity check for the SRAM cell,observing the trip point and checking the iterative threshold voltages taken for the simulation.Tested it in Temperature ranges-**-40-125** and Corners-**ss,nom,ff**.

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Simulation/DCsimulation.png)

**SNM-Signal to Noise Margin**


The **Signal to Noise Margin(SNM)** for SRAM Cell = **0.63** 

It can be extracted by calculating the largest possible square in the two voltage transfer characteristic curves (VTC) of the involved CMOS inverters and get us to know how much noise the SRAM Cell can tolerate.

## Sense Amplifier

**Circuit Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/CircuitDiagram/SenseAmplifier.png)


## Write Driver

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/BlockDiagram/WriteDriver.png)


## Precharge Circuit

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/BlockDiagram/PreCharge.png)
