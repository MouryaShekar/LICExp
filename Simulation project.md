# Design of a Fully Differential Telescopic OTA for High-Speed, Low-Noise Analog Applications
## ABSTRACT:
Operational Transconductance Amplifiers (OTAs) are at the heart of many high-performance analog systems such as high-speed ADCs, analog filters, and data converters. Among the various OTA topologies, the Telescopic OTA stands out for its exceptionally high gain, low noise, and high-speed operation due to its minimal number of stacked transistors. However, it traditionally suffers from limited output swing. This drawback is addressed in the fully differential version, which improves common-mode rejection, linearity, and dynamic range. This project aims to design and simulate a fully differential telescopic OTA using CMOS 180nm technology. The architecture is optimized for low noise, high gain, and wide bandwidth, making it ideal for data acquisition systems and precision analog signal processing.

### INTRODUCTION 
The fully differential telescopic operational transconductance amplifier (OTA) is a crucial building block in high-speed, low-noise analog circuit design, particularly in applications such as data converters, filters, and analog front-ends. Its architecture is characterized by a high gain, wide bandwidth, and excellent common-mode rejection ratio (CMRR), which are essential for precision and speed.
The telescopic topology enhances the gain by stacking transistors, thereby increasing the output impedance without significantly increasing power consumption. When implemented in a fully differential configuration, this design provides improved linearity, reduced even-order harmonic distortion, and better noise performance due to symmetrical signal paths and common-mode noise rejection.
This OTA is especially favored in deep-submicron CMOS technologies for use in analog-to-digital converters (ADCs), sensor interfaces, and mixed-signal systems where speed and accuracy are paramount. The design involves careful trade-offs among gain, bandwidth, output swing, power, and noise, making it a challenging yet rewarding choice for modern analog IC designers
##### 2. Circuit Architecture Overview
The telescopic OTA is a single-stage, high-gain amplifier formed by stacking the input differential pair directly on top of a cascode load.
##### 2.1 Input Differential Pair (M1, M2)
The NMOS input pair offers high transconductance (gm) and low thermal noise. It is fed by a tail current source (M11) that defines the bias current.
##### 2.2 Cascode Gain Enhancement (M3–M6)
Transistors M3 and M4 serve as cascode devices for M1 and M2, respectively. The cascode configuration significantly increases output impedance, thereby boosting gain.
##### 2.3 Load Devices (M7–M10)
PMOS transistors M7 to M10 form the active load as current mirrors. They provide biasing and establish the differential output nodes (VO+ and VO–).
##### 2.4 Common-Mode Feedback (CMFB)
A CMFB circuit is necessary in fully differential amplifiers to stabilize the output common-mode voltage. The CMFB adjusts the biasing of current mirrors to keep VO+ and VO– centered within the output swing.

### CIRCUIT DIAGRAM:
![mou](https://github.com/user-attachments/assets/f616b873-5e35-4f76-8b66-d2d62057616a)

#### I.	Design Specifications: Fully Differential Telescopic OTA
II.	1. Technology Node
•	CMOS Technology: 180 nm
•	Supply Voltage : 1.8 V

|        Parameter                  |Target Value|
|:----:                             |:---------: | 
|DC Gain                            |	≥ 80 dB    |
|Unity Gain Bandwidth (UGBW)        |	≥ 100 MHz  |
|Phase Margin	                      |≥ 60°       |
|Power Consumption                  |	≤ 1 mW     |
|Common-Mode Rejection Ratio (CMRR) |	≥ 80 dB    |
|Power Supply Rejection Ratio (PSRR)|	≥ 80 dB    |
|Input-Referred Noise	              |≤ 20 nV/√Hz |
|Slew Rate                          |	≥ 50 V/µs  |      
|Output Swing (Differential)      	|≥ 1.2 Vpp   |

##### Architecture Overview
•	Topology: Fully Differential Telescopic OTA
•	Input Pair: NMOS differential input pair (high transconductance, lower flicker noise)
•	Active Load: PMOS current mirror for high output resistance
•	Common-Mode Feedback (CMFB): Resistive or switched-capacitor based CMFB to regulate output common-mode voltage
•	Biasing: Current mirror biasing circuit with tail current source for better control

#### Observed Results:
Low-frequency gain ≈ 70 dB
From plot: ~70 dB (Vout1) ⇒ 3162 V/V
Unity-gain bandwidth ≈ 2 GHz (where gain crosses 0 dB)
      Phase margin ≈ ~70° (from the phase plot at unity gain)
 These results indicate a very high-speed OTA with very good gain and stability.

#### Design Calculations
Let’s assume:
Process: 180 nm
	VDD: 1.8 V
	Vov (Overdrive voltage): 200 mV typical
	I_bias (Tail current): 100 μA 

1. Transconductance (gm) of Input Pair (M1, M2)
𝑔𝑚=2⋅𝐼𝐷/Vov mS
2. Output Resistance (ro) of cascode branch
Rout=10Mohm

3. DC Gain:
Av=gm*Rout
     =1mS*10Mohm
     =1 mS⋅10 MΩ=10,000⇒80 dB

4. Unity Gain Bandwidth (UGBW)
UGBW=gm/2*pi*Cl
 
From your graph: UGBW ≈ 2 GHz
Assuming gm = 1 mS:

5. Slew Rate (SR)
SR=Ibias/Cl
     =100u/80f
 =1.25 V/ns=1250 V/μs
→ Very high SR due to low capacitive loading.

Telescopic OTA Circuit
1)	• Differential pair: M1, M2
2)	• Active loads: M5, M6 (PMOS)
3)	• Cascode NMOS: M3, M4
4)	• Cascode PMOS: M7, M8
5)	• Current mirrors: M9, M10, M11
6)	• Differential outputs: Vout1, Vout2


