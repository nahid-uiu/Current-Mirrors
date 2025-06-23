# Current-Mirrors
A current mirror is a basic analog circuit used to copy (or "mirror") a current from one branch of a circuit to another. In this repository discusses the design of various current mirror topologies including Basic Current Mirror, Cascode Current Mirror, Wide Swing Current Mirror etc.
## Table of Contents
- [Key Specifications](#Key-Specifications)
- [Basic Current Mirrors](#Basic-Current-Mirrors)
## Key Specifications​
Key specifications for a current mirror focus on how accurately and reliably it replicates a reference current. Here are the most important ones:
- Current Transfer Accuracy
- Output Resistance (R<sub>out</sub>)
- Voltage Compliance
- Accuracy & Process Independence
- Temperature Dependence
- Power Supply Rejection Ratio (PSRR)
## Basic Current Mirrors
<img align="left" width="25%" src="https://github.com/user-attachments/assets/1cb43c1d-5c74-4795-913d-3f913016fa96"> The structure consisting of M<sub>1</sub> and M<sub>2</sub> in this left figure is called a “current mirror.” For, assuming the $V_{TH_{1}} = V_{TH_{2}}$ and neglecting the channel-length modulation ($\lambda$) , we can write 

$I_{ref} = \frac{1}{2} \mu_n C_{ox} (\frac{W_{1}}{L_{1}}) \left( V_{GS} - V_{TH} \right)^2$ <br> 
$I_{out} = \frac{1}{2} \mu_n C_{ox} (\frac{W_{2}}{L_{2}}) \left( V_{GS} - V_{TH} \right)^2$ <br>

$\frac{I_{out}}{I_{ref}} = \frac{(\frac{W_{2}}{L_{2}})}{(\frac{W_{1}}{L_{1}})} I_{ref} $

By adjusting the dimensions of both transistors, we can achieve the same current, amplified or scaled down. The key advantage of this topology is its ability to accurately replicate the current, independent of process variations and temperature changes. Also, The drain current of $M_2$, will equal the current in $M_1$, $I_{\text{REF}}$, at the value of $V_{\text{OUT}}$ that causes the two devices to have the same $V_{\text{DS}}$ that is, $V_{\text{OUT}} = V_{\text{GS}}$
<br clear="left"/>

### Cadence Virtuoso Simulation of Basic Current Mirrors
<p align="center" width="100%">
    <img width="29%" src="https://github.com/user-attachments/assets/9acc7709-1258-4a7e-9606-4d4bc6fe5e49"> 
    <img width="33.3%" src="https://github.com/user-attachments/assets/e679934a-ca41-4ed7-a75e-271cfdc82d7e"> 
    <img width="36%" src="https://github.com/user-attachments/assets/0361b08b-6be6-4a59-b2ec-055dc5597d57" alt> 
  <em>Fig.01: (A) The Design Parameters, (B) DC Operating Points (C) Output Characteristics </em>
</p>
The above current mirror shows that both transistors share the same gate-source voltage of 923.019 mV and have nearly identical drain currents of approximately 99.998 µA. This indicates accurate current mirroring, with a negligible difference of about 0.0001 µA between the reference and mirrored currents. The output resistance is about 114.49 kΩ.

### **Drawbacks of a Simple Current Mirror**

1. Low Output Impedance
2. Threshold Voltage ($V_{TH}$) Mismatch
3. Channel-Length Modulation
4. Limited Output Voltage Swing

## Cascode Current-Mirrors
<img align="left" width="27%" src="https://github.com/user-attachments/assets/4c2384b0-fbc4-4737-900b-ec20dfbeffd5"> To mitigate low resistance $(R_{OUT})$ and achieve lower current variation  $(\Delta I = \frac{\Delta V}{R_{OUT}})$ at the output of the current mirror, we can use a cascode architecture instead of the basic current mirror structure. In this case an appropriate bias voltage $V_b$ is required such that $V_x = V_y$ , ensuring that both $V_{DS_1}$ and $V_{DS_2}$ are equal, allowing the output current to match the reference current. As, $V_x = V_y$, $V_{DS_1}$ = $V_{DS_2}$, $V_{DS_2}$ = $V_{GS_1}$ we can write, 
$V_{GS_3} = V_{G_3} - V_{S_3} = V_{b} - V_{y}$ <br> 
$V_{b} = V_{GS_3}+V_{y}$ <br> 
$V_{b} = V_{GS_3}+V_{GS_1}$ <br>

<br clear="left"/>


<img align="left" width="25%" src="https://github.com/user-attachments/assets/d93af4d9-ae5e-469d-bbb9-0e3fa65c4720">


