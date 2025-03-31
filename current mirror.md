# Linear Integrated Circuit
# Current Mirroring Experiment
# PART-A
## Aim

Design and Analyze Current mirror circuit as active load in amplifier circuit.

**Given** :

Vdd=1.8V,P<=1mW,Av>-10V/V

## DC Analysis:(for mirror ratio 1:1)

WKT It=Iref+Ix<br>
So, for 1:1 ratio Iref=Ix<br>
i,e Iref=It/2<br>
It=1mW/1.8V<br>
It=0.555mA.<br>
Therefore,Iref=0.2778mA.<br>

To get the correct current based on the given ratio, the W/L values for M1, M2, and M3 are all set to 3um/180nm. The input voltage (Vin) is chosen to be 0.838V to ensure that the transistors are operating in the saturation region.

![expacir](https://github.com/user-attachments/assets/cdc71af2-9f59-4fed-9b06-69396185c614)


**Obtained Output:**


![expa11](https://github.com/user-attachments/assets/593ae376-9769-4e79-bace-637f1192e6ff)

### Analyzing the current mirroring circuit by changing the w and L in same ratio.

**(a)L=180nm.**

WKT (w/L) ratio is 16.667.

Therefore for L=180nm the w=3um.

Mosfet M1: Id = 0.00027
Mosfet M2: Id = 0.00027

Mosfet M3: Id = 0.00027           

**(b)L=500nm.**

WKT(w/L) ratio is 16.667.

Therefore for L=500nm the w=8.334um.

Mosfet M1: Id = 0.00028

Mosfet M2: Id = 0.00028

Mosfet M3: Id = 0.000277         

**(c)L=1um.**

WKT (w/L) ratio is 16.667.

Therefore for L=1um the w=16.667um.


Mosfet M1: Id = 0.00028

Mosfet M2: Id = 0.00028
Mosfet M3: Id = 0.00027           


## Transient Analysis:

![expata](https://github.com/user-attachments/assets/184ad97a-3197-46eb-af30-e632dee73d62)




## AC Analysis:

![image](https://github.com/user-attachments/assets/b12cea30-c6c7-4774-b243-b67b23ebcb15)


The Expected gain in db of the circuit is 20db.But the obtained gain from the AC analysis(frequency response) is 22.16db.

Av (in dB):

Theory value = 20dB

Practical value = 22.16dB

Av (in V/V):

Theory value = 10

Practical value = 10.2


## DC Analysis:(for mirror ratio 1:2)

As we know It=Iref+Ix<br>
Therefore, for 1:2 ratio 2*Iref=Ix<br>
So,Iref=It/3<br>
It=P/Vdd<br>
It=1mW/1.8V<br>
It=0.555mA.<br>
Therefore,Iref=0.185mA.<br>

To obtain the current value according to the given ratio, the provided values of W/L for M1 is 6um/180nm , M2 is 6um/180nm, and M3 is 3um/180nm.<br>
Vin is selected in such a way that it should be in saturation region so the given Vin is 0.763V.<br>

![image](https://github.com/user-attachments/assets/fb07f2c3-fd23-4f6a-b96f-85647391048c)

![image](https://github.com/user-attachments/assets/ed9222d5-a885-46bd-a5ec-9c1af46c487b)




## Transient Analysis:

![image](https://github.com/user-attachments/assets/9ab42a09-4609-40e6-8c08-8a65b1d6e3aa)



## AC Analysis:


![image](https://github.com/user-attachments/assets/e9acaf5f-fe52-4e3b-9768-f46b30462251)



The Expected gain in db of the circuit is 21.34db.But the obtained gain from the AC analysis(frequency response) is 24.6db.

Av (in dB):

Theory value = 21.34dB

Practical value = 24.6dB

Av (in V/V):

Theory value = 10

Practical value = 11.68


### Inference:
The current mirror circuit works well, accurately copying the reference current with very little variation, even when the W/L ratio changes. As the W/L ratio is adjusted, the drain current (Id) stays almost the same, showing that the circuit is effectively replicating the current.

Regarding the amplifier's performance, the gain is a little higher than what theory predicted in both mirror ratios. This small difference is likely due to slight mismatches in transistor parameters or simulation errors.

When the mirror ratio is increased from 1:1 to 1:2, the gain increases as expected. However, this also reduces the bandwidth, dropping it from 2.267 GHz to 1.173 GHz.

Overall, the results are very close to what theory predicts, confirming that the simulation and circuit are working as expected.

---------------------------------------------------------------------------------------------   


# PART-B
## Aim
Design the differential amplifier using the same design specification as Experiment-3.
Perform DC analysis,trasient and AC analysis.

### DC Analysis:

![Screenshot 2025-03-23 232424](https://github.com/user-attachments/assets/f3a2e2ae-9cc1-46ba-8509-294e39deb6b1)

![expbdc](https://github.com/user-attachments/assets/b4196f93-5988-49c6-b2a3-0bc44e446f2e)



### Transient Analysis:

![expbta](https://github.com/user-attachments/assets/1484acd6-099b-4db9-b9f0-7236115f03ba)


### AC Analysis:



![image](https://github.com/user-attachments/assets/3b9e29f3-9baf-46d9-abe0-92999b9fb33b)