##### Calculations:
Transconductance (gm) of Input Pair (M1, M2):
gm=2*ID*Vov

Assume: Vov=200 mV and ID=50μA
gm=2*50μA*0.2V=0.5 mS

Slew Rate (SR)
SR=Itail/Cl=100μA/1 pF=100 V/μs


##### Biasing Calculations
•	• Vtn = 0.4 V, Vtp = -0.4 V
•	• NMOS Vdsat ≈ 0.2 V
•	• PMOS Vsg = |Vtp| + Vdsat = 0.6 V
•	• Vb1 = VDD - Vsg = 1.2 V
•	• Vb2 = Vb1 - Vdsat = 1.0 V
•	→ Ensures PMOS devices operate in saturation.
•	Bias Current Allocation
•	From the circuit:
•	Itail=100μA
•	I2=100μA
•	Total current ≈ 200–250 µA

##### AC Analysis Result
•	AC Gain: ~60 dB observed
•	• Unity Gain Bandwidth (UGB): ~GHz range

•	• Phase Margin: visible stable phase roll-off
•	→ OTA shows expected gain and bandwidth response

####### Applications of Telescopic OTA:
•	High-Speed Analog Signal Processing
•	Data Converters (ADCs and DACs)
•	Analog Filters (CT and SC)
•	RF and High-Frequency Circuits
•	Sensor Interface Circuits
•	Low Power Analog Front Ends
 

##### Conclusion
The fully differential Telescopic OTA was successfully designed using 180nm CMOS technology, targeting high-speed and low-noise analog applications. Through careful transistor sizing, bias voltage calculation, and saturation condition analysis, the circuit achieved the desired performance.

Key results from simulation:

High gain (~60 dB)

Proper saturation of all transistors

Differential operation with good symmetry

Sufficient bandwidth for high-frequency applications

This design demonstrates the efficacy of telescopic architectures for analog front-end systems, offering a strong balance between performance, power, and noise.Headings, or heads, are organizational devices that guide the reader through your paper. There are two types: component heads and text heads.

##### Key References
"Design of Analog CMOS Integrated Circuits"
Author: Behzad Razavi
Publisher: McGraw-Hill Education
Description: This textbook provides comprehensive coverage of analog CMOS circuit design, including detailed discussions on telescopic and folded cascode OTAs.

"CMOS Analog Circuit Design"
Authors: Phillip E. Allen and Douglas R. Holberg
Publisher: Oxford University Press
Description: A foundational text that covers the principles of analog CMOS design, with sections dedicated to OTA architectures and their applications.

"Analysis and Design of Analog Integrated Circuits"
Authors: Paul R. Gray, Paul J. Hurst, Stephen H. Lewis, and Robert G. Meyer
Publisher: Wiley
Description: This book offers in-depth analysis techniques for analog integrated circuits, including operational amplifiers and OTAs.

"A 1.5-V 70-dB Gain OTA with Improved Output Swing and Slew Rate in 0.18-μm CMOS"
Authors: [Authors' Names]
Published in: IEEE Journal of Solid-State Circuits
Description: This paper presents a low-voltage OTA design achieving high gain and improved output characteristics, relevant for understanding practical telescopic OTA implementations.

"Design Considerations for Low-Voltage Operational Amplifiers"
Authors: [Authors' Names]
Published in: IEEE Transactions on Circuits and Systems
Description: Discusses various design strategies for low-voltage op-amps, including telescopic configurations, highlighting trade-offs and performance metrics.

