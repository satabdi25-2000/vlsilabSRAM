# 6T SRAM

## Table Of Contents
- [SRAM Design](https://github.com/ReuelReuben/vsdSRAM#sram-design)
- [Block Diagram Of SRAM](https://github.com/ReuelReuben/vsdSRAM#basic-architectural-block-diagram)
- [SRAM Blocks](https://github.com/ReuelReuben/vsdSRAM#pre-layout)
  - [BitCell Array](https://github.com/ReuelReuben/vsdSRAM#6t-memory-cell)
  - [Sense Amplifier](https://github.com/ReuelReuben/vsdSRAM#sense-amplifier)
  - [Write Driver](https://github.com/ReuelReuben/vsdSRAM#write-driver)
  - [Precharge Circuit](https://github.com/ReuelReuben/vsdSRAM#tri-state-buffer)

- [Circuit Diagram](https://github.com/ReuelReuben/vsdSRAM#installing-and-simulating-on-ngspice)
- [Simulation on NgSpice](https://github.com/ReuelReuben/vsdSRAM/blob/master/Readme.md#future-works)
  - [6T SRAM Cell](https://github.com/ReuelReuben/vsdSRAM#6t-memory-cell)
  - [Bit Cell Array](https://github.com/ReuelReuben/vsdSRAM#6t-memory-cell)
  - [Sense Amplifier](https://github.com/ReuelReuben/vsdSRAM#sense-amplifier)
  - [Write Driver](https://github.com/ReuelReuben/vsdSRAM#write-driver)
  - [Precharge Circuit](https://github.com/ReuelReuben/vsdSRAM#tri-state-buffer)



# SRAM Design
This Project prioritizes on the design of SRAM using an OpenSource Compiler for SRAM known as **OpenRAM**. Design of the SRAM writing Spice netlist and simulating with **NgSpice**,also used a Schematic Editor-**Sue2** and **CppSim**.Layout of cells through OpenSource Layout Tool-**Magic**.

SRAM Specs - Memory Size of **1k-32bit** with Supply voltage of **5.0v** with 
*scn4m_subm* technology that is 0.5um. 
 

# Block Diagram Of SRAM
![](Documentation/BlockDiagram.png)






# SRAM Blocks

## 6T Memory cell

It is a Static Memory cell to store data where two cross-coupled CMOS inverters are connected storing DATA(**Q**) and complement of data(**Qbar**).It permits the modification(write) of data bits,as well as their retrieval(read) when needed.
![](https://github.com/ReuelReuben/vsdSRAM/blob/master/BlockDiagram/6TMem.png)

### Circuit Diagram

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/CircuitDiagram/6TMemCell.png)

### Simulation

**DC Simulation**

The DC Simulation was done to do the write and read sanity check for the SRAM cell,observing the trip point and checking the iterative threshold voltages taken for the simulation.Tested it in Temperature ranges-**-40-125** and Corners-**ss,nom,ff**.

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/PreLayoutWaveforms/6TMemCell/6TCellPrelayout.png)

**SNM-Signal to Noise Margin**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/PreLayoutWaveforms/6TMemCell/Screenshot%20from%202020-08-02%2018-01-50.png)

The **Signal to Noise Margin(SNM)** for SRAM Cell = **0.63** 

It can be extracted by calculating the largest possible square in the two voltage transfer characteristic curves (VTC) of the involved CMOS inverters and get us to know how much noise the SRAM Cell can tolerate.

## Sense Amplifier

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/BlockDiagram/SenseAmp.png)

**Circuit Diagram**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/CircuitDiagram/SenseAmplifier.png)

**Simulation**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/PreLayoutWaveforms/SenseAmpCell/SenseAmpPreLayout1.png)


## Write Driver

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/BlockDiagram/WriteDriver.png)

**Circuit Diagram**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/CircuitDiagram/WriteDriver.png)

**Simulation**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/PreLayoutWaveforms/WriteDriverCell/WriteDrivePreLayout.png)


## Pre-Charge Circuit

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/BlockDiagram/PreCharge.png)

**Circuit Diagram**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/CircuitDiagram/PreCharge.png)

**Simulation**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/PreLayoutWaveforms/PreChargeCell/PrechargePreLayout.png)


## Write Driver

**Layout**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/Layouts/WriteDriver.png)

**Simulation**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/PostLayoutWaveforms/WriteDriverCell/WriteDrivePostLayout.png)

**For Post Layout Simulation please** [click here](https://github.com/ReuelReuben/vsdSRAM#write-driver-3)

## Tri-State Buffer

**Layout**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/Layouts/TriGateBuffer.png)

**Simulation-1**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/PostLayoutWaveforms/TrigateCell/TrigateBufPostLayout1.png)

**For Post Layout Simulation please** [click here](https://github.com/ReuelReuben/vsdSRAM#tri-state-buffer-3)

**Simulation-2**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/PostLayoutWaveforms/TrigateCell/TrigateBufPostLayout2.png)

## Pre-Charge Circuit

**Layout**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/Layouts/PreChargeCell.png)

**Simulation**

![](https://github.com/ReuelReuben/vsdSRAM/blob/master/PostLayoutWaveforms/PreChargeCell/PrechargePostLayout.png)

