# Four-Quadrant Analog Multiplier based on square rooting circuit

This repositary presents the design of Four-quadrant Analog multiplier based on square rooting circuit implemented using synopsis custom compiler on 28nm CMOS Technology.

## Table of contents
 * [Introduction](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=Author-,Introduction,-An%20analog%20multiplier)
 * [Reference circuit details](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=neural%20networks%20etc.-,Reference%20circuit%20details,-Above%20figure%20shows)
 * [Reference circuit](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=dimensions%20of%20MOSFET-,Reference%20circuit,-Tools%20used)
 * [Tools Used](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=Reference%20circuit-,Tools%20used,-%E2%80%A2%20Synopsis%20custom%20compiler)
 * [Schematic of Four Quadrant Analog Multiplier based on square rooting circuit](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=custom%20compiler%20tool-,Schematic%20of%20Four%20Quadrant%20Analog%20Multiplier%20based%20on%20square%20rooting%20circuit,-The%20MOSFET%20model)
 * [Symbol of Four Quadrant Analog Multiplier based on square rooting circuit](https://github.com/AMITS424/Four-quadrant-analog-multiplier#:~:text=circuit%20is%2010-,Symbol%20of%20Four%20Quadrant%20Analog%20Multiplier%20based%20on%20square%20rooting%20circuit,-Schematic%20for%20neuron)
 * [Schematic for neuron activation function [5]](https://github.com/AMITS424/Four-quadrant-analog-multiplier#schematic-for-neuron-activation-function-5)
 * [Simulation Result for the four quadrant Analog Multiplier](https://github.com/AMITS424/Four-quadrant-analog-multiplier#:~:text=activation%20function%20%5B5%5D-,Simulation%20Result%20for%20the%20four%20quadrant%20Analog%20Multiplier,-1%2DTransient%20Analysis)
 
     	[Transient Analysis of the Multiplier](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=1%2DTransient%20Analysis%20of%20the%20Multiplier)
      
     	[Frequency Response of the multiplier](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=2%2DFrequency%20Response%20of%20the%20multiplier)
     
     	[Power Dissipation of the multiplier](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=3%2DPower%20Dissipation%20of%20the%20multiplier)
     
     	[Input noise of the multiplier](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=4%2DInput%20noise%20of%20the%20multiplier)
     
     	[Output noise of the multiplier](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=5%2DOutput%20noise%20of%20the%20multiplier)
 * [Netlist for the analog multiplier](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=of%20the%20multiplier-,Netlist%20for%20the%20Analog%20multiplier,-Netlist)
 * [Simulation result for neuron activation function](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=Netlist-,Simulation%20result%20for%20neuron%20activation%20function,-Results%20and%20Analysis)
 * [Results and Analysis](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=neuron%20activation%20function-,Results%20and%20Analysis,-Two%20sinusoidal%20waves)
 * [References](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=also%20be%20designed.-,References,-%5B1%5D%20N.%20Kiatwarin)
 * [Acknowledgements](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=2%2C%20April%202012.-,Acknowledgements,-Kunal%20Ghosh%2CFounder)
 * [Author](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/README.md#:~:text=Synopsis-,Author,-Amit%20Sarkar%2CM)

## Introduction
An analog multiplier is an important component for many signal processing algorithms, artificial neural network mapped into hardware. It has been proven that analog multipliers are used for application like neural network where we don’t require a very high level of accuracy. Analog multipliers provide high synapse density and high computational speed than a digital multiplier. A CMOS four quadrant analog multiplier[1] design is shown in this report. The designed circuit is simulated using 28nm CMOS process with 1.8 volt supply voltage. It is applicable for a wide range of applications like variable-gain amplifiers, peak detectors, modulators, phase detectors, artificial neural networks etc.

## Reference circuit details
![image](https://user-images.githubusercontent.com/99953169/154965322-2d433055-cfe8-4427-aa94-4554680ad83e.png)

Above figure shows a square rooting circuit, setting M3-M8 to be identical, the currents Ic and Id are found to be

Ic  =βp (V34+√(Ia/β p) )^2

Id  =βp (V34+√(Ib/β p) )^2

Where βp = µn Cox W/L

It can be easily shown that

Iout = I01-I02= 2V34 √ β p (√Ia -√Ib)

The reference analog multiplier circuit is shown in the next section where the output voltage is given by

Vout = V01 - V02  = R(I01-I02) 

Substituting the values of I_O1 and I_O2  it can be derived that

Vout = 2R√ β p β n V12 V34

Thus, the analog multiplier is designed where the gain can be changed by changing resistance values and the dimensions of MOSFET


## Reference circuit
![image](https://user-images.githubusercontent.com/99953169/154834613-8453b693-053d-4557-ab17-f26a795fcdae.png)

## Tools used
•	Synopsis custom compiler tool 



## Schematic of Four Quadrant Analog Multiplier based on square rooting circuit
* The MOSFET model chosen is TT model from 28nm PDK. Aspect ratio(W/L) of pMOS is 0.03um/0.24um & for nMOS it is 0.03um/0.12um
* Total no of transistor used for implementing the four quadrant analog multiplier based on square rooting circuit is 10

![image](https://user-images.githubusercontent.com/99953169/154834742-fb7912ec-922e-4f1e-ab07-9029f0fe7248.png)

## Symbol of Four Quadrant Analog Multiplier based on square rooting circuit
![image](https://user-images.githubusercontent.com/99953169/154834767-c19d9b75-02fb-40d7-8baa-5962bcdeba93.png)

## Schematic for neuron activation function [5]
![image](https://user-images.githubusercontent.com/99953169/155649295-d42f7fa6-f211-4cbc-ad20-85705eee1114.png)

## Simulation Result for the four quadrant Analog Multiplier
## 1-Transient Analysis of the Multiplier
![image](https://user-images.githubusercontent.com/99953169/154834864-29fbf296-64e6-4351-ad36-28464224c797.png)
![image](https://user-images.githubusercontent.com/99953169/155647633-ea3ff7b7-b222-4b98-91e0-dea1712f336a.png)

## 2-Frequency Response of the multiplier
![image](https://user-images.githubusercontent.com/99953169/154899140-9dd461f1-4e65-4328-80da-401c0687f7a2.png)

## 3-Power Dissipation of the multiplier
![image](https://user-images.githubusercontent.com/99953169/154849104-9d096605-1d4b-41f3-a75c-ca79e9051597.png)

## 4-Input noise of the multiplier
![image](https://user-images.githubusercontent.com/99953169/154898540-967dbe30-2d64-42ab-9850-1376714d9572.png)

## 5-Output noise of the multiplier
![image](https://user-images.githubusercontent.com/99953169/154898631-17f51d0b-307d-49f3-bb22-dbb604e0e26d.png)

## Netlist for the Analog multiplier
![image](https://user-images.githubusercontent.com/99953169/154834653-b53ced23-fd79-44a3-abed-89a147e979c2.png)

[Netlist](https://github.com/AMITS424/Four-quadrant-analog-multiplier/blob/main/netlist.pdf)

## Simulation result for neuron activation function
![image](https://user-images.githubusercontent.com/99953169/154945008-fe29ef07-2826-4bcf-a19f-d9380afadd6d.png)

## Results and Analysis
Two sinusoidal waves are given at the input of the multiplier. Each input having 100 mV amplitude and the frequencies are 50 MHz and 1 MHz respectively. At the output modulated wave is generated. After simulation it is concluded that the multiplier has bandwidth and power dissipation of 71.6 MHz  and 14.0300 µW respectively. A neuron activation function(NAF) is also simulated using 1.8 volt power supply. Using NAF and analog multiplier an analog neural network can also be designed.

![image](https://user-images.githubusercontent.com/99953169/154982532-d36851a1-3435-4b76-abc0-44d09f26882e.png)

## References
[1]	N. Kiatwarin, W. Ngamkham and W. Kiranon, “A Compact Low Voltage CMOS Four Quadrant Analog Multiplier”, ECTI International Conference,2007

[2]	B. Gilbert, “A precision four-quadrant multiplier with nanosecond response,” IEEE J. Solid-State Circuits, vol. SC-3, pp. 353-365, Dec. 1968

[3]	Alejandro Diaz-Sanchez, Juan Carlos Mateus-Ardila, Gregorio Zamora-Mejia, Alejandra Diaz-Armendariz, Jose Miguel Rocha-Perez, Luis Armando Moreno-Coria,” A four quadrant high-speed CMOS analog multiplier based on the flipped voltage follower cell” AEU - International Journal of Electronics and Communications,Volume 130, 2021. ISSN 1434-8411

[4]	S. Satyanarayana, Y. Tsividis and H. P. Graf, "A reconfigurable analog VLSI neural network chip" in Advances in Neural Information Processing Systems 2, CA, San Mateo:Morgan Kaufmann, vol. 2, pp. 758-768, 1990.

[5]	N.Chasta, S. Chouhan and Y. Kumar, “Analog VLSI Implementation of Neural Network Architecture for Signal Processing”,International Journal of VLSI Design & Comunication System, Vol.3, No.2, April 2012. 

## Acknowledgements
* [Kunal Ghosh](https://github.com/kunalg123),Founder,VSD Corp.Pvt.Ltd
* [IIT Hyderabad](https://iith.ac.in/)
* [Synopsis](https://www.synopsys.com/)

## Author 
[Amit Sarkar](https://github.com/AMITS424),M.tech in Microelectronics and VLSI

