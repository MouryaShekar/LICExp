Design of a Fully Differential Telescopic OTA for High-Speed, Low-Noise Analog Applications
ABSTRACT:
Operational Transconductance Amplifiers (OTAs) are at the heart of many high-performance analog systems such as high-speed ADCs, analog filters, and data converters. Among the various OTA topologies, the Telescopic OTA stands out for its exceptionally high gain, low noise, and high-speed operation due to its minimal number of stacked transistors. However, it traditionally suffers from limited output swing. This drawback is addressed in the fully differential version, which improves common-mode rejection, linearity, and dynamic range. This project aims to design and simulate a fully differential telescopic OTA using CMOS 180nm technology. The architecture is optimized for low noise, high gain, and wide bandwidth, making it ideal for data acquisition systems and precision analog signal processing.
 INTRODUCTION 
The fully differential telescopic operational transconductance amplifier (OTA) is a crucial building block in high-speed, low-noise analog circuit design, particularly in applications such as data converters, filters, and analog front-ends. Its architecture is characterized by a high gain, wide bandwidth, and excellent common-mode rejection ratio (CMRR), which are essential for precision and speed.
The telescopic topology enhances the gain by stacking transistors, thereby increasing the output impedance without significantly increasing power consumption. When implemented in a fully differential configuration, this design provides improved linearity, reduced even-order harmonic distortion, and better noise performance due to symmetrical signal paths and common-mode noise rejection.
This OTA is especially favored in deep-submicron CMOS technologies for use in analog-to-digital converters (ADCs), sensor interfaces, and mixed-signal systems where speed and accuracy are paramount. The design involves careful trade-offs among gain, bandwidth, output swing, power, and noise, making it a challenging yet rewarding choice for modern analog IC designers
2. Circuit Architecture Overview
The telescopic OTA is a single-stage, high-gain amplifier formed by stacking the input differential pair directly on top of a cascode load.
2.1 Input Differential Pair (M1, M2)
The NMOS input pair offers high transconductance (gm) and low thermal noise. It is fed by a tail current source (M11) that defines the bias current.
2.2 Cascode Gain Enhancement (M3–M6)
Transistors M3 and M4 serve as cascode devices for M1 and M2, respectively. The cascode configuration significantly increases output impedance, thereby boosting gain.
2.3 Load Devices (M7–M10)
PMOS transistors M7 to M10 form the active load as current mirrors. They provide biasing and establish the differential output nodes (VO+ and VO–).
2.4 Common-Mode Feedback (CMFB)
A CMFB circuit is necessary in fully differential amplifiers to stabilize the output common-mode voltage. The CMFB adjusts the biasing of current mirrors to keep VO+ and VO– centered within the output swing.

CIRCUIT DIAGRAM:

I.	Design Specifications: Fully Differential Telescopic OTA
II.	1. Technology Node
•	CMOS Technology: 180 nm
•	Supply Voltage : 1.8 V
|        Parameter                  |Target Value|
|DC Gain                            |	≥ 80 dB    |
|Unity Gain Bandwidth (UGBW)        |	≥ 100 MHz  |
|Phase Margin	                      |≥ 60°       |
|Power Consumption                  |	≤ 1 mW     |
|Common-Mode Rejection Ratio (CMRR) |	≥ 80 dB    |
|Power Supply Rejection Ratio (PSRR)|	≥ 80 dB    |
|Input-Referred Noise	              |≤ 20 nV/√Hz |
|Slew Rate                          |	≥ 50 V/µs  |
|Output Swing (Differential)      	|≥ 1.2 Vpp   |
