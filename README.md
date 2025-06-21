# Current-Mirrors
A current mirror is a basic analog circuit used to copy (or "mirror") a current from one branch of a circuit to another. In this repository discusses the design of various current mirror topologies including Basic Current Mirror, Cascode Current Mirror, Wide Swing Current Mirror etc.
## Key Specifications​
Key specifications for a current mirror focus on how accurately and reliably it replicates a reference current. Here are the most important ones:
- Current Transfer Accuracy
- Output Resistance (R<sub>out</sub>)
- Voltage Compliance
- Accuracy & Process Independence
- Temperature Dependence
- Power Supply Rejection Ratio (PSRR)
## Basic Current-Mirrors
<img align="left" width="25%" src="https://github.com/user-attachments/assets/1cb43c1d-5c74-4795-913d-3f913016fa96"> The structure consisting of M<sub>1</sub> and M<sub>2</sub> in this left figure is called a “current mirror.” For, assuming the $V_{TH_{1}} = V_{TH_{2}}$ and neglecting the channel-length modulation ($\lambda$) , we can write 

$I_{ref} = \frac{1}{2} \mu_n C_{ox} (\frac{W_{1}}{L_{1}}) \left( V_{GS} - V_{TH} \right)^2$ <br> 
$I_{out} = \frac{1}{2} \mu_n C_{ox} (\frac{W_{2}}{L_{2}}) \left( V_{GS} - V_{TH} \right)^2$ <br>

$\frac{I_{out}}{I_{ref}} = \frac{(\frac{W_{2}}{L_{2}})}{(\frac{W_{1}}{L_{1}})} I_{ref} $

By adjusting the dimensions of both transistors, we can achieve the same current, amplified or scaled down. The key advantage of this topology is its ability to accurately replicate the current, independent of process variations and temperature changes.
<br clear="left"/>
### Cadence Virtuoso Simulation of Basic Current Mirrors
<p align="center" width="100%">
    <img width="29%" src="https://github.com/user-attachments/assets/9acc7709-1258-4a7e-9606-4d4bc6fe5e49"> 
    <img width="33.3%" src="https://github.com/user-attachments/assets/e679934a-ca41-4ed7-a75e-271cfdc82d7e"> 
    <img width="36%" src="https://github.com/user-attachments/assets/0361b08b-6be6-4a59-b2ec-055dc5597d57" alt> 
  <em>Fig.01: (A) The Design Parameters, (B) DC Operating Points (C) Output Characteristics </em>
</p>

The drain current of $M_2$, will equal the current in $Q_1$, $I_{\text{REF}}$, at the value of $V_{\text{OUT}}$ that causes the two devices to have the same $V_{\text{DS}}$ that is,

$$
V_{\text{OUT}} = V_{\text{GS}}
$$
Certainly! Here are some well-explained **drawbacks of a simple current mirror**:

---

### ⚠️ **Drawbacks of a Simple Current Mirror**

1. ### **Low Output Impedance**

   * The simple current mirror uses a single transistor to mirror the output current.
   * This transistor behaves like a **current source**, but its output impedance is limited to the **output resistance $r_o$** of the MOSFET:

     $$
     r_o = \frac{1}{\lambda I_D}
     $$
   * A low output impedance means that the current mirror cannot maintain a constant current under varying load conditions or output voltages, reducing its accuracy as a current source.

2. ### **Threshold Voltage (V\textsubscript{TH}) Mismatch**

   * Current mirroring assumes the two transistors are **perfectly matched**, especially in threshold voltage $V_{TH}$.
   * In practice, **process variations** cause mismatch in $V_{TH}$, leading to **current mismatch** between the reference and output branches.
   * Even small $V_{TH}$ differences can cause significant current errors due to the exponential dependence in subthreshold or quadratic in saturation.

3. ### **Channel-Length Modulation**

   * The output current is also affected by **channel-length modulation** (modeled by λ), which is not compensated in a basic mirror.
   * As $V_{OUT}$ changes, $I_{OUT}$ slightly increases—this breaks the ideal current source behavior.

4. ### **Limited Output Voltage Swing**

   * For the output transistor to stay in saturation, $V_{OUT}$ must be greater than $V_{GS} - V_{TH}$.
   * This limits the **minimum output voltage**, reducing the available voltage swing, especially in low-voltage designs.

5. ### **No Temperature Compensation**

   * A simple current mirror is sensitive to temperature changes, which affect mobility, threshold voltage, and thus the mirrored current.
   * More advanced mirrors (e.g., Wilson or cascode) can offer better thermal stability.

---

### 🛠️ **Summary**

While simple current mirrors are compact and easy to implement, their **accuracy and performance are limited** due to low output impedance, transistor mismatch, and sensitivity to temperature and supply variations. For precision applications, **improved topologies** like **cascode**, **Wilson**, or **regulated mirrors** are preferred.

Let me know if you'd like this formatted for a report or LaTeX document!

This sentence uses `$` delimiters to show math inline: $\sqrt{3x-1}+(1+x)^2$This sentence uses `$` delimiters to show math inline: $\sqrt{3x-1}+(1+x)^2$
This sentence uses `$` delimiters to show math inline: $\sqrt{3x-1}+(1+x)^2$
This sentence uses `$` delimiters to show math inline: $\sqrt{3x-1}+(1+x)^2$
This sentence uses `$` delimiters to show math inline: $\sqrt{3x-1}+(1+x)^2$
This sentence uses `$` delimiters to show math inline: $\sqrt{3x-1}+(1+x)^2$
This sentence uses `$` delimiters to show math inline: $\sqrt{3x-1}+(1+x)^2$
This sentence uses `$` delimiters to show math inline: $\sqrt{3x-1}+(1+x)^2$
This sentence uses `$` delimiters to show math inline: $\sqrt{3x-1}+(1+x)^2$ 
## Basic Current-Mirrors 
