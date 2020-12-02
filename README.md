# 6T SRAM

## Table Of Contents
- [SRAM Design](https://github.com/satabdi25-2000/vlsilabSRAM#sram-design)
- [Modes Of SRAM Operation](https://github.com/satabdi25-2000/vlsilabSRAM#modes-of-sram-operation)
- [Block Diagram Of SRAM](https://github.com/satabdi25-2000/vlsilabSRAM#block-diagram-of-sram)
- [SRAM Blocks](https://github.com/satabdi25-2000/vlsilabSRAM#sram-blocks)
  - [6T 1-Bit SRAM Cell](https://github.com/satabdi25-2000/vlsilabSRAM#6T-1-Bit-SRAM-Cell)
  - [Sense Amplifier](https://github.com/satabdi25-2000/vlsilabSRAM#sense-amplifier)
  - [Write Driver](https://github.com/satabdi25-2000/vlsilabSRAM#write-driver)
  - [Precharge Circuit](https://github.com/satabdi25-2000/vlsilabSRAM#precharge-circuit)
  - [Positive edge triggered D-FlipFlop](https://github.com/satabdi25-2000/vlsilabSRAM#Positive-edge-triggered-D--FlipFlop)
  - [TriState Buffer](https://github.com/satabdi25-2000/vlsilabSRAM#TriState-Buffer)



- [PreLayout Simulations](https://github.com/satabdi25-2000/vlsilabSRAM#PreLayout-Simulations)
  - [6T SRAM Cell](https://github.com/satabdi25-2000/vlsilabSRAM#6t-sram-cell)
  - [Sense Amplifier](https://github.com/satabdi25-2000/vlsilabSRAM#sense-amplifier)
  - [Write Driver](https://github.com/satabdi25-2000/vlsilabSRAM#write-driver)
  - [Precharge Circuit](https://github.com/satabdi25-2000/vlsilabSRAM#prechrage-circuit)
  - [Positive edge triggered D-FlipFlop](https://github.com/satabdi25-2000/vlsilabSRAM#Positive-edge-triggered-D--FlipFlop)
  - [TriState Buffer](https://github.com/satabdi25-2000/vlsilabSRAM#TriState-Buffer)


- [PostLayout Simulations](https://github.com/satabdi25-2000/vlsilabSRAM#PostLayout-Simulations)
  - [6T SRAM Cell](https://github.com/satabdi25-2000/vlsilabSRAM#6t-sram-cell)
  - [Sense Amplifier](https://github.com/satabdi25-2000/vlsilabSRAM#sense-amplifier)
  - [Write Driver](https://github.com/satabdi25-2000/vlsilabSRAM#write-driver)
  - [Precharge Circuit](https://github.com/satabdi25-2000/vlsilabSRAM#prechrage-circuit)
  - [Positive edge triggered D-FlipFlop](https://github.com/satabdi25-2000/vlsilabSRAM#Positive-edge-triggered-D--FlipFlop)
  - [TriState Buffer](https://github.com/satabdi25-2000/vlsilabSRAM#TriState-Buffer)

- [Integrated Circuit](https://github.com/satabdi25-2000/vlsilabSRAM#Integrated-Circuit)

- [Future Works](https://github.com/satabdi25-2000/vlsilabSRAM#Future-Works)

- [Acknowledgements](https://github.com/satabdi25-2000/vlsilabSRAM#Acknowledgements)

- [Contact Information](https://github.com/satabdi25-2000/vlsilabSRAM#Contact-Information)






# SRAM Design
This Project prioritizes on the design of SRAM using an OpenSource Compiler for SRAM known as **OpenRAM**.OpenRAM is a open source memory compiler which provides a platform to implement and test new memory designs. Design of the Custom memory SRAM requires Spice netlists,Layout files of the Custom Cells,Design Rules-DRC and LVS and Technology files-SCMOS and generates a SRAM array.

- **SRAM Design Specs** 
- **Memory Size**- *1k*32* 
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


# Block Diagram Of SRAM
![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/SRAM.png)

 
 
 
# SRAM Blocks

## 6T 1-Bit SRAM Cell

It is a Static Memory cell to store data where two cross-coupled CMOS inverters are connected storing DATA(**Q**) and complement of data(**Qbar**).It permits the modification(write) of data bits,as well as their retrieval(read) when needed.

**Block Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/6TSRAMCELL.png)

**Circuit Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/CircuitDiagram/6TSRAM.png)




## Sense Amplifier

The Sense Amplifier is a differential circuit amplifier to sense the voltage difference between BL and BLB while a read operation is performed.It recovers the signals from the bit-lines as they do not experience full voltage swing because of large load parasitic capacitance.

**Block Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/SENSEAMPLIFIER.png)

**Circuit Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/CircuitDiagram/SenseAmplifier.png)




## Write Driver

The write driver is used to drive the input signal into the bit-cell during a write operation and pulls down one of the bitlines according to the input data.

**Block Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/WRITEDRIVER.png)

**Circuit Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/CircuitDiagram/WRITEDRIVER.png)




## Precharge Circuit
It precharges the bit-lines during the first phase of the clock cycle before read and write operations.It has a third PMOS transistor which connects the two bit-lines together and equalizes the voltage between the two bit-lines.

**Block Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/PRECHARGECELL.png)

**Circuit Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/CircuitDiagram/Precharge.png)

## D-Flipflop 
It is necessary to synchronize the inputs and outputs with a clock signal. In OpenRAM,a master-slave D-flipflop is used for the synchronizing process.

**Block Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/DFF.png)

**Circuit Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/CircuitDiagram/DFF.png)



## TriState Buffer
The TriState Buffer enables and puts the output data on data bus.

**Block Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/Tristatebuffer.png)

**Circuit Diagram**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/CircuitDiagram/Tristatebuffer.png)




# PreLayout Simulations

Before doing the Layout,the prelayout simulatons checked.The read/write timing estimation in Spice is done using a *fast-single-6T* parasitic model.
*Fast-single-6T* parasitic models considers and estimates the parasitics of the wordlines and bitlines in the bit cell array analysing the capacitance for only 1-Bit Cell.


 **SNM**

The **Signal to Noise Margin(SNM)** for SRAM Cell = **0.40** 

It can be extracted by calculating the largest possible square in the two voltage transfer characteristic curves (VTC) of the involved CMOS inverters and get us to know how much noise the SRAM Cell can tolerate.

 
 ![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Simulation/SNMREAD6T.png)
 
 **DC Simulation**

The DC Simulation does the write and read sanity check for the SRAM cell,observing the trip point and checking the iterative threshold voltages taken for the simulation.

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Simulation/DCsimulation.png)


**PVT Variations**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/PVT1.png)
![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/BlockDiagram/PVT2.png)

Deciding sizing through Vtn iterations,
- Dc simulation with 3 process corners nom,ff,ss 
- Dc simulation with temperature ranges -40-125
- Transient simulation with 3 process corners nom,ff,ss with temperatures(-40-105)

TOTAL SIMULATION= DC(9WRITE+9READ) +TRAN(9WRITE+9READ)

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Simulation/VthvsTemperature.png)


**Simulation**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Simulation/PreLayoutSimulations/InputSignals.png)
![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Simulation/PreLayoutSimulations/OutputSignals.png)




# PostLayout Simulations

## 6T SRAM Cell

**Layout**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Layouts/6TSRAMCELL.png)


**Simulation**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/PostLayoutSimulations/6TSRAM.png)


## Sense Amplifier

**Layout**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Layouts/SenseAmplifier.png)

**Simulation**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/PostLayoutSimulations/SenseAmplifier.png)


## Write Driver

**Layout**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Layouts/WRITEDRIVER.png)

**Simulation**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/PostLayoutSimulations/WRITEDRIVER.png)


## Precharge Circuit

**Layout**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Layouts/PrechargeCircuit.png)

**Simulation**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/PostLayoutSimulations/PrechargeCircuit.png)

## Positive edge triggered D-Flipflop

**Layout**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Layouts/DFF.png)

**Simulation**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/PostLayoutSimulations/DFF.png)

## TriState Buffer

**Layout**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Layouts/TriStateBuffer.png)

**Simulation**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Simulation/PostLayoutSimulations/TriStateBuffer.png)




# Integrated Circuit

**Layout**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Layouts/IntegratedCircuit.png)

**Simulation**

![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Simulation/PostLayoutSimulations/InputSignals.png)
![](https://github.com/satabdi25-2000/vlsilabSRAM/blob/master/Simulation/PostLayoutSimulations/OutputSignals.png)




# Future Works

# Acknowledgements












 
