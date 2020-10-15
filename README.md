# 6T SRAM

## Table Of Contents
- [SRAM Design](https://github.com/satabdi25-2000/vlsilabSRAM#sram-design)
- [Modes Of SRAM Operation](https://github.com/satabdi25-2000/vlsilabSRAM#modes-of-sram-operation)
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
This Project prioritizes on the design of SRAM using an OpenSource Compiler for SRAM known as **OpenRAM**.OpenRAM is a open source memory compiler which provides a platform to implement and test new memory designs. Design of the SRAM writing Spice netlist and simulating with **NgSpice**,also used a Schematic Editor-**Sue2** and **CppSim**.Layout of cells through OpenSource Layout Tool-**Magic**.

- **SRAM Design Specs** 
- **Memory Size**- *1k-32bit* 
- **Supply voltage**-*5.0v* 
- **Technology**- *scn4m_subm 0.5um*


# Modes Of SRAM Operation
 
 **Hold State**

- **WORDLINE=0** 
- Access transistors(M3,M4)-OFF
- Bistable operating points
- Previous data stored
 
 **Read Mode**
 
- **WORDLINE=1**
- Access transistors(M3,M4)-ON
- Bitlines Precharged
- Data(Q) to be read
 
 **Write Mode**
 
- **WORDLINE=1**
- Access transistors(M3,M4)-ON
- Bitline/Bitlinebar=0(According to data-Done by write driver)
- Data(Q) to be flipped/written over previous value
 
 **SNM**

The **Signal to Noise Margin(SNM)** for SRAM Cell = **0.63** 

It can be extracted by calculating the largest possible square in the two voltage transfer characteristic curves (VTC) of the involved CMOS inverters and get us to know how much noise the SRAM Cell can tolerate.

 
 ![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Simulation/SNM6T.png)
 
 
 
 
 
 
 
 # Block Diagram
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


## Sense Amplifier

**Block Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/SENSEAMPLIFIER.png)


**Circuit Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/CircuitDiagram/SenseAmplifier.png)


## Write Driver

**Block Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/WRITEDRIVER.png)


**Circuit Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/CircuitDiagram/SenseAmplifier.png)

## Precharge Circuit

**Block Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/PRECHARGECELL.png)


**Circuit Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/CircuitDiagram/SenseAmplifier.png)
