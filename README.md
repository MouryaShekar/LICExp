# LICExp1
## Aim:
To perform DC, transient, and AC analysis of a Common Source (CS) amplifier circuit using LTspice and extract various other parameters.
## Components required:
N-channel MOSFET(nmos4), Resistor (10K), Voltage supply (1.8V,0.9V) and connecting wires.
## Theory:
The Metal-Oxide-Semiconductor Field-Effect Transistor(MOSFET) is one of the most important components in electronics.
A MOSFET has a simple structure with only three terminals: Gate (G), Drain (D), and Source (S). 

MOSFETs are small and can be easily integrated into dense circuits, making them perfect for modern electronic devices, especially in VLSI (Very Large-Scale Integration) technology.MOSFETs use very little power.

MOSFETs can be connected in different ways, and each configuration offers different performance characteristics. The three main configurations are Common source, common drain and common gate.

MOSFET acts as amplifier in the saturation region when Vgs > Vth,Vgd < Vth , and Vds>=Vov for an N channel mosfet.

In the common-source configuration provides 180-degree Phase Shift,High Input Impedance and high voltage gain.
MOSFET Drain current equation:
The drain current (Id) in the saturation region is given by

**I<sub>d</sub> = 1/2*k<sub>n*(Vov)<sup>2</sup>**; **V<sub>ov</sub> = V<sub>gs</sub>-V<sub>th</sub>** **&** ****k<sub>n</sub>=W/L*u<sub>n</sub>*C<sub>ox</sub>**** for lambda = 0.

DC Analysis is performed to ensure the MOSFET is operating in the saturation region. It checks the biasing conditions, ensuring the MOSFET behaves as an amplifier. The drain current, gate-source voltage, and drain-source voltage are calculated.

Transient Analysis examines how the amplifier responds to a time-varying input signal, such as a sine wave. It provides insight into how the output signal changes over time in response to changes in the input signal.

AC analysis is used to determine the voltage gain of the amplifier. The voltage gain for a common-source amplifier is given by the equation**-gm*Rd**; gm is transconductance of the amplifier.

## Procedure:

Step 1: DC Analysis
Set up the circuit in LTspice, including the MOSFET,resistors, and supply voltage (Vdd).
change the name as CMOSN and give the length and width value.
Use the .op command to perform the DC operating point analysis in LTspice.
Check the DC values of drain current (Id), gate-source voltage (Vgs), and drain-source voltage (Vds).

Step 2: Transient Analysis 
Add an AC signal source (Vin) at the gate of the MOSFET.
Use the .tran command in LTspice for transient analysis.
Set the simulation time and time step (e.g., 10ms).
Observe the output waveform to measure the time-domain response, such as the output signal amplitude and phase shift.

Step 3: AC Analysis 
Replace the DC signal source with an AC signal source (small AC voltage like 1V).
Use the .ac command to perform frequency response analysis.
Set the frequency range, e.g., from 1 Hz to 10 MHz, and analyze the magnitude and phase of the voltage gain.
Observe the frequency response and note the gain and bandwidth.

## Circuit diagram:
![Circuit](https://github.com/user-attachments/assets/ead17790-c4ea-4b1e-8870-339b331f0366)
## Calculations:
Power = 100uW

Loop Equation: V<sub>dd</sub>=V<sub>ds</sub>+I<sub>d</sub>*R<sub>d</sub>

P=I*V (I<sub>d</sub>=55.55 uA , V<sub>dd</sub>=1.8V)

V<sub>ds</sub>=V<sub>out</sub>; V<sub>ds</sub>>=V<sub>gs</sub>-V<sub>th</sub>

R<sub>d</sub> (upon calculation) =10Kohm 

Widhth=0.2um(Vary width to get the current)

V<sub>ds</sub>=1.24V

gain=2.2dB(from AC analysis)

Q point is (1.24V,55.55uA)
## Tabular Column :

|Width  |  Current(Id) |  Vout |
|:----: |  :---------: |  :--: |
|1um    |  128.7uA     | 0.51  |
|0.5um  |  82.6uA      | 0.97  |
|0.2um  |  52.1uA      | 1.27  |
|0.23um |  55.0uA      | 1.25  |
|0.235um|  55.55uA     | 1.24  | 

## Results:
1.**DC Analysis:**
![DC analysis](https://github.com/user-attachments/assets/e3a217bb-5156-4ed3-8fc0-6b39a11e0db0)
Id=55.55uA\
Vout=1.24V\
Width=0.235um\
DC Operating point : (1.24V,55uA) is for 0.235um Width and 180nm Length.
2.**Transient Analysis:**
![Transient analysis](https://github.com/user-attachments/assets/1a4ed268-55a6-49a2-9a2b-39efdedeae6b)
Vout=1.24V\
Between the input and output, there is a 180 degree phase shift.
3.**AC Analysis:**
![AC analysis](https://github.com/user-attachments/assets/cf43fd43-b7c0-4ef9-a7e4-ca294f8cf238)
Gain:3.08dB
## Inference:
1. Drain current is directly propotional to the width of the MOSFET and the current varies with the change in width.

2. Q point stability is attained in saturation region and attains the linear amplification.








