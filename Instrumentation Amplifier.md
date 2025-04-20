# Instrumentation Amplifier 
Instrumentation Amplifier (IA) is a type of differential amplifier that has been optimized for high input impedance, precise gain, and excellent common-mode rejection. 
These characteristics make it ideal for accurately amplifying low-level signals from sensors and transducers, especially in noisy environments.

![image](https://github.com/user-attachments/assets/b4ce733f-bcd4-4f12-8de1-18e418f1cebd)

### Key Features:
- High input impedance: Prevents loading the signal source.
- Low output impedance: Can drive loads effectively.
- High Common-Mode Rejection Ratio (CMRR): Essential for rejecting noise and interference common to both inputs.
- Adjustable Gain: Usually controlled with a single resistor.

### Design Question:
Question Given : Design an Instrumentation amplifier using 3 op-amp configuration with the following constraints
R1=R3=10kΩ
R2=R4=20kΩ
R5=R6=10kΩ
Calculate Adm for RG=10Ω,100Ω,1kΩ,10kΩ,20kΩ
Find Acm and calculate CMRR for each case. Use LTspice simulator.

### Design Circuit:
![1](https://github.com/user-attachments/assets/bd5a89db-9532-466b-8b59-b0b6b8922d28)
For RG = 10Ω
- ADM = (R2 / R1) × [1 + 2 × (R5 / RG)]
- ADM = (20k / 10k) × [1 + 2 × (10k / 10)]
- ADM = 4002V/V

### Transient Analysis for Adm
![2](https://github.com/user-attachments/assets/0d0df437-b00f-4581-a587-72cd39322b9b)

For RG = 100Ω
- ADM = (R2 / R1) × [1 + 2 × (R5 / RG)]
- ADM = (20k / 10k) × [1 + 2 × (10k / 100)]
- ADM = 402V/V
  
For RG = 1kΩ
- ADM = (R2 / R1) × [1 + 2 × (R5 / RG)]
- ADM = (20k / 10k) × [1 + 2 × (10k / 1k)]
- ADM = 42V/V

For RG = 10kΩ
- ADM = (R2 / R1) × [1 + 2 × (R5 / RG)]
- ADM = (20k / 10k) × [1 + 2 × (10k / 10k)]
- ADM = 4V/V

For RG = 20kΩ
- ADM = (R2 / R1) × [1 + 2 × (R5 / RG)]
- ADM = (20k / 10k) × [1 + 2 × (10k / 20k)]
- ADM = 6V/V

### Transient Analysis for ACM:

![acm](https://github.com/user-attachments/assets/701bd58b-537b-494b-89b6-038da4ff6a94)

### Comparison Table:
|RG     |  ADM         |  ACM  |  CMRR |
|:----: |  :---------: |  :--: |:----: | 
|10     |  4002        | 48.2  | 38.38 | 
|100    |  402         | 48.2  | 18.42 | 
|1k     |  42          | 8.4   | 13.97 |
|10k    |  6           | 1.2   | 13.97 |
|20k    |  4           | 0.8   | 13.97 |

#### Inference
- CMRR increases with increase in ADM
– As ADM increases from 4 V/V to 4002 V/V, the CMRR improves from 13.97 to 38.38 dB.
- ACM kept constant in all circuits.
- Very high CMRR observed.
- RG value is inversely proportional to ADM.
