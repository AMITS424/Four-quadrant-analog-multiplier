# Introduction
An analog multiplier is an important component for many signal processing algorithms, artificial neural network mapped into hardware. It has been proven that analog multipliers are used for application like neural network where we don’t require a very high level of accuracy. Analog multipliers provide high synapse density and high computational speed than a digital multiplier. A CMOS four quadrant analog multiplier[1] design is shown in this report. The designed circuit is simulated using 28nm CMOS process with 1.8 volt supply voltage. It is applicable for a wide range of applications like variable-gain amplifiers, peak detectors, modulators, phase detectors, artificial neural networks etc.

# REFERENCE CIRCUIT
![image](https://user-images.githubusercontent.com/99953169/154834613-8453b693-053d-4557-ab17-f26a795fcdae.png)

# NETLIST
![image](https://user-images.githubusercontent.com/99953169/154834653-b53ced23-fd79-44a3-abed-89a147e979c2.png)

*  Generated for: PrimeSim
*  Design library name: AMIT
*  Design cell name: FOUR_QUADRANT_ANALOG_MULTIPLIER_tb
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Sun Feb 20 07:19:57 2022

.global gnd!
********************************************************************************
* Library          : AMIT
* Cell             : FOUR_QUADRANT_ANALOG_MULTIPLIER
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt four_quadrant_analog_multiplier gnd_1 v1 v2 v3 v4 vdd voneg vopos
xm8 net35 v2 net18 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm7 net32 v1 net18 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm6 net32 v2 net5 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm12 net35 v1 net5 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm4 net46 v1 net18 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm2 net18 net46 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm1 net37 v1 net5 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm0 net5 net37 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm11 net46 v4 gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm9 net37 v3 gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
r15 net32 net60 r=10k
r14 net35 net61 r=10k
e16 vopos voneg vcvs net60 net61 1 abs=0
.ends four_quadrant_analog_multiplier

********************************************************************************
* Library          : AMIT
* Cell             : FOUR_QUADRANT_ANALOG_MULTIPLIER_tb
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 gnd! net9 net18 net13 net21 net16 outn outp four_quadrant_analog_multiplier
v9 gnd! net21 dc=0 sin ( 0 100m 1meg 0 0 0 )
v7 gnd! net18 dc=0 sin ( 0 100m 50meg 0 0 0 )
v3 net13 gnd! dc=0 sin ( 0 100m 1meg 0 0 0 )
v1 net9 gnd! dc=0 sin ( 0 100m 50meg 0 0 0 )
v4 net16 gnd! dc=1.8

.tran '0.1u' '3u' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(net13) v(net9) v(outp)

.temp 25



.option primesim_output=wdf

# Schematic of Four Quadrant Analog Multiplier based on square rooting circuit
![image](https://user-images.githubusercontent.com/99953169/154834742-fb7912ec-922e-4f1e-ab07-9029f0fe7248.png)

# Symbol of Four Quadrant Analog Multiplier based on square rooting circuit
![image](https://user-images.githubusercontent.com/99953169/154834767-c19d9b75-02fb-40d7-8baa-5962bcdeba93.png)

# Simulation Result
![image](https://user-images.githubusercontent.com/99953169/154834864-29fbf296-64e6-4351-ad36-28464224c797.png)

# Remarks
Two sinusoidal waves are given at the input of the multiplier. Each input having 100 mV amplitude and the frequencies are 50 MHz and 1 MHz respectively. At the output modulated wave is generated. 
# References
[1]	N. Kiatwarin, W. Ngamkham and W. Kiranon, “A Compact Low Voltage CMOS Four Quadrant Analog Multiplier”, ECTI International Conference,2007

[2]	B. Gilbert, “A precision four-quadrant multiplier with nanosecond response,” IEEE J. Solid-State Circuits, vol. SC-3, pp. 353-365, Dec. 1968

[3]	Alejandro Diaz-Sanchez, Juan Carlos Mateus-Ardila, Gregorio Zamora-Mejia, Alejandra Diaz-Armendariz, Jose Miguel Rocha-Perez, Luis Armando Moreno-Coria,” A four quadrant high-speed CMOS analog multiplier based on the flipped voltage follower cell” AEU - International Journal of Electronics and Communications,Volume 130, 2021. ISSN 1434-8411

[4]	S. Satyanarayana, Y. Tsividis and H. P. Graf, "A reconfigurable analog VLSI neural network chip" in Advances in Neural Information Processing Systems 2, CA, San Mateo:Morgan Kaufmann, vol. 2, pp. 758-768, 1990.



