# CMOS-Circuit-Design-Spice-Simulation-using-Sky130nm-technology

## 📚 Table Of Contents

### [NgspiceSky130-Day1-Basics of NMOS Drain Current Id vs Drain-to-source Voltage Vds](#ngspicesky130-day1-basics-of-nmos-drain-current-id-vs-drain-to-source-voltage-vds)
  - [Introduction to Circuit Design and Spice Simulations](#introduction-to-circuit-design-and-spice-simulations)
    - [L1 Why do we need SPICE simulations](#l1-why-do-we-need-spice-simulations)
    - [L2 Introduction to basic element in Circuit design - NMOS](#l2-introduction-to-basic-element-in-circuit-design---nmos)
    - [L3 Strong inversion and threshold voltage](#l3-strong-inversion-and-threshold-voltage)
    - [L4 Threshold voltage with positive substrate potential](#l4-threshold-voltage-with-positive-substrate-potential)
  - [NMOS resistive region and Saturation region of operation](#nmos-resistive-region-and-saturation-region-of-operation)
    - [L1 Resistive region of operation with small drain-source voltage](#l1-resistive-region-of-operation-with-small-drain-source-voltage)
    - [L2 Drift current theory](#l2-drift-current-theory)
    - [L3 Drain current model for Linear region of operation](#l3-drain-current-model-for-linear-region-of-operation)
    - [L4 SPICE conclusion to resistive operation](#l4-spice-conclusion-to-resistive-operation)
    - [L5 Pinch-off region condition](#l5-pinch-off-region-condition)
    - [L6 Drain current model for saturation region of operation](#l6-drain-current-model-for-saturation-region-of-operation)
  - [Introduction to SPICE](#introduction-to-spice)
    - [L1 Basic SPICE setup](#l1-basic-spice-setup)
    - [L2 Circuit description in SPICE syntax](#l2-circuit-description-in-spice-syntax)
    - [L3 Define Technology parameters](#l3-define-technology-parameters)
    - [L4 First SPICE simulation](#l4-first-spice-simulation)
    - [L5 SPICE lab with Sky130 models](#l5-spice-lab-with-sky130-models)

 ### [NgspiceSky130-Day2-Velocity saturation and basics of CMOS inverter VTC](#ngspicesky130-day2-velocity-saturation-and-basics-of-cmos-inverter-vtc)
  - [SPICE simulation for lower nodes and velocity saturation effect](#spice-simulation-for-lower-nodes-and-velocity-saturation-effect)
    - [L1 SPICE simulation for lower nodes](#l1-spice-simulation-for-lower-nodes)
    - [L2 Drain current vs gate voltage for long and short channel device](#l2-drain-current-vs-gate-voltage-for-long-and-short-channel-device)
    - [L3 Velocity saturation at lower and higher electric fields](#l3-velocity-saturation-at-lower-and-higher-electric-fields)
    - [L4 Velocity saturation ](#l4-velocity-saturation-drain-current-model)
    - [L5 Labs Sky130 Id Vgs](#l5-labs-sky130-id-vgs)
    - [L6 Labs Sky130 Vt](#l6-labs-sky130-vt)
  - [CMOS voltage transfer characteristics VTC](#cmos-voltage-transfer-characteristics-vtc)
    - [L1 MOSFET as a switch](#l1-mosfet-as-a-switch)
    - [L2 Introduction to standard MOS voltage current parameters](#l2-introduction-to-standard-mos-voltage-current-parameters)
    - [L3 PMOS / NMOS Drain Current vs Drain Voltage](#l3-pmos--nmos-drain-current-vs-drain-voltage)
    - [L4 Step 1 – Convert PMOS Gate-Source Voltage to VIN](#l4-step-1--convert-pmos-gate-source-voltage-to-vin)
    - [L5 Convert PMOS and NMOS drain-source-voltage to Vout](#l5-step-2--step-3--convert-pmos-and-nmos-drainsource-voltage-to-vout)
    - [L6 Merge PMOS-NMOS load curves and plot VTC](#l6-step-4--merge-pmos--nmos-load-curves-and-plot-vtc)

 ### [NgspiceSky130-Day3-CMOS switching threshold and dynamic simulations](#ngspicesky130-day3-cmos-switching-threshold-and-dynamic-simulations)
  - [Voltage transfer characteristics-SPICE simulations](#voltage-transfer-characteristics-spice-simulations)
    - [L1 SPICE deck creation for CMOS inverter](#l1-spice-deck-creation-for-cmos-inverter)
    - [L2 SPICE simulation for CMOS inverter](#l2-spice-simulation-for-cmos-inverter)
    - [L3 Labs Sky130 SPICE simulation for CMOS](#l3-labs-sky130-spice-simulation-for-cmos)
  - [Static behaviour evaluation-CMOS inverter robustness-Switching Threshold](#static-behaviour-evaluation-cmos-inverter-robustness-switching-threshold)
    - [L1 Switching Threshold, Vm](#l1-switching-threshold-vm)
    - [L2 Analytical expression of Vm as a function of (W/L)p and (W/L)n](#l2-analytical-expression-of-vm-as-a-function-of-wlp-and-wln)
    - [L3 Analytical expression of (W/L)p and (W/L)n as a function of Vm](#l3-analytical-expression-of-wlp-and-wln-as-a-function-of-vm)
    - [L4 Static and Dynamic simulation of CMOS inverter](#l4-static-and-dynamic-simulation-of-cmos-inverter)
    - [L5 Static and Dynamic simulation of CMOS inverter with increased PMOS width](#l5-static-and-dynamic-simulation-of-cmos-inverter-with-increased-pmos-width)
    - [L6 Applications of CMOS inverter in clock network and STA](#l6-applications-of-cmos-inverter-in-clock-network-and-sta)

 ### [NgspiceSky130-Day4-CMOS Noise Margin robustness evaluation](#ngspicesky130-day4-cmos-noise-margin-robustness-evaluation)
  - [Static behaviour evaluation-CMOS inverter robustness-Noise Margin](#static-behaviour-evaluation-cmos-inverter-robustness-noise-margin)
    - [L1 Introduction to Noise Margin](#l1-introduction-to-noise-margin)
    - [L2 Noise Margin voltage parameters](#l2-noise-margin-voltage-parameters)
    - [L3 Noise margin equation and summary](#l3-noise-margin-equation-and-summary)
    - [L4 Noise margin variation with respect to PMOS width](#l4-noise-margin-variation-with-respect-to-pmos-width)
    - [L5 Sky130 Noise margin labs](#l5-sky130-noise-margin-labs)

- [NgspiceSky130-Day5-CMOS power supply and device variation robustness evaluation](#ngspicesky130-day5-cmos-power-supply-and-device-variation-robustness-evaluation)
  - [Static behaviour evaluation-CMOS inverter robustness-Power supply variation](#static-behaviour-evaluation-cmos-inverter-robustness-power-supply-variation)
    - [L1 Smart SPICE Simulation for Power Supply Variations](#l1-smart-spice-simulation-for-power-supply-variations)
    - [L2 Advantages and disadvantages using low supply voltage](#l2-advantages-and-disadvantages-using-low-supply-voltage)
    - [L3 Sky130 Supply variation Labs](#l3-sky130-supply-variation-labs)
  - [Static behaviour evaluation-CMOS inverter robustness-Device variation](#static-behaviour-evaluation-cmos-inverter-robustness-device-variation)
    - [L1 Sources of variation Etching process](#l1-sources-of-variation--etching-process)
    - [L2 Sources of variation Oxide thickness](#l2-sources-of-variation--oxide-thickness)
    - [L3 Smart SPICE simulation for device variations](#l3-smart-spice-simulation-for-device-variations)
    - [L4 Conclusion](#l4-conclusion)
    - [L5 Sky130 device variations labs](#l5-sky130-device-variations-labs)


---

<br>


# NgspiceSky130-Day1-Basics of NMOS Drain Current Id vs Drain-to-source Voltage Vds

# Introduction to Circuit Design and Spice Simulations

# L1 Why do we need SPICE simulations?

This lecture introduces the fundamental connection between circuit design and SPICE simulations in VLSI. Circuit design focuses on how logic gates such as inverters, NAND, NOR, AND, etc., are physically implemented using specific arrangements of PMOS and NMOS transistors. For example, in a CMOS inverter, the PMOS is connected at the top to VDD and the NMOS at the bottom to VSS, with their gates tied together and drains connected to form the output. This specific configuration gives the inverter its logic functionality. However, designing the connection alone is not sufficient; we must also understand how the circuit behaves electrically, which is where SPICE simulations become essential. SPICE characterizes transistor behavior by modeling NMOS and PMOS I-V characteristics and generating output waveforms. These waveforms determine delay, and delay depends directly on transistor sizing (W/L ratio), since W/L controls drive current, which shapes the output transition and ultimately defines cell timing.

<p align="center">
  <img src="https://github.com/user-attachments/assets/1bc14eb2-9c7f-46fe-9df8-06d16fb0c258" />
</p>

The lecture then explains why SPICE is critical in real VLSI flows such as physical design, clock tree synthesis (CTS), timing closure, and static timing analysis (STA). Although SPICE is not directly visible in these flows, all timing values used in STA originate from SPICE-based characterization. Standard cell libraries contain delay tables indexed by input slew and output load capacitance. For different buffer types (e.g., CBUF1 vs CBUF2), delay tables differ because their transistor sizes (W/L ratios) differ, giving them different drive strengths. When performing timing analysis, the tool selects a delay by interpolating between table entries based on the actual input slew and load capacitance. However, these delay values are not arbitrary; they are generated by detailed SPICE characterization of each cell under multiple conditions. Therefore, SPICE forms the foundation of all delay modelling.

## Example

In the example discussed, the instructor explains that different buffer types (such as CBUF1 and CBUF2) have different delay behaviours because they are designed with different transistor sizes (different W/L ratios), resulting in different drive strengths. The delay of a buffer is not a fixed value; instead, it depends on two main parameters: input slew and output load capacitance. Input slew refers to how fast the input signal transitions, and output load refers to the total capacitance the buffer must drive, including fanout and wiring capacitance. These two parameters form a delay table, where rows represent input slew values and columns represent output load values. The intersection gives the delay for that specific condition. If the exact load or slew is not available in the table, interpolation is used to estimate the delay. Even if two buffers receive the same input slew and drive the same load, their delays can differ because their internal transistor sizing differs. The instructor emphasizes that these delay values are not arbitrary; they come from SPICE characterization of each cell under different slew and load conditions. Thus, SPICE simulations are the foundation for generating the delay tables used in timing analysis, and they ensure that the delay values used in static timing analysis accurately reflect real transistor-level behaviour.

<p align="center">
<img width="708" height="366" alt="image" src="https://github.com/user-attachments/assets/b3b673f2-4e89-4319-9881-299c2bfaf6af" />
<img width="655" height="367" alt="image" src="https://github.com/user-attachments/assets/6381f3df-e82b-4b95-92cc-0a1285a12dc8" />
</p>

## Conclusion

The lecture raises three critical questions: (1) Where do delay tables come from? — They come from SPICE characterization of transistor-level circuits. (2) Are these delay models accurate? — Accuracy must be verified by comparing STA-extracted delays with direct SPICE simulation results under identical conditions. (3) How do we trust STA results? — By validating that the characterization data (derived from SPICE) accurately reflects real transistor behaviour. Ultimately, understanding NMOS and PMOS device physics, their voltage-current characteristics, and how W/L sizing affects delay is necessary to understand the origin of timing libraries and ensure correct chip functionality before tape-out. The lecture concludes by transitioning to a detailed study of NMOS transistor characteristics as the foundation for SPICE-based delay modelling. <br>

---

# L2 Introduction to basic element in Circuit design - NMOS

This lecture explains the fundamental structure of an NMOS transistor and builds the foundation for understanding threshold voltage and SPICE modeling. An NMOS is a four-terminal device consisting of gate, source, drain, and body (or bulk). It is built on a p-type substrate, and the source and drain are formed using heavily doped n+ diffusion regions. Above the substrate lies a thin gate oxide layer, and on top of the oxide is a polysilicon or metal gate. Isolation regions are also present to electrically separate adjacent transistors so that the operation of one device does not affect another. While the body terminal is often not explicitly shown in simplified circuit symbols because it is usually grounded, it plays a very important role in determining the threshold voltage. Any potential applied to the body can modify the threshold voltage, which directly affects device behavior.

<p align="center">
<img width="602" height="268" alt="image" src="https://github.com/user-attachments/assets/9737419d-99b7-4b90-9b57-6fa56ab35e66" /> </p>

The PMOS transistor has a similar structure but is complementary to the NMOS. It is built on an n-type substrate with p+ source and drain regions. Apart from the doping differences, the general structure remains the same. Understanding this structural difference is important for CMOS design.

The most critical parameter governing transistor operation is the threshold voltage (Vₜ). Threshold voltage determines when a conducting channel forms between source and drain. In SPICE simulations, transistor behavior is represented through mathematical models, and threshold voltage is a key component of these models. Although the full SPICE model contains complex equations, conceptually threshold voltage can be viewed as a function of several physical and electrical parameters. Accurate modeling of Vₜ ensures that SPICE simulations correctly represent real transistor behavior.

<p align="center">
<img width="677" height="257" alt="image" src="https://github.com/user-attachments/assets/cee5ef2e-fb4b-4312-92d4-139f2e76d419" /> </p>

To understand threshold voltage formation, consider the case when the gate-to-source voltage (VGS) is zero and all terminals are grounded. In this condition, the NMOS contains two back-to-back PN junctions: one between source and body and another between drain and body. Since no bias is applied, both junctions are effectively off, resulting in very high resistance between source and drain. No conducting channel exists, and therefore no current flows. The transistor is in the OFF state.

When a small positive voltage is applied to the gate, the gate, oxide, and substrate form a capacitor structure. The gate acts as one plate, the substrate acts as the other plate, and the oxide serves as the dielectric. Applying a positive voltage charges the gate positively. Because the substrate is p-type and contains holes as majority carriers, the positive gate voltage repels these holes away from the surface region beneath the gate. As holes move deeper into the substrate, they leave behind negatively charged ions. This creates a depletion region under the gate. At this stage, although charge redistribution has begun, a conducting channel has not yet formed.

<p align="center">
<img width="672" height="258" alt="image" src="https://github.com/user-attachments/assets/cb5fb083-3d40-4d8d-9720-d09797cf7102" /> </p>

If the gate voltage is increased further, the depletion region widens, and more holes are pushed away. Eventually, the electric field becomes strong enough to attract electrons (minority carriers in the p-type substrate) toward the surface. When sufficient electrons accumulate, an inversion layer forms beneath the gate oxide. This inversion layer creates a continuous conducting path between the n+ source and n+ drain regions. The gate voltage at which this conducting channel is formed is defined as the threshold voltage. Once VGS exceeds Vₜ, the transistor turns ON and current can flow between source and drain.

Understanding this physical process is essential because SPICE models are built upon these device physics principles. The threshold voltage, channel formation mechanism, and charge behavior directly influence I–V characteristics, delay, and overall transistor performance. Since all timing libraries and delay models used in digital design ultimately originate from SPICE-based characterization, a strong understanding of NMOS structure and threshold voltage formation is fundamental to accurate circuit design and timing analysis.

---

# L3 Strong Inversion and Threshold Voltage

## Initial Condition – VGS = 0 (Cutoff Region)

<p align="center">
  <img width="1292" height="488" alt="image" src="https://github.com/user-attachments/assets/311990e5-b4a9-4071-ade6-ed13e3b31c2e" />
</p>

When **VGS = 0** and drain, source, and bulk are connected to ground, the source–body and drain–body form two PN junction diodes. Since no bias is applied, both junctions are OFF.  

Therefore, the **source-to-drain resistance is very high**, and no current flows.  
The MOSFET operates in the **cutoff region**.

## Formation of Depletion Region

<p align="center">
  <img width="1282" height="481" alt="image" src="https://github.com/user-attachments/assets/ad2085f2-e233-4db5-ae60-4cf4c7466d30" />
</p>

When a small positive **VGS** is applied, the gate becomes positively charged.  
This repels holes (majority carriers in the p-substrate) away from the surface.  

As holes move deeper into the substrate, negative charge remains near the surface, forming a **depletion region**, similar to a reverse-biased PN junction diode.

## Increasing Gate Voltage – Surface Inversion Begins

<p align="center">
 <img width="830" height="483" alt="image" src="https://github.com/user-attachments/assets/920012a3-1082-41f8-a5da-f3de455427dc" />
</p>

As **VGS** increases further, the depletion region widens.  

Eventually, the electric field becomes strong enough to attract electrons (minority carriers) toward the surface.  
The semiconductor surface begins to behave like **n-type material**.

## Strong Inversion and Threshold Voltage (Vₜ)

<p align="center">
  <img width="1281" height="482" alt="image" src="https://github.com/user-attachments/assets/ba7f0a44-4e81-4218-9a80-5adafa64dae2" />
</p>

When the surface is fully inverted and a thin n-type layer forms beneath the gate oxide, the device reaches **strong inversion**.  

The gate voltage at which strong inversion occurs is defined as the:

> ### **Threshold Voltage (Vₜ)**

This voltage determines when the MOSFET turns ON and forms the foundation of SPICE modeling.

## Increasing VGS Beyond Threshold

<p align="center">
  <img width="1281" height="471" alt="image" src="https://github.com/user-attachments/assets/a7cba5be-0e80-45c0-bc50-1cf6649a08d4" />
</p>

After threshold is reached:

- The depletion width does **not increase significantly**
- The region is already depleted of majority carriers
- Additional gate voltage increases **inversion charge density**

## Electron Attraction from n+ Source

<p align="center">
  <img width="598" height="470" alt="image" src="https://github.com/user-attachments/assets/4fc44052-0988-4904-93b7-ad0df55ad515" />
</p>

When VGS increases beyond Vₜ, electrons are drawn from the heavily doped **n+ source region** into the area under the gate.  

This strengthens the inversion layer and increases channel charge.

## Continuous n-Channel Formation

<p align="center">
 <img width="1297" height="605" alt="image" src="https://github.com/user-attachments/assets/92d4c137-1887-44f1-a4bd-afc199624af8" />
</p>

Once sufficient electrons accumulate, a **continuous n-type channel** forms between source and drain.  

The conductivity of this channel is controlled by **VGS**.  

Current will flow only when a drain voltage is applied.

## Case 1: VSB = 0

<p align="center">
  <img width="536" height="477" alt="image" src="https://github.com/user-attachments/assets/269a4ba3-0b9c-44c6-8493-1604815f415f" />
</p>

When source and body are at the same potential:

- No additional reverse bias exists
- Depletion width is normal
- Threshold voltage is at nominal value

## Case 2: VSB > 0

<p align="center">
 <img width="647" height="453" alt="image" src="https://github.com/user-attachments/assets/a2dcf7a2-fc18-4d3c-ae0b-76f94e3353a9" />
</p>

When a positive voltage is applied between source and body:

- The source–body PN junction becomes more reverse biased
- Depletion region width increases near the source

## Additional Reverse Bias Effect

<p align="center">
  <img width="1175" height="542" alt="image" src="https://github.com/user-attachments/assets/dd2a5b07-beef-4a4e-afa0-20d30efb2eb0" />
</p>

The additional reverse bias makes inversion harder to achieve because:

- A larger depletion region must be overcome
- More gate voltage is required


## Depletion Width Increases Near Source

<p align="center">
 <img width="1212" height="582" alt="image" src="https://github.com/user-attachments/assets/098eff6e-9fdb-4bb6-952d-2e4db412f7a3" />
</p>

The depletion layer near the source becomes slightly larger compared to the VSB = 0 case.  

Therefore, inversion is delayed.

---

# L4 Threshold voltage with positive substrate potential

## Comparing Two Cases: VSB = 0 and VSB > 0

<p align="center">
  <img width="680" height="321" alt="image" src="https://github.com/user-attachments/assets/569f37d4-d52a-45a0-892c-71f21319728c" />
</p>

We consider two scenarios:

- Case 1: VSB = 0  
- Case 2: VSB > 0  

In both cases, the gate-to-source voltage (VGS) is increased gradually.  
The depletion width increases in both scenarios.  

However, a key difference appears when VSB is positive.


## Effect of Positive VSB on Charge Distribution

<p align="center">
 <img width="613" height="262" alt="image" src="https://github.com/user-attachments/assets/ed4638e0-6360-414a-8a8b-82b4b9ee0dd8" />
</p>

When VSB is positive, the source is at a higher potential relative to the body.  
This creates additional reverse bias across the source–body PN junction.

As negative charges accumulate under the gate due to increasing VGS,  
the positive source terminal attracts some of these charges toward itself.

In the VSB = 0 case, charges simply accumulate under the gate region.

This causes inversion to be delayed when VSB > 0.


## Surface Inversion Comparison

<p align="center">
  <img width="627" height="257" alt="image" src="https://github.com/user-attachments/assets/449ad035-648f-416d-a07e-a0a974fe297e" />
</p>

As VGS increases:

- Inversion occurs earlier when VSB = 0  
- Inversion is delayed when VSB > 0  

At the same VGS value, the device without body bias may already show strong inversion,  
while the device with positive VSB has not yet fully inverted.


## Definition of VTO (Threshold Voltage at VSB = 0)

<p align="center">
  <img width="647" height="317" alt="image" src="https://github.com/user-attachments/assets/343099b0-b525-4660-9fa8-cca860d2b8ac" />
</p>

**VTO** is defined as the threshold voltage when VSB = 0.

At:

- VGS = VTO → Strong inversion occurs when VSB = 0  
- The same VGS does not produce inversion when VSB > 0
- 

## Additional Gate Voltage Required (VTO + V1)

<p align="center">
<img width="680" height="316" alt="image" src="https://github.com/user-attachments/assets/cdda03c0-90f7-4f45-b576-6f0fd469d4a1" />
</p>

When VSB is positive, additional gate voltage is required to achieve inversion.

If:

- VGS = VTO → inversion only when VSB = 0  
- VGS = VTO + V1 → inversion when VSB > 0  

An extra voltage **V1** is required due to body bias.


## Conclusion: 

<p align="center">
  <img width="680" height="364" alt="image" src="https://github.com/user-attachments/assets/3149b3e0-bc04-4dfb-9794-8ec8f973b1db" />
</p>

In the presence of substrate bias VSB:

- Strong inversion requires additional gate voltage  
- Threshold voltage increases  


## Threshold Voltage Equation

<p align="center">
  <img width="678" height="302" alt="image" src="https://github.com/user-attachments/assets/563a39cd-6dd7-4601-9871-d919c2db2767" />
</p>
- Vto = Threshold voltage at Vsb = 0, and is a function of manufacturing process.


## Body Effect Coefficient (γ)

<p align="center">
  <img width="222" height="117" alt="image" src="https://github.com/user-attachments/assets/8eae9769-4617-4d54-bc37-7f1b6b0a9dd3" />
      </p>

γ (Gamma) is called the **Body Effect Coefficient**.

It represents how strongly VSB influences the threshold voltage.

Gamma depends on:

- Substrate doping concentration (NA)  
- Oxide capacitance (Cox)  
- Relative permittivity of Si = 11.7
- Electron charge (q)   

These parameters are technology-dependent and provided by the foundry.


## Fermi Potential (ΦF)

<p align="center">
  <img width="270" height="76" alt="image" src="https://github.com/user-attachments/assets/f0fa453f-9270-48ee-86ba-a3c1f31e56db" />
</p>

The Fermi potential (ΦF) appears in the threshold voltage equation.

---

<br>

# NMOS resistive region and Saturation region of operation

# L1 Resistive region of operation with small drain-source voltage

## Three Modes of Operation

<p align="center">
 <img width="652" height="247" alt="image" src="https://github.com/user-attachments/assets/61555aa1-95e0-4e67-8621-2d1d447da8ec" />
</p>

The MOSFET operates in three regions:

- Cutoff region  
- Resistive (Linear) region  
- Saturation region  

Previous discussions focused on the cutoff region, where strong inversion occurs at VGS = VT.  
This section begins the discussion of the resistive (linear) region.


## Threshold Voltage Recap

<p align="center">
<img width="670" height="261" alt="image" src="https://github.com/user-attachments/assets/c98efddf-f63f-4f7a-810e-c126b0e9ea4a" />
</p>

At VGS = VT, strong inversion occurs and the semiconductor surface becomes n-type.  

When VGS > VT:

- More charge carriers are induced  
- Channel width increases  
- Conducting path between source and drain strengthens  


## Effective Channel Length

<p align="center">
  <img width="403" height="321" alt="image" src="https://github.com/user-attachments/assets/005be098-892a-45b3-819b-0030fd7e0eb1" />
</p>

Due to fabrication techniques, the effective channel length is smaller than the designed channel length.

For example:

- Designed channel length may be 100 nm  
- Effective channel length may be smaller  

For simplicity in this discussion, the effective channel length is assumed to be L.


## Channel Representation Along x-Axis

<p align="center">
  <img width="662" height="303" alt="image" src="https://github.com/user-attachments/assets/04f4f7b6-e02c-4daa-affd-85f79036641f" />
</p>

The channel is represented from:

- x = 0 (source)  
- x = L (drain)  

At every point along the channel, the voltage can be different once VDS is applied.


## Induced Charge and Gate Voltage Relationship

As VGS increases:

- Channel width increases  
- Induced charge increases  
- Conducting region expands  

The induced charge in the channel is proportional to:

VGS − VT  

Only the portion of VGS greater than VT contributes to channel formation.


## Applying Small Drain-to-Source Voltage (VDS)

<p align="center">
  <img width="422" height="318" alt="image" src="https://github.com/user-attachments/assets/917eefc4-388d-4853-b1e1-a1cc607a4fba" />
</p>

Now a small drain-to-source voltage is applied.

Example values used:

- VGS = 1 V  
- VDS = 0.05 V (50 mV)  

VDS is kept very small initially.  

## Voltage is No Longer Constant Across the Channel

<p align="center">
  <img width="422" height="318" alt="image" src="https://github.com/user-attachments/assets/4c697de7-1a51-4dc5-9620-610d6baedc49" />
</p>

In the absence of VDS, the channel voltage is constant.

Once VDS is applied:

- A voltage gradient appears  
- Voltage varies along the channel  

At different positions:

- At source end → V(x) ≈ 0  
- At drain end → V(x) ≈ VDS  
- Intermediate points → Voltage lies between 0 and VDS  

This is an important observation.

## Gate-to-Channel Voltage Variation

<p align="center">
  <img width="421" height="330" alt="image" src="https://github.com/user-attachments/assets/534aca29-ebf4-463f-a657-c79f11b67d24" />
</p>

With VDS applied, the effective gate-to-channel voltage at any point x becomes:

VGS − V(x)

Because:

- V(x) = 0 at source  
- V(x) = VDS at drain  
- V(x) varies continuously along channel  

Therefore, channel charge varies along the channel length.

## Transition to Drain Current Derivation

Because V(x) varies across the channel:

- Induced charge varies  
- Current will vary along the channel  

The drain current equation will be derived next.

The drain current equation:

- Drives transistor behavior  
- Determines delay  
- Is used in simulations and circuit design  

The derivation in the resistive region will continue in the next discussion.

---

# L2 Drift Current Theory

## Definition of V(x) Along the Channel

<p align="center">
  <img width="682" height="318" alt="image" src="https://github.com/user-attachments/assets/4908d633-8758-4df2-b903-d993cca1da8d" />
</p>

In the previous discussion, the term **V(x)** was introduced.

V(x) represents the voltage at each point along the channel (x-axis).

- At x = 0 → V(0) = 0 V  
- At x = L → V(L) = VDS  

Thus, voltage varies from source to drain.


## Effective Channel Voltage (VGS − V(x))

Because VGS is applied at the gate, the effective channel voltage at any point becomes:

### **VGS − V(x)**

Example:

If:
- VGS = 1 V  
- V(0) = 0 V  

Effective voltage at source = 1 − 0 = 1 V  

If:
- VGS = 1 V  
- V(L) = VDS = 0.05 V  

Effective voltage at drain = 1 − 0.05 = 0.95 V  

So the channel voltage lies between **1 V and 0.95 V**.


## Voltage Gradient Across the Channel

Because V(x) changes from 0 to VDS:

- Channel voltage is not constant  
- A voltage gradient exists  

If VDS were grounded, the channel voltage would be constant.  
With VDS applied, it gradually decreases from source to drain.


## Induced Charge in Presence of VDS

<p align="center">
  <img width="672" height="323" alt="image" src="https://github.com/user-attachments/assets/a7f82b30-55e3-4d94-afb3-0cbf46e7a97f" />
</p>

The induced charge at each point depends on:

### **VGS − V(x) − VT**

Since VT is the threshold voltage that turns on the transistor, it must be subtracted.

Thus, induced charge varies along the channel.


## Charge Equation (Q = C × V)

<p align="center">
  <img width="673" height="317" alt="image" src="https://github.com/user-attachments/assets/f0297e8d-82e5-4add-be53-e8246784379d" />
</p>

Using the charge relation:

### **Q = C × V**

The induced charge at each point becomes:

### **Q(x) = Cox (VGS − V(x) − VT)**

Where:

Cox = Gate oxide capacitance  
Cox = εox / tox  

These are constants for a given technology.


## Oxide Capacitance Parameters

<p align="center">
  <img width="661" height="318" alt="image" src="https://github.com/user-attachments/assets/2c3fbed5-59f4-43e4-9ba2-d3c7dd294a3d" />
</p>

Cox depends on:

- εox (oxide permittivity)  
- tox (oxide thickness)  

εox = 3.97 × ε₀  
tox = Gate oxide thickness  

The oxide lies between:

- Gate  
- p-type substrate  

These are technology constants from the foundry.


## Two Types of Currents in Device Physics

<p align="center">
  <img width="675" height="316" alt="image" src="https://github.com/user-attachments/assets/4af8ca1c-3801-4fca-bd2b-028e81419fb2" />
</p>

Two types of currents exist:

### (a) Drift Current  
Current due to potential difference between two points.

### (b) Diffusion Current  
Current due to difference in carrier concentration.

Analogy used:

- One tank filled with water  
- One tank empty  
- Water flows due to difference in water levels  

Similarly, diffusion current flows due to difference in carrier concentration.


## Current Considered in This Discussion

<p align="center">
  <img width="647" height="318" alt="image" src="https://github.com/user-attachments/assets/0c0773bd-7e66-4247-a590-1baa1087b833" />
</p>

This discussion focuses on **drift current**.

Because:

- Source = 0 V  
- Drain = VDS  

There is a potential difference.

Therefore, current flowing from source to drain is drift current.

Diffusion current related to PN junction behavior will be discussed separately.


## Definition of Drift Current

<p align="center">
  <img width="682" height="317" alt="image" src="https://github.com/user-attachments/assets/672f1957-6c27-4fdd-9964-aa4aaae28667" />
</p>

Drift current is defined as:

### **Velocity of charge carriers × Available charge**

This happens over a certain area — the channel width.


## Channel Width (Top View Perspective)

<p align="center">
  <img width="646" height="367" alt="image" src="https://github.com/user-attachments/assets/03e3bd33-e946-4ab5-8cab-1973bc5acc3f" />
</p>

From the side view, only channel length is visible.

From the top view:

- Gate appears rectangular  
- Source and drain are visible  
- Channel lies between them  
- Gate overlaps source and drain  

Current flows across the complete channel width.


## Current as Function of Area

Current depends on:

- Carrier velocity  
- Available charge  
- Channel width  

To derive the drain current equation:

- Substitute velocity expression  
- Substitute charge expression  
- Integrate across the channel  

---

# L3 Drain current model for linear region of operation

## Objective of Derivation

<p align="center">
  <img width="235" height="293" alt="image" src="https://github.com/user-attachments/assets/9f758ec3-e3d5-4422-be32-65a4235dc9d3" />
</p>

Previously, drain current was identified as:

**Drain Current = Velocity of charge carriers × Available charge × Channel width**

Now the goal is to derive a mathematical model for I<sub>D</sub> that can be used by an engine.

SPICE already has complicated and accurate models.  
Here, we derive a simple working model to understand the basics behind SPICE simulations.


## Drain Current Expression Setup

Drain current is expressed as:

- Velocity → v<sub>n</sub>(x)  
- Induced charge → q<sub>i</sub>(x)

So,

I<sub>D</sub> = v<sub>n</sub>(x) × q<sub>i</sub>(x) × W

Where:
- W = channel width


## Velocity Expression

Velocity is defined as:

v<sub>n</sub>(x) = μ<sub>n</sub> (dV/dx)

Where:
- μ<sub>n</sub> = mobility  
- dV/dx = electric field  

Since there is a voltage gradient along the channel, velocity is proportional to the electric field.


## Induced Charge Expression

<p align="center">
  <img width="225" height="292" alt="image" src="https://github.com/user-attachments/assets/9e655fe6-9483-4699-8f4f-40bad2b1a8dd" />
</p>

Previously derived:

q<sub>i</sub>(x) = C<sub>ox</sub> (V<sub>GS</sub> − V(x) − V<sub>T</sub>)

Where:

C<sub>ox</sub> = ε<sub>ox</sub> / t<sub>ox</sub>

These are technology constants.


## Substitution into Drain Current

<p align="center">
  <img width="242" height="357" alt="image" src="https://github.com/user-attachments/assets/f5b0a66a-f964-4954-8e9d-bbf9e79f1879" />
</p>

Substitute:

v<sub>n</sub>(x) = μ<sub>n</sub> (dV/dx)

q<sub>i</sub>(x) = C<sub>ox</sub> (V<sub>GS</sub> − V(x) − V<sub>T</sub>)

Multiply by W and integrate across the channel length.


## Integration Limits

Integration conditions:

- dx from 0 to L  
- dV from 0 to V<sub>DS</sub>  

Voltage varies from source to drain.


## Result After Integration

<p align="center">
<img width="242" height="263" alt="image" src="https://github.com/user-attachments/assets/f952a453-bf69-41a7-a168-fbc71aed3797" />
</p>

After integration:

I<sub>D</sub> = μ<sub>n</sub> C<sub>ox</sub> (W/L)  
[(V<sub>GS</sub> − V<sub>T</sub>) V<sub>DS</sub> − V<sub>DS</sub><sup>2</sup> / 2]

Where:

- μ<sub>n</sub>  
- C<sub>ox</sub>  
- W  
- L  

are technology constants.

These form part of the model parameters in SPICE.


## Process Transconductance Parameter

<p align="center">
<img width="248" height="340" alt="image" src="https://github.com/user-attachments/assets/ce21fe61-aab8-4886-93d2-fec73dc4b5fe" />
</p>

Define:

k'<sub>n</sub> = μ<sub>n</sub> C<sub>ox</sub>

This is the process transconductance parameter.

Then define:

k<sub>n</sub> = k'<sub>n</sub> (W/L)

This is called the gain factor.

The drain current becomes:

I<sub>D</sub> = k<sub>n</sub>  
[(V<sub>GS</sub> − V<sub>T</sub>) V<sub>DS</sub> − V<sub>DS</sub><sup>2</sup> / 2]

## Observation: Quadratic Term in VDS

The equation contains:

V<sub>DS</sub><sup>2</sup> / 2

So I<sub>D</sub> is quadratic in V<sub>DS</sub>.

But this applies when V<sub>DS</sub> is small.


## Numerical Example

<p align="center">
  <img width="645" height="361" alt="image" src="https://github.com/user-attachments/assets/a6238142-c831-405c-a324-7964268ad63d" />
</p>

Given:

- V<sub>GS</sub> = 1 V  
- V<sub>T</sub> = 0.45 V  
- V<sub>DS</sub> = 0.05 V  

Compute:

(V<sub>GS</sub> − V<sub>T</sub>) = 0.55  

(V<sub>GS</sub> − V<sub>T</sub>) V<sub>DS</sub> = 0.0275  

V<sub>DS</sub><sup>2</sup> / 2 = 0.00125  

The second term is very small compared to the first.


## Linear Region Condition

For:

V<sub>DS</sub> < (V<sub>GS</sub> − V<sub>T</sub>)

The term:

V<sub>DS</sub><sup>2</sup> / 2

can be neglected.

Then:

I<sub>D</sub> ≈ k<sub>n</sub> (V<sub>GS</sub> − V<sub>T</sub>) V<sub>DS</sub>

Now I<sub>D</sub> becomes linear in V<sub>DS</sub>.

This defines the **linear (resistive) region of operation**.


## Final Linear Region Model

<p align="center">
 <img width="666" height="363" alt="image" src="https://github.com/user-attachments/assets/087dfb7f-4de5-470f-b19c-f726fc6f8d3a" />
</p>

For:

V<sub>DS</sub> < (V<sub>GS</sub> − V<sub>T</sub>)

The drain current model is:

I<sub>D</sub> = k<sub>n</sub> (V<sub>GS</sub> − V<sub>T</sub>) V<sub>DS</sub>

---

# L4 SPICE conclusion to resistive operation

## Linear Region Condition

<p align="center">
<img width="1252" height="682" alt="image" src="https://github.com/user-attachments/assets/c3c2a4d2-f2f5-4e9d-ac2f-bfb50310ac89" />
</p>

We are at a point where the drain current is a linear function of VDS.

The condition for linear mode of operation is:

VDS ≤ VGS − VT  

When this condition is satisfied, the device operates in the linear region.

The drain current equation in this region is:

Id ∝ (VGS − VT) · VDS  

## Objective

We need to study:

- Effect of varying VGS  
- Effect of varying VDS  
- Impact on drain current  

There are applications operating at:

- Lower VGS  
- Higher VGS  

So we must simulate device behavior across different voltage levels.

## VGS Sweep

<p align="center">
<img width="743" height="423" alt="image" src="https://github.com/user-attachments/assets/5ce884b9-dbce-4e79-83b6-7c85fa589fea" /> </p>

Sweep VGS from 0 to 2.5 V in steps of 0.5 V:

- 0.5 V  
- 1.0 V  
- 1.5 V  
- 2.0 V  
- 2.5 V  

For each VGS value, determine allowable VDS range such that:

VDS ≤ VGS − VT  

## Corresponding VDS Sweep Ranges

<p align="center">
<img width="521" height="138" alt="image" src="https://github.com/user-attachments/assets/204082fd-dbd5-4f13-a0d4-41508060f34c" />
<img width="520" height="140" alt="image" src="https://github.com/user-attachments/assets/96ec9153-8a13-4333-a766-8f48a0b9ea51" />
<img width="508" height="138" alt="image" src="https://github.com/user-attachments/assets/938a210e-0395-4f70-8a51-b4d7d65c79a1" />
<img width="526" height="131" alt="image" src="https://github.com/user-attachments/assets/70db48b3-b276-4af0-aa19-9e42b47eafb6" />
</p>

For each VGS:

- VGS = 0.5 V → VDS: 0 to 0.05 V  
- VGS = 1.0 V → VDS: 0 to 0.55 V  
- VGS = 1.5 V → VDS: 0 to 1.05 V  
- VGS = 2.0 V → VDS: 0 to 1.55 V  
- VGS = 2.5 V → VDS: 0 to 2.05 V  

At every VGS value, VDS must be swept only up to (VGS − VT) to keep the device in linear region.

## Challenge

Manually calculating drain current for:

- All VGS values  
- All corresponding VDS values  

is not feasible.

We require:

- Accurate models  
- Automated computation  

## Solution: SPICE Simulation

We can:

- Provide sweep conditions for VGS  
- Sweep VDS from 0 to (VGS − VT)  
- Obtain drain current characteristics  

SPICE engine performs:

- Accurate current calculations  
- Automated sweeping  
- Waveform generation  

## Important Question

What happens when:

VDS > VGS − VT ?

In this case, the device enters the saturation region of operation.

---

# L5 Pinch-Off Region Condition

## Sweeping VDS

<p align="center">
<img width="1112" height="607" alt="image" src="https://github.com/user-attachments/assets/133c40e1-d2b5-480b-b374-f3e969f30c52" />
</p>

Now:

- VGS is kept constant at 1 V  
- VT is kept constant at 0.45 V  
- VDS is increased from 0.05 V to 0.95 V  
  in steps of 0.1 V  

This sweep could be fed directly into a SPICE engine.

But before simulations, the physical concept must be understood.


## Linear Region Behavior 

<p align="center">
<img width="1260" height="620" alt="image" src="https://github.com/user-attachments/assets/64c1c298-daa4-40b2-b2fe-71e815a2a946" />
</p>

As VDS increases from:

0.05 → 0.45 V

The channel voltage:

VGS − VDS

takes values:

- 0.95 V  
- 0.85 V  
- 0.75 V  
- 0.65 V  
- 0.55 V  

All of these are greater than VT (0.45 V).

Therefore:

- Channel exists
- Surface inversion is maintained
- Device operates in linear region


## Critical Condition: VDS = 0.55 V

<p align="center">
<img width="1208" height="591" alt="image" src="https://github.com/user-attachments/assets/24237e50-417c-4fd8-a066-5f7fa152b518" />
</p>

When:

VDS = 0.55 V

<p align="center">
<img width="1220" height="577" alt="image" src="https://github.com/user-attachments/assets/dbbce28d-601e-436e-8523-502719c01df4" /> </p>

Channel voltage becomes:

VGS − VDS = 1 − 0.55 = 0.45 V

Now:

Channel Voltage = VT

At this exact point:

- Surface inversion just happens at the drain end
- One end of channel is at threshold
- Other end (near source) is still greater than threshold

This creates a mixed condition:

- Near source → inversion already exists  
- Near drain → inversion just disappears  


## Beginning of Channel Disappearance

<p align="center">
<img width="1230" height="586" alt="image" src="https://github.com/user-attachments/assets/4548c733-ce9c-495c-b059-86cba4e6427b" />
</p>

Since channel voltage no longer satisfies:

VGS − VDS > VT

The channel begins to disappear near the drain region.

The channel still exists near the source.


## Does Current Stop?

No.

Even though the channel begins to disappear near the drain:

- There is still potential difference between source and drain
- Current still flows

However:

- The linearity of current changes
- Behavior transitions from linear region


## When VDS Increases Further

<p align="center">
<img width="656" height="308" alt="image" src="https://github.com/user-attachments/assets/bc86950b-baca-4d95-843c-a0d2cdafeaa2" />
</p>

If VDS increases further:

0.65 V  
0.75 V  
0.85 V  
0.95 V  

Then:

VGS − VDS < VT

In this condition:

- No channel near drain
- Channel exists only near source
- Drain-end channel completely disappears


## Saturation Region Condition

This condition is referred to as:

**Saturation Region**

Pinch-off occurs when:

VGS − VDS ≤ VT

This means:

The device enters saturation region.

From this point onward:

- Channel near drain vanishes
- Device behavior changes

---

# L6 Drain current model for saturation region of operation

## When VDS Increases Beyond Limit

When VDS is increased to such an extent that:

VGS − VDS < VT

the channel begins to disappear near the drain.

This creates a contradiction compared to the linear region.


## Contradiction Between Linear and Pinch-Off Region

In the linear region:

Channel voltage = VGS − VDS  
and the transistor operates normally.

But when:

VGS − VDS < VT

the channel is no longer valid near the drain.

Only a small channel beneath the gate near the source remains.


## Channel Voltage Behavior in Saturation

<p align="center">
  <img width="663" height="331" alt="image" src="https://github.com/user-attachments/assets/85f4fa66-8be9-4c45-be5d-0537ec93f0c4" />
</p>

In the saturation region:

Channel voltage remains approximately constant.

It becomes:

VGS − VT

It is no longer dependent on VDS the way it was in the linear region.

This is the important difference between linear and saturation region.


## Revisiting Linear Region Equation

Previously derived linear region equation:

I<sub>D</sub> = k<sub>n</sub> (VGS − VT) VDS − (k<sub>n</sub> / 2) VDS²

For small VDS:

The VDS² term was neglected.

This made drain current linear in VDS.


## Replacing Channel Voltage in Saturation

<p align="center">
<img width="681" height="342" alt="image" src="https://github.com/user-attachments/assets/28e5eb63-1db7-49e7-898f-bfe3441bfffe" /> </p>

In saturation:

Channel voltage becomes constant:

VGS − VT

So in the drain current equation:

VDS is replaced by VGS − VT

Because:

Channel voltage = Drain-to-source voltage  
And in saturation, it is fixed at VGS − VT


## Saturation Drain Current Equation

<p align="center">
<img width="151" height="42" alt="image" src="https://github.com/user-attachments/assets/90b8f1bd-9bd1-4101-919c-aeecf3a2e527" /> </p>

After substitution:

I<sub>D</sub> = (k<sub>n</sub> / 2) (VGS − VT)²

This is the drain current equation in the saturation region.

It is no longer a linear function of VDS.


## Constant Current Behavior

<p align="center">
  <img width="622" height="251" alt="image" src="https://github.com/user-attachments/assets/b3d1b5dd-e5be-4dce-a547-60529d8b47c8" />
    </p>
  
If:

- VT is constant  
- VGS is constant  

Then:

I<sub>D</sub> becomes constant.

As VDS increases further beyond pinch-off:

Drain current remains approximately constant.

This makes the MOSFET appear like a constant current source in saturation.


## Revisiting k<sub>n</sub> Expression

k<sub>n</sub> = k'<sub>n</sub> (W / L)

From this equation:

It appears that reducing channel length L increases drain current.

However, this is not always true.


## Effective Channel Length Modulation

<p align="center">
  <img width="655" height="337" alt="image" src="https://github.com/user-attachments/assets/2bd99e07-9de6-4dc6-b48f-700b5b780e65" />
</p>

Although channel voltage becomes constant:

The effective channel length is still modulated by VDS.

As VDS increases further:

- Effective channel length reduces  
- Depletion region at drain increases 

There exists a channel length modulation factor that can be added to the equation for completeness.

---

<br>

# Introduction to SPICE

# L1 Basic SPICE Setup

## Feeding Models to SPICE Engine

<p align="center">
<img width="631" height="292" alt="image" src="https://github.com/user-attachments/assets/a0b62562-29c1-4512-8a94-dd146128542e" /> </p>


Now the next part is to feed the derived models correctly into the SPICE engine so that it understands them and evaluates the drain current equations as expected.

Previously, we worked with:

- The MOSFET structure  
- Applied VDS  
- Applied VGS  
- Grounded source and substrate  

We also derived model equations:

- Threshold voltage equation  
- Linear region drain current equation  
- Saturation region drain current equation  

These represent the MOSFET behavior.

## Linear Region Model Review

<p align="center">
<img width="167" height="60" alt="image" src="https://github.com/user-attachments/assets/ec39eb2b-5fff-4ee8-9865-f5284e442e92" /> </p>

In hand calculations, we ignored the term:

VDS² / 2

because VDS was assumed small.

That allowed us to approximate drain current as a linear function of VDS.

However, in SPICE:

We do not ignore terms manually.

The engine handles full expressions for better accuracy.


## Saturation Region Model Review

<p align="center">
<img width="206" height="61" alt="image" src="https://github.com/user-attachments/assets/ce48dffd-5daa-4d4d-982b-c1804fae6590" /> </p>

In saturation:

Channel voltage becomes:

VGS − VT

Replacing VDS in the equation gives:

I<sub>D</sub> = (k<sub>n</sub> / 2) (VGS − VT)²

This is the saturation region current equation.

This equation is no longer linear in VDS.


## Technology Constants (Model Parameters)

<p align="center">
<img width="462" height="278" alt="image" src="https://github.com/user-attachments/assets/5f70f1dc-b838-4068-8cb5-c90f1789e902" /> </p>

Certain parameters are technology constants, for example:

- μn  
- Cox  
- k'n  
- k<sub>n</sub>  
- VT  
- γ  
- φf  

These constants come from the foundry for each technology node.

Examples:

- 1.2 micron  
- 180 nanometers  
- 20 nanometers  

Each node has unique values.

These values are provided to SPICE through a special file called:

**Model File**

We do not derive these again.

They are supplied as constants.

Correct model parameters are essential to obtain correct voltage and current waveforms.


## SPICE Inputs Required

Two main inputs are required:

1. SPICE Model Parameters (Technology constants)  
2. SPICE Netlist  

Both must be provided correctly to the SPICE engine.


## SPICE Output

<p align="center">
<img width="131" height="247" alt="image" src="https://github.com/user-attachments/assets/09c12adb-5648-4ce7-bb1f-d026309b0652" />
 </p>

When both:

- Model file  
- Netlist  

are fed into SPICE,

We obtain:

- IDS vs VDS curves  
- Different curves for different VGS values  

Previously, we observed behavior where part of curve was linear and part entered saturation.

SPICE reproduces these curves automatically.


## Netlist 

<p align="center">
<img width="592" height="296" alt="image" src="https://github.com/user-attachments/assets/a59dcde1-8517-4102-ab49-06df419838b8" /> </p>

SPICE requires a special syntax (like C or C++ program syntax).

The MOSFET cannot be given directly as a diagram.

It must be written in a special formatted netlist.

This formatted description is called a:

**SPICE Deck**


## MOSFET Circuit Setup

<p align="center">
<img width="268" height="186" alt="image" src="https://github.com/user-attachments/assets/19dfb3f4-643b-4b74-82ec-5f2eb374905d" /> </p>

Circuit connections:

- Drain connected to VDD  
- Source connected to ground  
- Substrate connected to ground  
- Gate connected through a protection resistor  

The protection resistor is used because:

Current should not directly enter the gate and damage it.

---

# L2 Circuit Description in SPICE Syntax

## Writing the SPICE Netlist

<p align="center">
<img width="612" height="298" alt="image" src="https://github.com/user-attachments/assets/d1d151fb-2c42-463c-b04f-504e2b920c7e" /> </p>

Now that we understand the basic SPICE setup, the next step is to write the SPICE netlist in the correct syntax so that it is properly understood by the SPICE engine.

Just like a C program or any software language has its own syntax, SPICE also has its own syntactical format.

We now write the SPICE netlist for this circuit and simulate it.


## Assigning Circuit Values

<p align="center">
<img width="282" height="157" alt="image" src="https://github.com/user-attachments/assets/84b52116-dfc6-44b3-98aa-d3d6a31a1205" /> </p>

Before defining nodes, assign values:

- VDD = 2.5V  
- R1 = 55 ohms  
- MOSFET M1:
  - Width (W) = 1.8 micron  
  - Length (L) = 1.2 micron  

VSS = 0V

This must now be written in a SPICE-understandable format.


## Step 1: Defining Nodes

<p align="center"> <img width="293" height="176" alt="image" src="https://github.com/user-attachments/assets/4d650baf-db72-47dd-bbac-9abf13807311" />
</p>

A component must be defined between nodes.

A node is formed where there is no electrical obstruction along a connected wire.

For example:

- Continuous wire from R1 to voltage source → one node  
- Continuous wire from supply to ground → one node  
- Continuous wire from transistor terminal to supply → one node  

The circuit contains four nodes.

<p align="center">
  <img width="597" height="256" alt="image" src="https://github.com/user-attachments/assets/2c60183c-db18-4682-8286-f82f0e68cc87" />
</p>

We assign names:

- in  
- n1  
- 0  
- VDD  

There is no restriction on node names. They can be numeric or text.


## Step 2: Writing MOSFET Entry

<p align="center">
<img width="611" height="178" alt="image" src="https://github.com/user-attachments/assets/e85124f1-41ce-42ef-9c08-25b3979b96db" /> </p>

MOSFET has four terminals:

Drain, Gate, Source, Substrate.

SPICE expects the order:

Drain Gate Source Substrate (DGSS)

Syntax format:

Mname Drain Gate Source Substrate ModelName W= L=

For this circuit:

M1 vdd n1 0 0 NMOS W=1.8u L=1.2u

Explanation:

- M1 → first MOSFET  
- vdd → Drain node  
- n1 → Gate node  
- 0 → Source node  
- 0 → Substrate node  
- NMOS → model name (comes from technology file)  
- W and L → width and length  

## Step 3: Writing Resistor Entry

<p align="center">
<img width="606" height="186" alt="image" src="https://github.com/user-attachments/assets/f8ffc04a-1cc4-4b56-b60d-49dc03d28967" /> </p>


Resistors start with R.

Syntax:

Rname Node1 Node2 Value

For this circuit:

R1 in n1 55

This defines:

- R1 between node "in" and node "n1"  
- Value = 55 ohms  


## Step 4: Writing VDD Supply

<p align="center">
<img width="640" height="210" alt="image" src="https://github.com/user-attachments/assets/a00465ed-e016-48ad-9f34-380b455a4352" /> </p>

Voltage sources start with V.

Syntax:

Vname PositiveNode NegativeNode Value

For VDD:

VDD VDD 0 2.5

- Between node VDD and ground  
- Value = 2.5V  


## Step 5: Writing Gate Voltage Source

<p align="center">
<img width="617" height="203" alt="image" src="https://github.com/user-attachments/assets/26d0cab3-6674-4db5-9228-2772c301cf3b" /> </p>

Gate voltage source:

VIN in 0 2.5

- Between node "in" and ground  
- Value = 2.5V  

Any element starting with V represents a voltage source.


## Complete SPICE Netlist

<p align="center">
<img width="262" height="68" alt="image" src="https://github.com/user-attachments/assets/18675667-e02c-4a30-9ec7-d799037171d9" /> </p>

```spice
M1 VDD n1 0 0 NMOS W=1.8u L=1.2u
R1 in n1 55
VDD VDD 0 2.5
VIN in 0 2.5
```

---


# L3 Define Technology Parameters

## Model Definition for NMOS

<p align="center">
  <img width="310" height="273" alt="image" src="https://github.com/user-attachments/assets/885d43d5-2e31-468a-8c60-fb0bd69ee8f0" />
</p>

We have already defined the SPICE netlist.  
The next step is to define the model for this NMOS.

A model describes how a device behaves.

For example:

- AND gate → output is Boolean multiplication of inputs  
- OR gate → output is Boolean addition of inputs  

Similarly, NMOS has its own models.

When we plug in the model for this NMOS, the SPICE engine understands:

- Where NMOS is picked from  
- What constants must be used  
- How to evaluate threshold voltage  
- How to evaluate drain current equations  

All model parameters come as a package.


## Important Model Parameters

We previously introduced model parameters such as:

- VTO → Needed for threshold voltage  
- Gamma → Body effect coefficient  
- k'n  
- Lambda  
- Cox  
- Epsilon values  

Once these constants are provided, it becomes easy for the engine to calculate:

- VT  
- ID (linear region)  
- ID (saturation region)

These values are used during simulation.


## .MODEL Statement

The model is defined using:

```spice
.model NMOS nmos (parameters)
```


## Important Rule

The name **NMOS** in the model file must match exactly with the name used in the netlist.

If the names do not match, simulation will not work correctly.

This is a very important step.

Similarly, if PMOS is used in the circuit, the PMOS name must match its model definition.


## Example Model Parameters

Some parameter mappings:

- VTH0 → Threshold voltage without body bias  
- TOX → Oxide thickness  
- U0 → Mobility  
- Gamma1 → Body effect coefficient  

Example format:

```spice
.model NMOS nmos
+ TOX = value
+ VTH0 = value
+ U0 = value
+ GAMMA1 = value
```

Once these are defined:

The engine automatically substitutes:

- Gamma value into VT equation  
- Mobility into current equation  
- TOX into Cox calculation  

The engine evaluates all equations internally.

Provided correct inputs are given.


## Model Files for Technology Node

<p align="center">
<img width="323" height="145" alt="image" src="https://github.com/user-attachments/assets/2da7ca09-bd26-4db7-93fd-2355a768afde" /> </p>

For each technology node:

- 1.2 micron  
- 350 nanometer  
- Lower nodes  

Foundry provides all constants.

You package all model parameters into a single file.

Example section:

```spice
.lib CMOS_models
...
.endl CMOS_models
```

This defines a library block.

The list inside a real technology file is very large.

Only required parameters are used for our purpose here.


## Including Model File in Netlist

<p align="center">
<img width="317" height="252" alt="image" src="https://github.com/user-attachments/assets/9483a948-b5f2-4ac1-9401-d574498bd264" /> </p>

To use the model file in the top-level netlist:

```spice
.lib filename.mod CMOS_models
```

- `filename.mod` → Model file  
- `CMOS_models` → Section name inside file  

After inclusion:

- NMOS model parameters are loaded  
- Equations are evaluated  
- VT and ID models are active  


## Complete SPICE Deck Structure

We now have three sections:

### 1. Netlist Description

```spice
M1 VDD n1 0 0 NMOS W=1.8u L=1.2u
R1 in n1 55
VDD VDD 0 2.5
VIN in 0 2.5
```

### 2. Model File Inclusion

```spice
.lib filename.mod CMOS_models
```

### 3. Simulation Commands

Simulation commands are used to sweep voltages.

Previously, we calculated drain current for a single VGS.

But to evaluate:

- ID for multiple VGS values  
- While sweeping VDS from 0 to supply voltage  

We use SPICE simulation commands.

These commands allow:

- Sweeping VGS  
- Sweeping VDS  

This replaces manual hand calculation.

---


# L4 First SPICE simulation

## Clone Repository

```bash
git clone https://github.com/kunalg123/sky130CircuitDesignWorkshop
cd sky130CircuitDesignWorkshop/design
ls
```

## Go to Device Models

```bash
cd sky130
cd antiphase
cd cells
```

Use:

- `nfet_01v8`

Only use **W/L values provided inside the model corner files**.


## Select Corner

Open library file:

```bash
less sky130.lib.spice
```

Corners available:

- TT → Typical  
- SS → Slow-Slow  
- FF → Fast-Fast  
- SF → Slow-Fast  

Modify `.lib` line to change corner.


## Transistor Format

SPICE syntax:

```
M1 Drain Gate Source Bulk nfet_01v8 W=1.68 L=0.15
```

Source = 0  
Bulk = 0  
Supply = 1.8V  


## DC Sweep

Sweep:

- VDS → 0 to 1.8V (step 0.1V)
- VGS → 0 to 1.8V (step 0.2V)

```spice
.dc VDS 0 1.8 0.1 VGS 0 1.8 0.2
```


## Run Simulation

Inside NGSpice:

```bash
plot -i(VDS)
```


## Result

<p align="center"> <img width="493" height="502" alt="image" src="https://github.com/user-attachments/assets/4b894ab8-9b01-43bd-b5ce-49ed9a7d5f7c" />
</p>

- ID vs VDS curves generated  
- Low VDS → Linear region  
- High VDS → Saturation (quadratic behavior)  

---

# L5 SPICE Lab with sky130 models

## Clone and Navigate

```bash
cd
git clone https://github.com/kunalg123/sky130CircuitDesignWorkshop
cd sky130_circuit_design_workshop
cd sky130
cd cells
cd nfet_01v8
```

## Open Library File

```bash
less sky130.lib.spice
```

Use **TT (Typical corner)**.

## Transistor Parameters

- Model: `nfet_01v8`
- W = **5 µm**
- L = **2 µm**
- Supply Voltage = **1.8 V**
- Source = 0
- Bulk = 0

## DC Sweep Settings

- VDS: 0 → 1.8 V (step 0.1 V)
- VGS: 0 → 1.8 V (step 0.2 V)


## Run Simulation

Inside NGSpice:

```bash
plot -VDD#branch
```

## Results

<p align="center"> <img width="990" height="472" alt="image" src="https://github.com/user-attachments/assets/0ecc3ac7-4874-42a0-a9f2-d5c7699d98b7" />
</p>
  
- ID vs VDS curves generated  
- Cutoff below **Vth ≈ 0.55 V**  
- Small current at VGS = 0.6 V (~2 µA)  

---

<br><br>

# NgspiceSky130-Day2-Velocity saturation and basics of CMOS inverter VTC

# SPICE simulation for lower nodes and velocity saturation effect

# L1 SPICE simulation for lower nodes

## SPICE Simulation Results

In the previous simulation:

- Y-axis → Drain Current (ID)  
- X-axis → Drain-to-Source Voltage (VDS)

Multiple curves correspond to different values of VGS.


## Understanding the Curves

<p align="center">
  <img width="587" height="337" alt="image" src="https://github.com/user-attachments/assets/0c5b4a7a-549b-4ce7-91fa-38107724f6c4" />
</p>

### VGS = 0 V

- Curve overlaps the X-axis.
- Drain current = 0.
- Reason: Device is OFF.
- No channel formed.


### VGS ≈ Threshold

A curve slightly above zero current:

- VGS just crosses threshold voltage.
- Minimum channel is formed.
- Small drain current appears.


### Higher VGS Values

Curves correspond to:

- VGS = 1 V  
- VGS = 1.5 V  
- VGS = 2 V  
- VGS = 2.5 V  

All previously derived equations are encapsulated in these curves.

Each curve represents ID vs VDS for a specific VGS.


## Regions of Operation

<p align="center">
 <img width="546" height="308" alt="image" src="https://github.com/user-attachments/assets/8f156429-8598-45d3-9de7-b80534748e7d" />
</p>

The curve has two behavioral regions:

### 1️. Linear (Resistive) Region

- Drain current increases linearly with VDS.
- Occurs at low VDS.
- Derived equation:

```
ID = kn [(VGS − VT)VDS − VDS²/2]
```

At small VDS:

```
VDS²/2 → negligible
```

So:

```
ID ≈ kn (VGS − VT)VDS
```

Drain current is linear in VDS.


### 2️. Saturation Region

Condition:

```
VDS ≥ (VGS − VT)
```

At this point:

- Replace VDS with (VGS − VT)
- Drain current becomes:

```
ID = (kn/2)(VGS − VT)² (1 + λVDS)
```

- Not perfectly constant.
- Slight increase due to channel length modulation.
- Appears almost constant.


### 3️. Cutoff Region

Condition:

```
VGS ≤ VT
```

- No channel formed.
- Device OFF.
- ID = 0.


## Moving to Lower Node

Now consider new device dimensions:

- W = 0.375 µm  
- L = 0.25 µm  

W/L ratio is kept constant.

Expectation:

If W/L is constant → Drain current should remain same.

But this does **not** happen at lower nodes.


## New SPICE Simulation Setup

Only change from previous deck:

- W changed to 0.375 µm
- L changed to 0.25 µm
- All other parameters remain same:
  - Resistance
  - VDD
  - VIN
  - .op
  - .dc
  - Model file


## Running New Simulation

1. Source the new circuit file (.cir)
2. Run simulation:

```
run
```

3. Check available plots:

```
setplot
```

Select:

```
dc1
```

4. Display available nodes:

```
display
```

5. Plot drain current:

```
plot -VDD#branch
```

(negative sign due to current direction convention)


## New Plot Observations

Observations compared to previous case:

### 1️. Reduced Difference Between Curves

Spacing between adjacent VGS curves is reduced.


### 2️. Saturation Current Changed

Current in saturation region is different from previous long-channel case.


### 3️. Curve Spacing Behavior Changed

Difference between adjacent curves appears more uniform compared to earlier case.


## Comparison: Long Channel vs Short Channel

<p align="center">
  <img width="697" height="296" alt="image" src="https://github.com/user-attachments/assets/62f0443f-ebbd-41de-a45e-46201785ddcc" />
</p>

Previous device:

- W = 1.8 µm  
- L = 1.2 µm  

New device:

- W = 0.375 µm  
- L = 0.25 µm  

Even though W/L ratio is constant:

- Drain current is not identical.
- Behavior changes at lower technology nodes.


## Conclusion

Maintaining constant W/L does **not** guarantee same drain current at lower nodes.

Short-channel effects alter device behavior.

---


# L2 Drain current vs gate voltage for long and short channel device

## Previous Simulation Context

In the previous SPICE simulation, two devices were analyzed:

- **Long channel device** → 1.2 µm  
- **Short channel device** → 0.25 µm  

We now focus on:

> Drain Current (ID) vs Gate Voltage (VGS)  
> At constant Drain Voltage (VDS)

## Observation for Long Channel Device (1.2 µm)

<p align="center">
  <img width="685" height="295" alt="image" src="https://github.com/user-attachments/assets/f2c8c513-bf7c-4469-918a-86484babfce0" />
</p>

Let:

- VDS = 2.5 V (constant)

Observations:

- At VGS = 0 → ID = 0  
- At VGS = 0.5 V → small ID (~10 µA)  
- At VGS = 1 V → larger ID (~40 µA)  

ID does **not** increase linearly with VGS.

It shows **quadratic dependence**.

This matches the derived equation:

```
ID = (kn/2) (VGS − VT)²
```

So:

- ID ∝ (VGS − VT)²  
- Drain current increases quadratically with gate voltage.

---

## Observation for Short Channel Device (0.25 µm)

<p align="center">
  <img width="691" height="287" alt="image" src="https://github.com/user-attachments/assets/15b8ab6d-26aa-4f71-8225-440ecfe95716" />
</p>

Initial region:

- At VGS = 0 → ID = 0  
- At VGS = 0.5 V → small ID  
- At VGS = 1 V → larger ID  

Here also, initially:

- ID shows quadratic dependence.

But after a certain VGS:

- ID increases **linearly** with VGS.

This behavior is different from long channel device.

---

## Key Difference

<p align="center">
<img width="698" height="318" alt="image" src="https://github.com/user-attachments/assets/235dbec3-c3de-4fd4-8a90-4eb3fee6491e" /> </p>

| Device Type | Behavior |
|-------------|----------|
| Long Channel (1.2 µm) | Quadratic throughout |
| Short Channel (0.25 µm) | Quadratic initially → Linear at higher VGS |

This effect is due to:

> **Velocity Saturation**

# SPICE Simulation Setup – ID vs VGS

We now perform:

- ID vs VGS
- At constant VDS = 2.5 V


## SPICE Deck Change

Only one line changes:
New sweep condition:

- Sweep VGS from 0 → 2.5 V  
- Step = 0.1 V  
- VDS held constant at 2.5 V  

Syntax meaning:

- Left-hand variable is swept
- Right-hand variable defines outer sweep

# Conclusion

For constant VDS:

- Long channel device follows quadratic model.
- Short channel device deviates due to velocity saturation.
- This is a short channel effect observed at lower nodes.

Further analysis continues next.

---

# L3 Velocity Saturation at Lower and Higher Electric Fields

## ID vs VGS Simulation Results

<p align="center">
  <img width="692" height="322" alt="image" src="https://github.com/user-attachments/assets/8ff06d48-22a9-4955-8178-ac46916b18bd" />
</p>

We performed ID vs VGS simulations at constant VDS for:

- Long channel device (1.2 µm)
- Short channel device (0.25 µm)

### Observation

### Long Channel (1.2 µm)

- Drain current shows complete **quadratic dependence** on VGS.
- Matches derived saturation model:

```
ID ∝ (VGS − VT)²
```
The curve follows quadratic behavior throughout.

### Short Channel (0.25 µm)

For lower VGS:

- Trend is still quadratic.
- Matches saturation model.

For higher VGS:

- Curve becomes **linear**.
- No longer follows quadratic dependence.

Thus:

- At low VGS → Quadratic behavior.
- At high VGS → Linear behavior.

This deviation is a **short channel effect**.

# Velocity Saturation

Velocity saturation is one of the major short channel effects.

## Electric Field vs Velocity

<p align="center">
  <img width="527" height="189" alt="image" src="https://github.com/user-attachments/assets/02cef8bb-768d-4d83-ac81-b91c58b846e0" />
</p>

Trend from device physics:

- For low electric field → velocity ∝ electric field (linear).
- Beyond critical electric field → velocity becomes constant.

This constant value is:

```
VSAT (Saturation velocity)
```

## Velocity Model

For electric field E:

### If E < EC (critical field) &  If E ≥ EC

<p align="center">
<img width="267" height="62" alt="image" src="https://github.com/user-attachments/assets/084deaa0-e7fa-492b-a133-23473add940b" /> </p>


## Boundary Condition

<p align="center">
<img width="130" height="45" alt="image" src="https://github.com/user-attachments/assets/7ff202e1-34a5-4412-984a-d7af25b6166b" />
</p>

At E = EC:

Equating the two velocity expressions:

```
μn EC / 2 = VSAT
```

Rearranging:

```
EC = 2 VSAT / μn
```

This defines the critical electric field.


# Re-Deriving Drain Current with Velocity Saturation

<p align="center">
<img width="633" height="225" alt="image" src="https://github.com/user-attachments/assets/35728834-5d3e-49be-b5c8-cec300467206" />
</p>

Previously:

- Charge = Cox (VGS − VX − VT)
- Velocity = μn E

Using these, we derived ID.

Now velocity saturates, so drain current model must account for VSAT.

The full derived equation becomes complex and difficult for hand calculation.

Therefore, a simplified model is introduced.


# Regions of Operation

<p align="center"> <img width="327" height="142" alt="image" src="https://github.com/user-attachments/assets/7e733104-2458-4fd9-8248-75b9125d0984" />
 </p>

For long channel devices:

1. Cutoff
2. Linear
3. Saturation

For short channel devices:

1. Cutoff
2. Linear
3. Saturation (low VGS)
4. Velocity Saturation (high VGS)

---

# Simplified Notation

Define:

```
VGT = VGS − VT
```

This simplifies equations.

---

# Complete Drain Current Model

<p align="center"> <img width="512" height="177" alt="image" src="https://github.com/user-attachments/assets/9d79f9f9-3f84-4400-a3f9-1fac2290cb70" />
 </p>
  
### Cutoff Region

If:

```
VGT < 0
```

Then:

```
ID = 0
```

(Device OFF)

---

### Unified Model for Other Regions

Drain current:

```
ID = kn [ VGT · Vmin − (Vmin² / 2) ] (1 + λVDS)
```

Where:

```
Vmin = min (VGT, VDS, VDSAT)
```

## Interpretation of Vmin

- If VGT is minimum → behaves like saturation region.
- If VDS is minimum → behaves like linear region.
- If VDSAT is minimum → velocity saturation region dominates.

This single model accounts for:

- Linear region
- Saturation region
- Velocity saturation region

---

# L4 Velocity Saturation Drain Current Model

## Unified Drain Current Model

In the previous discussions, a unified drain current model was introduced to represent all regions of operation, including velocity saturation.

The model is:

```
ID = kn (VGT · Vmin − Vmin² / 2) (1 + λVDS)
```

Where:

```
VGT = VGS − VT
Vmin = min (VGT, VDS, VDSAT)
```

The term `(1 + λVDS)` is retained for all regions.

For very low values of λVDS, this term approaches 1 and can effectively be ignored.

## Cutoff Region

If:

```
VGT ≤ 0
```

Then:

```
ID = 0
```

The device is completely OFF.

This applies to both long and short channel devices.

# Technology Parameter: VDSAT

<p align="center"> <img width="452" height="113" alt="image" src="https://github.com/user-attachments/assets/0108d8c5-ce3d-466c-9f36-fb382285236a" />
  </p>

For short channel devices (< 250 nm), a technology parameter called **VDSAT** is defined.

- Provided by foundry
- Present in model file
- Constant for a given technology node
- Independent of VGS and VDS

VDSAT defines the voltage at which velocity saturation begins.


# Case Analysis of Vmin

We now evaluate the unified model for different minimum conditions.

## Case 1: VGT is Minimum

<p align="center"> <img width="495" height="232" alt="image" src="https://github.com/user-attachments/assets/bb6615a2-c6e2-4f08-9f60-2f38fce4dac2" />
 </p>

If:

```
Vmin = VGT
```

Substitute into model:

```
ID = kn (VGT² − VGT² / 2)(1 + λVDS)
```

Which simplifies to:

```
ID = (kn / 2) VGT² (1 + λVDS)
```

This is the familiar **saturation region equation**.

### Interpretation

If VGT is minimum:

- VDS must be high
- Device operates in saturation
- Valid for both long and short channel

## Case 2: VDS is Minimum

<p align="center"> <img width="495" height="233" alt="image" src="https://github.com/user-attachments/assets/215ed6ca-9c49-4cf5-9e41-a34b4fbf2977" />
</p>

If:

```
Vmin = VDS
```

Substitute into model:

```
ID = kn (VGT·VDS − VDS²/2)(1 + λVDS)
```

For small VDS:

```
(1 + λVDS) ≈ 1
```

Thus:

```
ID = kn (VGS − VT)VDS − VDS²/2
```

This matches the **linear (resistive) region equation**.

### Interpretation

- Occurs at small VDS
- Device behaves resistively
- Drain current increases linearly with VDS

## Case 3: VDSAT is Minimum (Velocity Saturation)

<p align="center"> <img width="482" height="227" alt="image" src="https://github.com/user-attachments/assets/0f4ddbd5-2c86-4197-a564-3b7d86a3e201" />
 </p>
  
If:

```
Vmin = VDSAT
```

Substitute into model:

```
ID = kn (VGT·VDSAT − VDSAT²/2)(1 + λVDS)
```

This is the drain current equation for **velocity saturation region**.

This region exists only in short channel devices.

# Expanded Form

<p align="center">
<img width="437" height="34" alt="image" src="https://github.com/user-attachments/assets/726f1b5d-66ed-4d65-9ea1-246ff40d84a4" />
</p>

Expanding kn:

```
kn = μn Cox (W/L)
```

Thus:

```
ID = μn Cox (W/L) [VGT·VDSAT − VDSAT²/2]
```

# Important Observation

<p align="center">
<img width="1322" height="607" alt="image" src="https://github.com/user-attachments/assets/f8d2cfcc-c2e3-4c15-9e31-3da4d1674cb2" /> </p>

If W/L is kept constant:

The long channel expectation is that drain current remains same.

However, experimentally:

- Long channel (1.8µm / 1.2µm) → Peak current ≈ 410 µA
- Short channel (scaled device) → Peak current ≈ 210 µA

The peak current reduces in short channel devices.

This deviation occurs due to **velocity saturation**.

---

# L5 Labs Sky130 Id-Vgs

## Device Parameters

- **Technology:** Sky130  
- **Corner:** Typical (TT)  
- **Width (W):** 0.39 µm  
- **Length (L):** 0.15 µm (Short channel)  
- **VDS Max:** 1.8 V  

## Plot - 1

**Sweep Conditions:**
- VDS: 0 → 1.8 V (step 0.1 V)  
- VGS: 0 → 1.8 V (step 0.2 V)  

**Result:**

<p align="center"> <img width="995" height="486" alt="image" src="https://github.com/user-attachments/assets/814fa3ad-dd21-4fdc-b67b-3bd0004381ce" />
</p>

- Low VGS → Quadratic behavior  
- High VGS (≥ ~1 V) → Linear behavior  
- Shows **velocity saturation**

## Plot - 2

**Sweep Conditions:**
- VDS = 1.8 V (constant)  
- VGS: 0 → 1.8 V  

**Result:**
<p align="center"> <img width="993" height="486" alt="image" src="https://github.com/user-attachments/assets/4c55d4dd-988c-41e5-ad55-eed76779f315" />
</p>

- Linear trend at higher VGS  
- Confirms **short channel velocity saturation**

---

# L6 Sky130 Lab

## Device / Simulation Setup

- **Technology:** Sky130  
- **Corner:** Typical (TT)  
- **Curve Used:** ID vs VGS  
- **VDS:** 1.8 V (constant)  
- **Method:** Tangent method on ID–VGS curve  


## Result

<p align="center"> <img width="381" height="293" alt="image" src="https://github.com/user-attachments/assets/bf44a03a-afb6-4971-ad36-60309ec43d13" />
 </p>
  
- **Threshold Voltage (VT) ≈ 0.76 V**

(Obtained by extending tangent of steep ID–VGS slope to X-axis.)

---

<br>

# CMOS voltage transfer characteristics (VTC)

# L1 MOSFET as a Switch

## MOSFET from a Switch Perspective

<p align="center"> <img width="272" height="261" alt="image" src="https://github.com/user-attachments/assets/4ec2905b-0ac2-47ac-884f-94896847ba0e" />
 </p>

To understand CMOS voltage transfer characteristics, the MOSFET must be viewed from a **switch point of view** instead of only a device physics perspective.

Consider a generic MOS transistor (NMOS or PMOS).

The device turns **ON** when:

```
|VGS| ≥ |VT|
```

- For NMOS → VGS is positive  
- For PMOS → VGS is negative  

The magnitude condition applies in both cases.

## MOSFET Switch Representation

<p align="center">
 <img width="490" height="221" alt="image" src="https://github.com/user-attachments/assets/9b372da3-2060-4125-8d0e-8e1ba01f8486" />
</p>

### Case 1: VGS < VT

- Device is OFF  
- Infinite resistance between drain and source  
- Open circuit  
- No current flow  

### Case 2: VGS ≥ VT

- Device is ON  
- Finite resistance between drain and source  
- Closed switch  
- Current flows  

The ON resistance is finite and nonlinear.


## CMOS Structure

Now bias the devices to form a CMOS inverter.

<p align="center">
  <img width="362" height="317" alt="image" src="https://github.com/user-attachments/assets/fb8d6143-7780-4c01-8a35-ede5361c9a53" />
</p>

### Connections

- PMOS at top → Source connected to VDD  
- NMOS at bottom → Source connected to VSS (ground)  
- Gates tied together → Input (VIN)  
- Drains tied together → Output  
- Load capacitance → CL  

CMOS = Complementary MOS  
When one device is ON, the other is OFF.


## Case Analysis

## Case: VIN = VDD (Input High)

```
VIN = VDD
```

### PMOS

<p align="center">
<img width="293" height="357" alt="image" src="https://github.com/user-attachments/assets/897a7831-57f8-4688-9c82-2cf422acca07" />
</p>

VGS (PMOS):

```
VGS = VG − VS
```

Here:

```
VG = VDD
VS = VDD
```

Therefore:

```
VGS = 0
```

Since |VGS| < |VT|:

- PMOS turns OFF  
- Represented as open switch

### NMOS

<p align="center">
<img width="327" height="357" alt="image" src="https://github.com/user-attachments/assets/ee3a19d3-bc06-4d47-b966-aa2f0762a85f" />
</p>

VGS (NMOS):

```
VGS = VIN − VSS
```

Since VSS = 0:

```
VGS = VDD
```

If VDD > VT:

- NMOS turns ON  
- Represented as resistor  
 

## Resulting Circuit (VIN = VDD)

<p align="center">
  <img width="172" height="307" alt="image" src="https://github.com/user-attachments/assets/c5835715-66f6-4cb8-af4b-7008a0ff6516" />
</p>

- PMOS → Open  
- NMOS → Resistor  
- Output connected to ground through NMOS  
- Output pulled LOW  

## Important Observation

The gate-to-source voltage depends on node potentials:

- NMOS → VGS = VIN − VSS  
- PMOS → VGS = VIN − VDD  

Correct polarity and node reference are essential to determine ON/OFF state.

## Summary

MOSFET as Switch:

| Condition | State | Representation |
|------------|--------|----------------|
| VGS < VT | OFF | Open switch |
| VGS ≥ VT | ON | Finite resistor |

For VIN = VDD:

- NMOS → ON  
- PMOS → OFF  
- Output → LOW  

This forms the basis for CMOS voltage transfer characteristics.

---

# L2 Introduction to standard MOS voltage current parameters

## Objective

To derive equivalent circuits of a CMOS inverter under different input conditions in order to later obtain the Voltage Transfer Characteristics (VTC) and delay.

We require:

- Equivalent circuit when VIN = High  
- Equivalent circuit when VIN = Low  

These will later be merged to derive CMOS VTC.

## VIN = 0 V (Low Input)

### PMOS Operation

<p align="center">
<img width="162" height="348" alt="image" src="https://github.com/user-attachments/assets/37680981-09de-49ab-8f0f-d247e76301fe" /> </p>

For PMOS:

```
VGS(P) = VG − VS
```
Condition for PMOS ON:

```
|VGS| > |VT|
```

PMOS turns ON.

An ON transistor is modeled as a resistor:

```
RP
```

This resistance is **non-linear**, not an ideal resistor.

### NMOS Operation

<p align="center">
<img width="137" height="347" alt="image" src="https://github.com/user-attachments/assets/d85c39d2-f78e-4686-afbf-87d9cff1f1e6" />
</p>

For NMOS:

```
VGS < VT
```

NMOS turns OFF.

An OFF transistor is modeled as an open switch.


## Current Flow (VIN = 0)

<p align="center">
<img width="645" height="336" alt="image" src="https://github.com/user-attachments/assets/1db56354-3292-4815-ab30-513cdb9d109f" />
</p>

There is a direct path:

```
VDD → RP → CL
```

Capacitor charges.

Final condition:

```
VOUT = VDD
```

## Naming Conventions

<p align="center">
<img width="650" height="331" alt="image" src="https://github.com/user-attachments/assets/5d7601d9-c60c-4a65-9f2d-3b89cd63612c" />
</p>

To proceed with systematic derivation:

### Gate–Source Voltages

- VGSP → PMOS gate–source voltage
- VGSN → NMOS gate–source voltage

### Drain–Source Voltages

- VDSP → PMOS drain–source voltage
- VDSN → NMOS drain–source voltage

### Drain Currents

- IDSP → PMOS drain current
- IDSN → NMOS drain current

These naming conventions are required to derive:

- Current equations
- Load curves
- Voltage Transfer Characteristics (VTC)

---

## L3 PMOS / NMOS Drain Current vs Drain Voltage

### CMOS Inverter Reference

<p align="center">
  <img width="660" height="357" alt="image" src="https://github.com/user-attachments/assets/7ac0d853-546a-4eb1-9411-f74e7207bca4" />
</p>

We previously defined voltage naming conventions:

- **VGSN, VDSN** → NMOS voltages  
- **VGSP, VDSP** → PMOS voltages  

Important observation:

- PMOS and NMOS drain currents flow in opposite directions.
- Therefore:

```
IDSP = − IDSN
```
(Current sign differs only due to direction.)


## Voltage Relationships

### NMOS

Source connected to ground (VSS = 0).

```
VGSN = VIN − VSS = VIN
VDSN = VOUT − VSS = VOUT
```

NMOS voltage expressions are simple because one terminal is grounded.


### PMOS

Source connected to VDD.

```
VGSP = VIN − VDD
VDSP = VOUT − VDD
```

PMOS voltages require subtracting VDD.

Care must be taken with sign conventions.


## NMOS ID vs VDS Curve

<p align="center">
  <img width="422" height="356" alt="image" src="https://github.com/user-attachments/assets/44b6b509-c595-40d2-bd63-f6b4824aebc5" />
</p>

Plot: **IDSN vs VDSN**

Observations:

- When VGSN = 0 → IDSN ≈ 0 (device OFF)
- When VGSN > VT → current flows
- Increasing VGSN → higher drain current
- Curve transitions from linear to saturation

Multiple curves correspond to:

```
VGSN1 < VGSN2 < VGSN3 < ...
```

Higher VGS → higher current.


## PMOS ID vs VDS Curve

<p align="center">
  <img width="382" height="432" alt="image" src="https://github.com/user-attachments/assets/bdf03f27-89c3-44e7-835b-6913cb43395f" />
</p>

Plot: **IDSP vs VDSP**

Key differences:

- IDSP is negative (opposite current direction)
- VDSP is negative (due to reference to VDD)
- Magnitude behavior similar to NMOS

Observations:

- If |VGSP| < |VT| → PMOS OFF → IDSP = 0
- If |VGSP| > |VT| → PMOS ON → current flows
- Increasing |VGSP| → higher magnitude of drain current

## Current Direction Relationship

Because capacitor charging/discharging directions are opposite:

```
IDSP = − IDSN
```
Current itself is not negative physically — sign only represents direction reference.

---

# L4 Step 1 – Convert PMOS Gate-Source Voltage to VIN

## CMOS Inverter Reference

We previously defined:

- VGSN, VDSN → NMOS voltages  
- VGSP, VDSP → PMOS voltages  

However, in digital logic:

- Only **VIN** and **VOUT** are visible.
- Internal voltages (VGSP, VDSP, etc.) are not visible.

Therefore, all curves must be expressed as functions of:

```
VIN and VOUT only
```

## Express VGSP in terms of VIN

From earlier derivation:

```
VGSP = VIN − VDD
```

Rearranging:

```
VIN = VGSP + VDD
```

Assume:

```
VDD = 2 V
```

Each PMOS curve can be re-plotted as:

```
IDSN vs VIN
```

Example:

- VGSP = 0 → VIN = 2 V → ID = 0
- VGSP = −0.5 → VIN = 1.5 V
- VGSP = −1 → VIN = 1 V
- VGSP = −1.5 → VIN = 0.5 V
- VGSP = −2 → VIN = 0 V

Drain current values remain same in magnitude, but sign flips to match NMOS convention.


## Conversion Table

<p align="center">
<img width="342" height="217" alt="image" src="https://github.com/user-attachments/assets/d53beaae-1cb5-44b7-9f32-d888c71d0f98" />
</p

Shows conversion of PMOS gate voltage into input voltage.


## NMOS ID–VDS Curves & PMOS ID–VDS Curves

<p align="center">
<img width="443" height="368" alt="image" src="https://github.com/user-attachments/assets/3d7ac33e-9461-47d8-b8d4-4af062390b7e" /> </p>


## Result After Conversion

<p align="center"> <img width="327" height="317" alt="image" src="https://github.com/user-attachments/assets/96d89aa1-bf57-4651-a4c4-8358458fe6b1" />
</p>
  
- VGSP eliminated
- IDSP eliminated
- Only IDSN retained
- Current now expressed as function of VIN

---

# L5 Step 2 & Step 3 – Convert PMOS and NMOS Drain–Source Voltage to VOUT

## Step 1 Completed

Previously:

- Converted **VGSP** → function of **VIN**
- Converted **IDSP** → expressed as **IDSN**
- PMOS load curve expressed as function of **VIN**

Remaining variable:

```
VDSP
```

Now we convert **VDSP to VOUT**

## Step 2: Convert VDSP to VOUT (PMOS)

From earlier relation:

```
VOUT = VDD + VDSP
```

Rearranged from:

```
VDSP = VOUT − VDD
```

This means:

- Entire PMOS curve shifts by **+VDD**
- X-axis (VDSP) becomes **VOUT**


## Understanding the Shift

If:

```
VDSP = −2 V
VDD = 2 V
```

Then:

```
VOUT = −2 + 2 = 0 V
```

So:

- When VOUT = 0  
- Capacitor is completely discharged  
- Charging current flows  

Finite current exists at VOUT = 0.

If:

```
VDSP = 0
```

Then:

```
VOUT = 2 V
```

At:

```
VOUT = VDD
```

Capacitor fully charged → Current = 0

## PMOS Load Curve (After Conversion)

<p align="center">
 <img width="687" height="215" alt="image" src="https://github.com/user-attachments/assets/439d09e1-73a9-4e65-922f-d054e9bca01b" />
</p>

## Step 3: Table to Derive NMOS Load Curve

For NMOS:

```
VGSN = VIN − VSS
```

Since:

```
VSS = 0
```

Therefore:

```
VGSN = VIN
```

Also:

```
VDSN = VOUT
```

<p align="center">
<img width="315" height="238" alt="image" src="https://github.com/user-attachments/assets/e047e1cd-7a0e-4226-8efa-b539105e4afd" />
</p>

NMOS conversion is straightforward.

## Original NMOS Curve

<p align="center">
  <img width="240" height="203" alt="image" src="https://github.com/user-attachments/assets/931557fb-99bc-4a03-b51d-9c485c1937e7" />
</p>

## After Conversion

<p align="center">
  <img width="465" height="202" alt="image" src="https://github.com/user-attachments/assets/84f27652-e854-4c87-9265-23c0d53e5ec9" />
</p>

NMOS load curve now becomes:

- Function of VIN
- Function of VOUT
- Current = IDSN

This is the **NMOS load curve**.

## Result of Step 2 & Step 3

<p align="center">
<img width="500" height="230" alt="image" src="https://github.com/user-attachments/assets/4e7426e3-5dd8-4949-b96f-807f229ede49" /> </p>

Now we have:

- PMOS load curve → IDSN vs VOUT (parameter VIN)
- NMOS load curve → IDSN vs VOUT (parameter VIN)

---

# L6 Step 4 – Merge PMOS & NMOS Load Curves and Plot VTC

## Objective

<p align="center">
<img width="497" height="215" alt="image" src="https://github.com/user-attachments/assets/a0c65714-daaf-4fd8-af27-e53b97bbe5fd" />
</p>

Generate the **Voltage Transfer Characteristics (VTC)** of a CMOS inverter  
using:

- PMOS load curve  
- NMOS load curve  

The VTC is obtained from the **intersection points** of the two load curves.

## Step 1: Superimpose Load Curves

<p align="center">
  <img width="272" height="195" alt="image" src="https://github.com/user-attachments/assets/7641bb7a-6486-44bf-a964-eec24bdd930c" />
</p>

Both PMOS and NMOS load curves:

- Are functions of **VIN**
- Are functions of **VOUT**
- Share the same current axis

To derive VTC:

- For a given VIN  
- Find the intersection of PMOS and NMOS curves  
- That intersection gives corresponding VOUT  

## Voltage Range

```
VIN  : 0 → 2 V
VOUT : 0 → 2 V
```

We sweep VIN from 0 to 2 volts and determine VOUT from intersection points.

## Case 1: VIN = 0 V

<p align="center">
<img width="1297" height="708" alt="image" src="https://github.com/user-attachments/assets/359dcfd8-5e72-4df0-882e-87bf131bfb06" /> </p>

From load curves:

- NMOS → Cutoff (OFF)
- PMOS → Linear region

Intersection point gives:

```
VOUT = 2 V
```

So:

- VIN = 0
- VOUT = 2
- PMOS → Linear
- NMOS → Cutoff

Plot this point on VTC.

## Case 2: VIN = 0.5 V

<p align="center">
<img width="1307" height="712" alt="image" src="https://github.com/user-attachments/assets/5e251dc3-efc3-4779-b44f-25cbf4316279" />
</p>

From intersection:

- PMOS → Linear region
- NMOS → Saturation region

VOUT lies between:

```
1.5 V and 2 V
```

Plot:

- VIN = 0.5
- VOUT ≈ between 1.5 and 2

## Case 3: VIN = 1 V

<p align="center">
<img width="1287" height="715" alt="image" src="https://github.com/user-attachments/assets/bab20e59-94e1-41ed-b756-f233691a89b0" /> </p>

Intersection lies near center.

Both:

- PMOS → Saturation
- NMOS → Saturation

VOUT lies between:

```
0.5 V and 1.5 V
```

This is the **sharp transition region**.

This region has:

- Very high gain
- Small change in VIN
- Large change in VOUT

This is the steep switching region of CMOS.

## Case 4: VIN = 1.5 V

<p align="center">
<img width="1297" height="716" alt="image" src="https://github.com/user-attachments/assets/a24d4627-b7e6-47fd-bec0-07ef45eff4fc" />
</p>

From load curves:

- PMOS → Saturation
- NMOS → Linear

VOUT lies between:

```
0 V and 0.5 V
```

Plot corresponding point.

## Case 5: VIN = 2 V

<p align="center">
<img width="1298" height="717" alt="image" src="https://github.com/user-attachments/assets/e055a03d-2bad-479d-9733-aaab4916f429" />
</p>

From intersection:

- NMOS → Linear
- PMOS → Cutoff

Result:

```
VOUT = 0 V
```

Plot final point.

## Constructing VTC

<p align="center">
  <img width="490" height="353" alt="image" src="https://github.com/user-attachments/assets/350f9dd5-d74a-4565-b4fc-43593cd3ff35" />
</p>

Steps:

1. Plot all intersection points
2. Connect them

This gives the **CMOS Voltage Transfer Characteristic**.

---

<br><<br>

# NgspiceSky130-Day3-CMOS switching threshold and dynamic simulations

# Voltage transfer characteristics-SPICE simulations

# L1 SPICE Deck Creation for CMOS Inverter

## What is a SPICE Deck?

SPICE Deck → Connectivity + Component Values + Nodes

A SPICE deck (netlist) contains:

- Component connectivity
- Component values
- Input definitions
- Output nodes
- Model references

It completely defines the circuit for simulation.

Previously, SPICE decks were created for a single NMOS.  

## CMOS Inverter Circuit Description

<p align="center">
<img width="465" height="461" alt="image" src="https://github.com/user-attachments/assets/b9b24a20-d5ab-4632-91b3-7e36104d6637" />
</p>

### Transistor Symbols

- PMOS symbol: Arrow pointing outward
- NMOS symbol: Arrow pointing inward

Each transistor has:

- Drain
- Gate
- Source
- Substrate terminal

The substrate terminal must also be defined in the SPICE netlist because it affects threshold voltage.

## Connectivity Description

<p align="center">
<img width="586" height="462" alt="image" src="https://github.com/user-attachments/assets/065d90e2-2749-4ec4-9656-8507455f387d" /> </p>

- PMOS source → VDD
- NMOS source → VSS
- Gates of both → Input (Vin)
- Drains connected together → Output (Vout)
- Output connected to load capacitor
- Other terminal of load capacitor → VSS

## Component Values

<p align="center"> <img width="556" height="442" alt="image" src="https://github.com/user-attachments/assets/836e6a86-4c41-41fe-9522-a646c336ed85" />
</p>

### Technology

- Channel length = 0.25 µm (250 nm technology)

### Transistor Dimensions

Both transistors initially assumed equal:

- W = 0.375 µm
- L = 0.25 µm

Although ideally:

- PMOS should be 2× or 3× wider than NMOS

For now, equal sizing is used to observe characteristics.

### Supply and Input Voltage

- VDD = 2.5 V
- Vin = 2.5 V (maximum value during sweep)

For 250 nm technology:

- Supply voltage typically around 2.5 V

## Identifying Nodes

<p align="center"> <img width="721" height="552" alt="image" src="https://github.com/user-attachments/assets/661a1422-6a37-4101-b9d5-cb2793d95a14" />
</p>

Nodes are required to define components in SPICE.

A node is:

- A point between which no component exists
- A unique electrical connection point

### Assigned Node Names

- Input node → `in`
- Output node → `out`
- Supply node → `VDD`
- Ground node → `0` (VSS)

## Writing the SPICE Deck

<p align="center"> <img width="1220" height="472" alt="image" src="https://github.com/user-attachments/assets/7f57edfc-3f7d-41e5-9f7a-56c625efd74b" />
</p>

Lines beginning with `*` are comments.

### PMOS Definition (M1)

SPICE MOS syntax:

Drain Gate Source Substrate

```
M1 out in VDD VDD PMOS W=0.375u L=0.25u
```

Explanation:

- Drain → out
- Gate → in
- Source → VDD
- Substrate → VDD
- Type → PMOS
- Width → 0.375 µm
- Length → 0.25 µm

This line completely defines the PMOS transistor.

---

# L2 SPICE Simulation for CMOS Inverter

## Component Values

<p align="center"> <img width="653" height="271" alt="image" src="https://github.com/user-attachments/assets/cbca37a9-32b0-4d29-a24d-2845884f8eac" />
 </p>

### Output Load Capacitor

```
Cload out 0 10f
```

- Between out and 0  
- Value = 10 fF  

### Supply Voltage

```
VDD VDD 0 2.5
```

- Between VDD and 0  
- Value = 2.5 V  

### Input Voltage

```
Vin in 0 2.5
```

- Between in and 0  
- Value = 2.5 V

## NMOS Description

<p align="center"> <img width="568" height="493" alt="image" src="https://github.com/user-attachments/assets/043ee861-cdaa-487e-b2d2-548f8d9e99f0" />
 </p>

### NMOS (M2)

```
M2 out in 0 0 NMOS W=0.375u L=0.25u
```

- Drain → out  
- Gate → in  
- Source → 0  
- Substrate → 0  
- Type → NMOS  
- W = 0.375 µm  
- L = 0.25 µm  

This completes transistor connectivity.

## Model File Inclusion

The model file contains complete technological parameters:

- Threshold voltage
- Oxide thickness
- Mobility
- Body effect coefficients

Model file contains:

```
.model NMOS ...
.model PMOS ...
```

Included using:

```
.include model_file.mod
```

## Simulation 

### Case 1: Equal Width PMOS and NMOS

<p align="center"> <img width="710" height="537" alt="image" src="https://github.com/user-attachments/assets/b265db13-35e8-4fe7-bacd-f7c146e2c035" />
 </p>

- Wn = 0.375 µm  
- Wp = 0.375 µm  
- Ln = Lp = 0.25 µm  


### Case 2: PMOS Width = 2.5 × NMOS Width

<p align="center"> <img width="767" height="585" alt="image" src="https://github.com/user-attachments/assets/82db499d-6195-45c6-a5ef-66934fe6a57e" />
 </p>

New PMOS width:

\[
0.375 \times 2.5 = 0.9375 \text{ µm}
\]

So:

- Wn = 0.375 µm  
- Wp = 0.9375 µm  
- Ln = Lp = 0.25 µm  

Only PMOS width changed.

---

# L3 Labs Sky130 SPICE simulation for CMOS

## DC Analysis – VTC Characteristics

We are using both PFET and NFET for the CMOS inverter.

- (W/L)p = 2.33 × (W/L)n  
- Vin sweep: 0 V to 1.8 V  
- Step size: 0.01 V  

To generate the plot:
- Type `ngspice`
- Then type `plot out vs in`

This gives the Voltage Transfer Characteristic (VTC).

<p align="center"> <img width="1600" height="1084" alt="image" src="https://github.com/user-attachments/assets/492117f0-a1b0-492c-8333-34c36841bc41" />
</p>

### Switching Threshold

Switching threshold is the point where:

Vin = Vout  

<p align="center">
<img width="654" height="499" alt="Screenshot 2026-02-27 145637" src="https://github.com/user-attachments/assets/6b1682c6-2200-4506-87ba-fff4c0b53315" />
</p>

From the graph:

Switching threshold for W/L = 2.3 is approximately:

Vm ≈ 0.876 V  

## Transient Analysis

Open the transient SPICE file (day3).

- Process corner: Typical  
- (W/L) ratio: Same as DC case  

Pulse input parameters:

- Initial value: 0 V  
- Final value: 1 V  
- Time shift: 0  
- Rise time: 0.1 ns  
- Fall time: 0.1 ns  
- Pulse width: 2 ns  
- Total time period: 4 ns  

Run the simulation.

## Delay Calculation

<p align="center">
<img width="992" height="487" alt="image" src="https://github.com/user-attachments/assets/e7a99a3d-f86f-4bbc-b27b-847c4c39b766" />
 </p>

<p align="center"> <img width="992" height="480" alt="image" src="https://github.com/user-attachments/assets/7d61b25a-dc77-4925-a5fe-9538b7204cfc" />
 </p>

For rise and fall delay:

- Consider 50% of output voltage.
- 50% of 1.8 V = 0.9 V  

### Rise Delay
  
Measure time difference at 0.9 V crossing.

Rise delay:

2.482 ns − 2.15 ns = 0.333 ns  

### Fall Delay

Measure during falling transition at 0.9 V.

Fall delay:

4.334 ns − 4.050 ns = 0.285 ns  

---

<br>

# Static behaviour evaluation-CMOS inverter robustness-Switching Threshold

# L1 Switching Threshold, Vm

## Comparison of Waveforms

<p align="center">
<img width="1198" height="578" alt="image" src="https://github.com/user-attachments/assets/963357f1-bed3-4da7-8d91-343bc98f2ddc" />
</p>

Observation:

- Shape of both curves is similar.
- Switching point shifts.
- Inverter behavior is preserved.

This confirms CMOS inverter robustness.

Whenever:

- Vin = 0 → Vout = High  
- Vin = High → Vout = Low  

The inversion property remains intact across device sizes.

## Switching Threshold (Vm)

<p align="center"> </p>

Switching threshold is defined as:

Vin = Vout

To find Vm:

<p align="center">
<img width="1195" height="490" alt="image" src="https://github.com/user-attachments/assets/0e440b67-9966-4486-8e82-a15bdcdf5630" />
</p>

### Switching Threshold – Case 1

<p align="center"> <img width="1206" height="458" alt="image" src="https://github.com/user-attachments/assets/02446376-c6ed-45cd-9f21-983f1fdd4da0" />
</p>

From waveform:
Vm ≈ 0.9 V

More precisely:
Vm ≈ 0.98 V

This corresponds to equal sizing case.

### Switching Threshold – Case 2

<p align="center"> <img width="1188" height="455" alt="image" src="https://github.com/user-attachments/assets/88225961-82ba-4330-8703-e914cbaacf53" />
 </p>

From waveform:

V_m ≈ 1.2 

Switching point shifts toward center when PMOS is stronger.


## Significance of Switching Region

The switching region is critical because:

- Vin = Vout
- Both PMOS and NMOS operate in saturation
- Both devices are turned ON

In this region:

- Direct current flows from VDD to VSS
- Short-circuit current exists
- Maximum current conduction occurs

Outside this region:

- One device OFF, one device ON
- No direct current from supply to ground

Thus, switching region is the highest current region.

## Electrical Conditions at Vm

<p align="center"> <img width="1051" height="462" alt="image" src="https://github.com/user-attachments/assets/d7cb89c6-147e-435d-91b7-534ccc2625af" />
</p>
  
At switching threshold:

IDSP = - IDSN

Currents are equal in magnitude and opposite in direction.

Also:

VGS = VDS

Devices are in saturation.

---

# L2 Analytical Expression of Vm as a Function of (W/L)p and (W/L)n

## Switching Threshold Condition

Switching threshold (Vm) occurs when:

Vin = Vout = Vm  
VGS = VDS  

At this point:

Idsp + Idsn = 0  
Idsp = −Idsn  

Both NMOS and PMOS operate in saturation.

## Drain Current Equations (λ ≈ 0)

<p align="center"> <img width="822" height="308" alt="image" src="https://github.com/user-attachments/assets/b4c5782c-00db-4642-8dc5-082b68ae248c" />
  <img width="527" height="48" alt="image" src="https://github.com/user-attachments/assets/988ecb1e-cec1-4249-ab55-57cadcb22456" />
 </p>

## Solving for Vm

Applying:

Idsp + Idsn = 0  

<p align="center"> <img width="503" height="120" alt="image" src="https://github.com/user-attachments/assets/cb12f5ca-4446-4eaa-8f4f-026d72abb777" />
</p>

<p align="center"> <img width="838" height="55" alt="image" src="https://github.com/user-attachments/assets/806cffa5-1b89-4997-aaef-7d0da5893915" />
 </p>

<p align="center"> 
 <img width="385" height="152" alt="image" src="https://github.com/user-attachments/assets/2f54324f-f32d-486a-8390-dc74858f1acf" />
</p>

## Final equation

<p align="center"> <img width="228" height="117" alt="image" src="https://github.com/user-attachments/assets/7e318695-00c5-4aee-b892-5f8f1289debe" />
</p>

---

# L3 Analytical Expression of (W/L)p and (W/L)n as a Function of Vm

## Starting Point

Previously, Vm was derived as a function of:

- (W/L)p  
- (W/L)n  

Now we reverse the process:

Given a desired Vm, determine required (W/L)p and (W/L)n.

## Current Equality at Switching Threshold

At Vm:

Idsn = −Idsp  

Using saturation-region current equations:

<p align="center">
<img width="937" height="153" alt="image" src="https://github.com/user-attachments/assets/305f344e-f1a3-41cb-ad9d-d0b4e0a830f4" /> </p>

Rearranging signs:

<p align="center">
<img width="850" height="67" alt="image" src="https://github.com/user-attachments/assets/b008af1b-f9ab-4dc5-bc72-16440ec65768" /> </p>

## Grouping Terms

<p align="center">
<img width="570" height="98" alt="image" src="https://github.com/user-attachments/assets/96840736-5ebc-4dee-8ce6-233bd467799a" />
 </p>

## Expanding Gain Factors

<p align="center">
<img width="557" height="98" alt="image" src="https://github.com/user-attachments/assets/5fef3cb9-d3ca-4356-b6e8-0bd92e57e99c" /> </p>

## Final Result

<p align="center">
<img width="556" height="113" alt="image" src="https://github.com/user-attachments/assets/817a7c37-2c53-45de-a1e3-78311b578e95" />
</p>

All terms except Vm are process constants from the model file.

Thus:

- If Vm is specified, required transistor sizing can be calculated.
- Larger desired Vm → larger (W/L)p relative to (W/L)n.
- Smaller Vm → stronger NMOS relative to PMOS.

## Example 

If:

(W/L)p = 3.75  
(W/L)n = 1.5  

Then:

(W/L)p / (W/L)n = 2.5  

This corresponds to Vm ≈ 1.2 V.

If both ratios are equal:

Vm ≈ 0.98 V.

---

# L4 Static and Dynamic Simulation of CMOS Inverter

## Objective

<p align="center"> <img width="1241" height="537" alt="image" src="https://github.com/user-attachments/assets/7fcaf76c-7645-462b-8bca-e17a01cfe599" />
 </p>

Modify PMOS size in integer multiples of NMOS and:

- Observe variation in switching threshold (Vm)
- Measure rise delay and fall delay
- Study robustness of CMOS inverter

## Static Simulation (DC Analysis)

### Circuit Parameters

- Wn = 0.375 µm  
- Wp = 0.375 µm  
- Ln = Lp = 0.25 µm  
- (W/L)n = (W/L)p = 1.5  

## Dynamic Simulation (Transient Analysis)

To evaluate delay:

- Replace DC input with pulse input
- Use transient (`.tran`) analysis

### Pulse Definition

- Initial value = 0 V
- Final value = 2.5 V
- Time delay = 0
- Rise time = 10 ps
- Fall time = 10 ps
- Pulse width = 1 ns
- Period = 2 ns
- 50% duty cycle

Pulse starts at time zero.

## Rise Delay Calculation

<p align="center"> <img width="770" height="592" alt="image" src="https://github.com/user-attachments/assets/6d553686-9c76-4dfb-a4fb-2acb6c8850b1" />
 </p>

<p align="center"> <img width="756" height="583" alt="image" src="https://github.com/user-attachments/assets/bd81fa04-4782-4909-817f-1a22599458ec" />
 </p>

From waveform:

First point (input 50% crossing):
t₁ = 1.01446 ns  

Second point (output 50% crossing):
t₂ = 1.16277 ns  

Rise delay:

t_rise = t₂ − t₁  
= 1.16277 − 1.01446  
≈ 0.148 ns  
≈ 148 ps  

## Fall Delay Calculation

<p align="center"> <img width="763" height="582" alt="image" src="https://github.com/user-attachments/assets/ccde050c-9613-4b8a-90bc-b112bafd4533" />
 </p>

<p align="center"> <img width="771" height="576" alt="image" src="https://github.com/user-attachments/assets/5adeacb8-a162-4ad3-b7d1-468d632e3c85" />
 </p>

First point:
t₁ = 2.00486 ns  

Second point:
t₂ = 2.07653 ns  

Fall delay:

t_fall = t₂ − t₁  
= 2.07653 − 2.00486  
≈ 0.071 ns  
≈ 71 ps  

---

# L5 Static and Dynamic Simulation of CMOS Inverter with Increased PMOS Width

## Case 1: PMOS = NMOS

<p align="center"> <img width="1218" height="527" alt="image" src="https://github.com/user-attachments/assets/ed219d6c-9096-4e24-9c2b-a20997fb9778" />
 </p>

- Wp = Wn = 0.375 µm  
- Lp = Ln = 0.25 µm  

Results:

- Rise delay = 148 ps  
- Fall delay = 71 ps  
- Vm ≈ 0.99 V  

## Case 2: PMOS Width = 2 × NMOS

<p align="center">  <img width="1232" height="536" alt="image" src="https://github.com/user-attachments/assets/b37b83f3-4764-4d5b-a265-11dafcb98108" />
</p>

- Wp = 0.375 × 2 = 0.75 µm  
- Lp = Ln = 0.25 µm  

### DC Analysis

<p align="center"> <img width="757" height="585" alt="image" src="https://github.com/user-attachments/assets/651725c4-d595-4e26-8dc0-8373603cbb92" />
</p>

- Plot Vout vs Vin  
- Transfer curve shifts to the right  
- Switching threshold moves right  

Vm ≈ 1.2 V  

Reason:  
PMOS becomes stronger than NMOS, increasing charging capability of load capacitor.

### Transient Analysis

Rise delay:

<p align="center"> <img width="765" height="585" alt="image" src="https://github.com/user-attachments/assets/23edbdcc-e537-4ab8-955c-60f5c5656ae0" />
 </p>

<p align="center"> <img width="765" height="582" alt="image" src="https://github.com/user-attachments/assets/e07af9cb-ae89-41a0-99bd-d9f127aeb50a" />
 </p>

- t₁ = 1.01496 ns  
- t₂ = 1.09496 ns  
- Rise delay ≈ 0.08 ns ≈ 80 ps  

Fall delay:

<p align="center"> <img width="767" height="588" alt="image" src="https://github.com/user-attachments/assets/1c99f8a4-0822-4392-8939-70e00e4ab482" />
 </p>

<p align="center"> <img width="757" height="582" alt="image" src="https://github.com/user-attachments/assets/7ece7aa9-9686-432b-85a7-fc82ac0104d6" />
 </p>

- t₁ = 2.00487 ns  
- t₂ = 2.08122 ns  
- Fall delay ≈ 0.076 ns ≈ 76 ps  

## Case 3: PMOS Width = 3 × NMOS

<p align="center"> <img width="1238" height="542" alt="image" src="https://github.com/user-attachments/assets/45afad03-d6db-49fe-8705-bf2411d87a86" />
 </p>

Results:

- Rise delay ≈ 57 ps  
- Fall delay ≈ 80 ps  
- Vm ≈ 1.25 V (near center)

## Case 4: PMOS Width = 4 × NMOS

<p align="center"> <img width="1232" height="540" alt="image" src="https://github.com/user-attachments/assets/8e9ce5df-a5c2-46fc-b791-ce94a3b03693" />
</p>

Results:

- Rise delay ≈ 45 ps  
- Fall delay ≈ 84 ps  
- Vm ≈ 1.35 V  

Switching threshold shifts further right.

## Case 5: PMOS Width = 5 × NMOS

<p align="center"> <img width="1218" height="534" alt="image" src="https://github.com/user-attachments/assets/0fe8c610-414f-454e-869f-37742d2f969a" />
</p>

Results:

- Rise delay ≈ 37 ps  
- Fall delay ≈ 88 ps  
- Vm ≈ 1.4–1.44 V  

## Summary Table

<p align="center"> <img width="710" height="235" alt="image" src="https://github.com/user-attachments/assets/92ff7d5b-495b-4ea2-8662-5fbef9bbcbdf" />
</p>

---

# L6 Applications of CMOS Inverter in Clock Network and STA

## Review of Experimental Observations

PMOS size was varied as an integer multiple of NMOS.

For each case, the following were obtained:

- Rise delay  
- Fall delay  
- Switching threshold (Vm)  

### Observation 1: Small Variation in Switching Threshold

<p align="center">
<img width="710" height="235" alt="image" src="https://github.com/user-attachments/assets/30862f30-7b36-448e-a342-79a89512b5eb" />
</p>

When PMOS size varies between nearby integers (e.g., 2× to 3× NMOS):

- Vm changes only slightly (~50 mV).
- Even fabrication variations (e.g., 4.5× becoming 4.7× or 5×) result in small Vm variation.
- CMOS inverter behavior remains intact.

This demonstrates robustness of switching threshold against process variations.

### Observation 2: Symmetry of Rise and Fall Delay

<p align="center"> <img width="1172" height="272" alt="image" src="https://github.com/user-attachments/assets/210a4374-4eec-4cec-aec5-45ee96a39db8" />
</p>

There exists a PMOS/NMOS size ratio where:

- Rise delay ≈ Fall delay  
- Switching threshold ≈ 1.2–1.25 V (near Vdd/2 for 2.5 V supply)

This symmetry is critical for clock network cells.

## Application 1: Clock Network (Clock Inverter / Clock Buffer)

<p align="center"> <img width="1177" height="267" alt="image" src="https://github.com/user-attachments/assets/d0cfcc3c-be2c-474e-b5b2-cc10fe5c6ef1" /> </p>

<p align="center"> <img width="1257" height="713" alt="image" src="https://github.com/user-attachments/assets/7440d97d-ec18-410b-9ee5-4d5ca7c89966" />
 </p>

In a clock distribution network:

- Input clock waveform must maintain symmetry.
- Rise delay must equal fall delay.
- Low-to-high delay must equal high-to-low delay.

If an inverter has unequal rise and fall delays:

- Output waveform becomes distorted.
- Duty cycle changes.
- Timing errors propagate across clock tree.

To achieve symmetry:

- PMOS must be larger than NMOS.
- PMOS is typically ~2 to 2.5× NMOS.
- This compensates for mobility differences.
- Effective resistances of PMOS and NMOS become approximately equal.

Result:

- Symmetric output waveform.
- Clock integrity preserved.

Such cells are referred to as clock inverters or clock buffers.

## Application 2: Data Path Optimization (Static Timing Analysis - STA)

<p align="center">
<img width="1123" height="285" alt="image" src="https://github.com/user-attachments/assets/3b0a2808-ad68-4a10-9b0f-2db6575dfe9d" /> </p>

<p align="center"> <img width="1278" height="692" alt="image" src="https://github.com/user-attachments/assets/9d2b962d-c299-4c52-8df1-cfd2a98d3d25" />
</p>

In data paths:

Condition for valid timing:

Data arrival time ≤ Data required time  
Slack ≥ 0  

If:

Data arrival time > Data required time  

Then:

- Combinational delay is too high.
- Path violates timing.

Solution:

- Replace inverter with a faster variant.
- Use inverter with larger PMOS size.
- Reduced rise delay improves arrival time.

Clock inverter → symmetric delays  
Regular inverters → optimized for data paths  

Tradeoff:

- Larger PMOS → faster rise
- Slightly increased fall delay
- Increased area

---

<br><br>

# NgspiceSky130-Day4-CMOS Noise Margin robustness evaluation

# Static behaviour evaluation-CMOS inverter robustness-Noise Margin

# L1 Introduction to Noise Margin

## Objective

Determine the robustness of a CMOS inverter by identifying its **noise margin**.

Noise margin is related to:

- Crosstalk noise  
- Glitches  

These effects are common in lower technology nodes.

Noise margin helps identify how robust a logic gate is against such disturbances.

## Basic Inverter Operation

For an inverter:

- Logic LOW input → Logic HIGH output  
- Logic HIGH input → Logic LOW output  

## Ideal Voltage Transfer Characteristic (VTC)

<p align="center">
 <img width="617" height="505" alt="image" src="https://github.com/user-attachments/assets/164e856c-b294-40d5-a364-3557d7d5dfec" />
</p>

Axes:

- X-axis → VIN  
- Y-axis → VOUT  

Behavior:

- VIN = 0 → VOUT = VDD  
- VIN = VDD → VOUT = 0  

Switching occurs at:

```
VIN = VDD / 2
```

## Ideal Slope at Switching Point

<p align="center">
<img width="612" height="511" alt="image" src="https://github.com/user-attachments/assets/f42d7f40-41f8-4d0a-9a39-540b30cfc9a6" />
</>

Slope definition:

```
Slope = dVOUT / dVIN
```

At switching point:

- Output changes from VDD to 0  
- Input change ≈ 0  

Therefore:

```
Slope = VDD / 0 → Infinite
```

Ideal inverter has **infinite gain** at switching threshold.

## Practical VTC

In reality:

- NMOS and PMOS have finite resistances  
- Capacitances exist  
- Transition is not instantaneous  

Result:

<p align="center">
  <img width="388" height="373" alt="image" src="https://github.com/user-attachments/assets/229ba82e-07d4-4c16-87c2-25984b5cf6a4" />
</p>

Characteristics:

- Finite slope  
- Gradual transition  
- Output does not drop exactly instantaneously  

Slope becomes finite.

## Define Important Voltage Levels

From practical VTC:

### 1️. VIL (Input Low Voltage)

<p align="center">
<img width="723" height="413" alt="image" src="https://github.com/user-attachments/assets/9f2854cc-a35e-47ad-b5d3-a80b44d5fed8" />
</p>

Range:

```
0 → VIL
```

If:

```
VIN ∈ [0 , VIL]
```

Then:

```
VOUT = VOH
```

Output remains HIGH.


### 2️. VIH (Input High Voltage)

<p align="center">
<img width="717" height="417" alt="image" src="https://github.com/user-attachments/assets/b3b67080-29eb-4faa-86af-11b1734fb44f" />
</>

Range:

```
VIH → VDD
```

If:

```
VIN ∈ [VIH , VDD]
```

Then:

```
VOUT = VOL
```

Output remains LOW.

---

# L2 Noise Margin Voltage Parameters

## Meaningful Inference from VTC

Assume:

```
VDD = 1 V
```

Let:

```
VIL  ≈ 0.25 V  (250 mV)
VIH  ≈ 0.75 V  (750 mV)
```

## Input Logic Recognition

<p align="center"> <img width="730" height="412" alt="image" src="https://github.com/user-attachments/assets/cea007d7-a3e1-4f28-b5eb-07187c222aff" /> </p>

### Logic 0 Recognition

If input voltage lies in:

```
0 → VIL   (0 → 250 mV)
```

It is recognized as:

```
Logic 0
```

### Logic 1 Recognition

If input voltage lies in:

```
VIH → VDD   (750 mV → 1 V)
```

It is recognized as:

```
Logic 1
```

## Output Voltage Requirements

<p align="center"> <img width="730" height="360" alt="image" src="https://github.com/user-attachments/assets/9715ba03-d354-4e4b-86a7-b34e9cd10905" />
</p>

Since the output of one inverter feeds the next stage:

### Output Low Voltage (VOL)

VOL must lie in:

```
0 → VIL
```

Reason:

- Next stage detects logic 0 only if input < VIL.
- Therefore:

```
VOL < VIL
```

### Output High Voltage (VOH)

VOH must lie in:

```
VIH → VDD
```

Reason:

- Next stage detects logic 1 only if input > VIH.
- Therefore:

```
VOH > VIH
```

## More Practical VTC

<p align="center">
 <img width="362" height="332" alt="image" src="https://github.com/user-attachments/assets/6ce565b2-915f-4a56-983d-bfb325f5d998" />
</p>

This curve differs from earlier near-ideal curve because:

- Non-ideal resistances exist
- Capacitances exist
- Device nonlinearities exist

Transition is curved and not straight.

## Marking VIL, VIH, VOL, VOH

<p align="center">
  <img width="361" height="335" alt="image" src="https://github.com/user-attachments/assets/245c6940-44ca-4342-a66b-de9d6224cddb" />
</p>

From the curve:

- Region 1 → VIN < VIL → VOUT ≈ VOH  
- Region 2 → Transition region  
- Region 3 → VIN > VIH → VOUT ≈ VOL  

## Slope Around Mid Region

<p align="center">
<img width="395" height="340" alt="image" src="https://github.com/user-attachments/assets/caeb1e05-587e-4f4e-8cd3-87de0df3dc51" />
</p>

Slope definition:

```
Slope = dVOUT / dVIN
```

Example:

If:

- Input increases from 100 mV → 200 mV  
- Output decreases from 900 mV → 800 mV  

Then:

```
ΔVOUT = 800 − 900 = −100 mV
ΔVIN  = 200 − 100 = +100 mV
```

Therefore:

```
Slope = −100 / 100 = −1
```

Slope in transition region ≈ −1.

---

# L3 Noise Margin Equation and Summary

## Plotting Voltage Levels on Single Scale

We place the voltage levels in descending order.

Given:

- VOH > VIH  
- VIL > VOL  

Descending order:

```
VOH
VIH
VIL
VOL
```

Reasoning:

- VOH must be greater than VIH  
  → So next stage detects logic '1'

- VOL must be less than VIL  
  → So next stage detects logic '0'


## Voltage Scale Representation

<p align="center"><img width="146" height="336" alt="image" src="https://github.com/user-attachments/assets/826a9d21-3e73-4a89-b568-abb1488fb99a" />
</p>


## Noise Margin Definitions

## 1. Noise Margin High (NMH)

<p align="center"> <img width="702" height="422" alt="image" src="https://github.com/user-attachments/assets/d2521796-2806-4a48-9fb9-0b9c1a6e516a" />
 </p>

Range:

```
VIH → VOH
```

Definition:

Any voltage in this range (at input or output) is detected as **logic '1'**

Equation:

```
NMH = VOH − VIH
```

## 2. Noise Margin Low (NML)

<p align="center"> <img width="708" height="410" alt="image" src="https://github.com/user-attachments/assets/6e1acdeb-f49a-46dc-884e-d0156e27aae4" />
 </p>
  
Range:

```
VOL → VIL
```

Definition:

Any voltage in this range (at input or output) is detected as **logic '0'**

Equation:

```
NML = VIL − VOL
```

## Undefined Region

<p align="center">
<img width="698" height="401" alt="image" src="https://github.com/user-attachments/assets/a2787f1f-eb50-4bc4-9bdb-263dabaa5f9b" /> </p>

Region between:

```
VIH and VIL
```

This is the **undefined region**.

Any voltage in this range:

- May be interpreted as logic '0'
- May be interpreted as logic '1'
- Unpredictable behavior


## Noise Bump Interpretation

<p align="center">
 <img width="927" height="536" alt="image" src="https://github.com/user-attachments/assets/43b396db-9693-410d-82d0-a90bba12442a" />
</p>

The chart summarizes noise tolerance.

### Case 1: Small Bump (Safe)

If bump height lies in:

```
VOL → VIL
```

It is still detected as **logic '0'**

Safe glitch.

### Case 2: Undefined Bump (Unsafe)

If bump height lies in:

```
VIL → VIH
```

It enters **undefined region**

- May flip logic
- Must be fixed

### Case 3: Large Bump (Logic Flip)

If bump height lies in:

```
VIH → VOH
```
It will be detected as **logic '1'**

This is harmful and must be corrected.

---

# L4 Noise Margin Variation with Respect to PMOS Width

## Objective

Understand how varying PMOS width affects CMOS inverter robustness.

## Case 1: Wp = Wn

<p align="center">
  <img width="1235" height="527" alt="image" src="https://github.com/user-attachments/assets/3b6d2095-9e2e-431a-ba90-d7c634569eaa" />
</p>

Step:

- Find points where slope = −1
- Extend tangents
- Calculate margins

Result:

```
NMH = 0.3 V
NML = 0.3 V
Vm  = 0.99 V
```

Meaning:

- Any voltage in NMH range → Logic 1
- Any voltage in NML range → Logic 0

Wider margin → More noise immunity.

## Case 2: Wp = 2Wn

<p align="center"><img width="1233" height="528" alt="image" src="https://github.com/user-attachments/assets/e1b658a9-f03d-414c-abd1-e864456b2b7f" />
 </p>

Slope −1 points identified again.

Result:

```
NMH = 0.35 V
NML = 0.3 V
Vm  = 1.2 V
```

Observation:

- NMH increased by 50 mV
- NML unchanged

Reason:

- PMOS holds charge for logic '1'
- Larger PMOS → lower resistance path to VDD
- Better ability to hold logic high

## Case 3: Wp = 3Wn

<p align="center"> <img width="1248" height="541" alt="image" src="https://github.com/user-attachments/assets/818e160b-ef20-4a28-995b-9ae2e0add448" />
</p>

Result:

```
NMH = 0.4 V
NML = 0.3 V
Vm  = 1.25 V
```

Observation:

- NMH increases further
- NML still constant

Reason:

- Stronger PMOS improves logic '1' holding capability
- NMOS responsible for logic '0'

## Case 4: Wp = 4Wn

<p align="center"> <img width="1275" height="556" alt="image" src="https://github.com/user-attachments/assets/21c9781c-5125-47f9-8b2d-8cd97661d65a" />
 </p>

Result:

```
NMH = 0.42 V
NML = 0.27 V
Vm  = 1.35 V
```

Observation:

- NMH increase is minimal (~20 mV)
- NML decreases

Reason:

- PMOS becomes much stronger than NMOS
- NMOS becomes relatively weaker
- Logic '0' holding capability reduces

## Case 5: Wp = 5Wn

<p align="center"> <img width="1258" height="551" alt="image" src="https://github.com/user-attachments/assets/80f69bce-9c57-4a83-8b98-71b4a4bc0d94" />
</p>

Result:

```
NMH = 0.42 V
NML = 0.27 V
Vm  = 1.4 V
```

Observation:

- NMH saturates
- NML slightly reduced
- Further PMOS increase does not significantly improve NMH

## Summary Table

<p align="center">
 <img width="710" height="232" alt="image" src="https://github.com/user-attachments/assets/f253db8e-705e-494b-98bd-7133ade1d03e" />
</p>

- Increasing PMOS width increases NMH.
- NML remains mostly stable.
- Excessive PMOS sizing reduces NML.
- NMH increase saturates beyond certain width ratio.

Total variation range:

```
NMH: 0.3 V → 0.42 V  (≈120 mV range)
NML: small variation (~30 mV)
```

## Fabrication Variation Insight

If designed for:

```
Wp = 2Wn
NMH = 0.35 V
NML = 0.3 V
```

Fabrication may produce:

```
Wp = 1.8Wn or 2.2Wn
```

Effect:

- Noise margin variation only ~100 mV
- Switching threshold variation small
- Overall variation ~2–3%

CMOS inverter remains robust.

## Digital vs Analog Region

### Digital Design Region

<p align="center">
  <img width="701" height="571" alt="image" src="https://github.com/user-attachments/assets/29328a1c-a029-4c07-9ef5-6fab101d0c17" />
</p>

Regions:

- NMH range → Logic 1
- NML range → Logic 0

CMOS inverter is highly suitable for digital logic.

### Analog Region

<p align="center"> <img width="708" height="571" alt="image" src="https://github.com/user-attachments/assets/2f99e363-2e71-4038-9e82-9fbf2b51bfe9" />
 </p>

Mid transition region (high gain region):

- Small change in VIN
- Large change in VOUT

Used for amplification.

---

# L5 Sky130 Noise Margin Lab

## Simulation Parameters

- Circuit: CMOS Inverter
- PMOS/NMOS (W/L) ratio: 2.77
- Input sweep: Sweeping the Vin from 0 to 1.8V with stepsize of 0.01V

<p align="center">
<img width="941" height="482" alt="image" src="https://github.com/user-attachments/assets/706c36af-29b7-4751-8639-68fb3ba85030" />
</p>

### Upper Intersection

- VIL  = 0.7733 V
- VOH  = 1.70952 V

### Lower Intersection

- VIH  = 0.98778 V
- VOL  = 0.09523 V

## Calculated Noise Margins

### Noise Margin High (NMH)

```
NMH = VOH - VIH
    = 1.70952 - 0.98778 = 0.72174
```

### Noise Margin Low (NML)

```
NML = VIL − VOL
    = 0.7733 - 0.09523 = 0.67807
```

## Final Results

- NMH ≈ 0.72174 V
- NML ≈ 0.67807 V

---

# NgspiceSky130-Day5-CMOS power supply and device variation robustness evaluation

# Static behaviour evaluation-CMOS inverter robustness-Power supply variation

# L1 Smart SPICE Simulation for Power Supply Variations

## Power Supply Scaling Concept

While evaluating CMOS inverter robustness, power supply scaling must also be considered.

When technology scales from 250 nm to lower nodes such as 20 nm, supply voltage is also scaled.

- Circuits operating at 2.5 V years back now operate at 1 V.
- Circuits operating at 1 V may operate at 0.7 V.

The CMOS inverter must behave correctly under supply scaling.

The goal of this experiment is to verify that CMOS inverter behavior does not change under reduced supply voltage and thereby prove inverter robustness.

## Inverter Setup

<p align="center">
<img width="1088" height="521" alt="image" src="https://github.com/user-attachments/assets/805fdd36-b570-4cd9-b8ac-58614a4c63e0" />
</p>

- PMOS width (Wp) = 0.9375 µm  
- NMOS width (Wn) = 0.375 µm  
- Channel length (L) = 0.25 µm  
- Load capacitor = 10 fF  
- PMOS width is greater than NMOS width to match resistances.

The same CMOS inverter configuration is used while sweeping supply voltage.

Supply voltage is swept from:

2.5 V → 2.0 V → 1.5 V → 1.0 V → 0.5 V  

Step size = 0.5 V  

The objective is to ensure inverter behavior remains unchanged under supply scaling.

## SPICE Simulation Approach

<p align="center">
<img width="633" height="457" alt="image" src="https://github.com/user-attachments/assets/50378050-744b-4008-96a1-d28b5823f553" />
  <img width="683" height="167" alt="image" src="https://github.com/user-attachments/assets/0fc1c361-fb6d-43fe-a86c-d7be083a1212" />
<img width="452" height="160" alt="image" src="https://github.com/user-attachments/assets/17419e7c-d05f-4fb6-a251-56a9c0282919" />
</p>

Instead of creating multiple SPICE netlists for different VDD values, a single SPICE netlist is used.

Everything between:

```
.control
...
.endc
```

allows scripting.

## Script Explanation 

1. `let powerSupply = 2.5`  
   Define initial supply voltage.

2. `alter Vdd = powerSupply`  
   Update VDD dynamically.

3. `let voltageSupplyVariation = 0`  
   Initialize loop counter.

4. `dowhile voltageSupplyVariation < 5`  
   Perform simulation five times.

5. `dc Vin 0 2.5 0.01`  
   Sweep input from 0 to 2.5 V.

6. `let powerSupply = powerSupply - 0.5`  
   Reduce supply by 0.5 V each iteration.

7. `alter Vdd = powerSupply`  
   Apply updated supply.

8. `let voltageSupplyVariation = voltageSupplyVariation + 1`  
   Increment loop counter.

This produces five DC simulations corresponding to:

- DC1 → 2.5 V  
- DC2 → 2.0 V  
- DC3 → 1.5 V  
- DC4 → 1.0 V  
- DC5 → 0.5 V  

## Plotting

<p align="center">
<img width="747" height="557" alt="image" src="https://github.com/user-attachments/assets/dc0703f4-d2a5-4c55-884c-3cb34ec5b5fe" /> </p>

All curves are plotted in a single command:

```
plot dc1.out vs in dc2.out vs in dc3.out vs in dc4.out vs in dc5.out vs in
```

X-axis: Input Voltage  
Y-axis: Output Voltage  

Title: Inverter DC characteristics as a function of supply voltage

---

## L2 Advantages and Disadvantages Using Low Supply Voltage

### Analysis of Supply Scaling Curves

In the previous simulation, a CMOS inverter was operated at multiple supply voltages.

Observation:

The CMOS inverter is able to operate even at 0.5 V.

Question:  
Why not use 0.5 V operation?

There are advantages and disadvantages.

### Gain Comparison (2.5 V vs 0.5 V)

Gain = (Change in Output Voltage) / (Change in Input Voltage)

To calculate gain:

1. Select two points around the region of steep slope.
2. Compute:
   - ΔVout
   - ΔVin
3. Gain = ΔVout / ΔVin

### Gain at 2.5 V

<p align="center">
<img width="926" height="552" alt="image" src="https://github.com/user-attachments/assets/28f0bb0d-4e21-45b0-a609-caf27489dc24" />
</p>

Calculated gain ≈ **7.38**

### Gain at 0.5 V

<p align="center">
<img width="923" height="547" alt="image" src="https://github.com/user-attachments/assets/df721ba7-7343-42f4-9bd3-e4f884669606" />
</p>

Calculated gain ≈ **11.53**

This corresponds to approximately **56% improvement in gain**.

Advantage:

Lower supply voltage produces a sharper transition region.  
A small change in input results in a larger change in output.

This is beneficial for analog design.


## Energy Consumption Comparison

Energy formula:

E = 1/2 C V^2

Where:
- C = Load capacitance
- V = Supply voltage

### At 2.5 V

<p align="center"> <img width="955" height="547" alt="image" src="https://github.com/user-attachments/assets/4e31daed-f300-433e-b59f-77863c837687" />
</p>
  
### At 0.5 V

<p align="center"> <img width="957" height="547" alt="image" src="https://github.com/user-attachments/assets/f85b24c4-814a-49cc-9dfd-e87b1cf7a759" />
 </p>

Energy reduction =
((2.5)^2 - (0.5)^2) / (2.5)^2 ≈ 96%

Approximately **96% reduction in energy consumption**.

Advantage:

- Significant power saving
- Beneficial for battery-powered devices

## Performance Impact (Major Disadvantage)

### Delay at 2.5 V

<p align="center"> <img width="987" height="539" alt="image" src="https://github.com/user-attachments/assets/525192e5-3ae2-4d34-ad5a-cd66f00bb640" />
 </p>

Rise delay ≈ **66 ps**  
Fall delay ≈ **78 ps**

Output capacitor charges and discharges quickly.

### Delay at 0.5 V

<p align="center"> <img width="983" height="566" alt="image" src="https://github.com/user-attachments/assets/5adab3a8-749e-4626-8b64-cf6573206f83" />
 </p>

<p align="center">
Transient response at VDD = 0.5 V
</p>

Observations:

- Output does not fully charge/discharge within same time.
- Rise time is insufficient to charge load capacitance completely.
- Reduced voltage limits charging capability.

Device becomes slower.

### Delay at 1 V 

<p align="center">
<img width="990" height="542" alt="image" src="https://github.com/user-attachments/assets/fa2ff93d-3d3c-469e-8cfe-ec03cfd6ed11" />
</p>

Rise delay ≈ **220 ps**  
Fall delay ≈ **160 ps**

This is a significant increase in delay compared to 2.5 V.

---

# L3 Sky130 Supply variation Labs

## Supply Variation Setup

Initial supply voltage:

Vdd = 1.8 V  

We reduce the supply voltage in steps of 0.2 V.

Total iterations:

1.8 V  
1.6 V  
1.4 V  
1.2 V  
1.0 V  
0.8 V  

Total = 6 iterations  

<p align="center">
<img width="1255" height="647" alt="image" src="https://github.com/user-attachments/assets/3a32680b-7434-4cc5-b922-8f71f817eb25" />
</p>

## Gain Calculation

Gain is calculated from the slope of the VTC in the transition region.

### Case 1: Vdd = 1.8 V

Selected points from VTC:

Point 1:  
x₀ = 0.78427, y₀ = 1.68571  

Point 2:  
x₀ = 0.994382, y₀ = 0.0833333  

Magnitude of Gain:

|Gain| = 7.6229  

### Case 2: Vdd = 0.8 V

Selected points from VTC:

Point 1:  
x₀ = 0.423596, y₀ = 0.771429  

Point 2:  
x₀ = 0.502247, y₀ = 0.0333333  

Magnitude of Gain:

|Gain| = 9.3844  

---

<br>

# Static behaviour evaluation-CMOS inverter robustness-Device variation

# L1 Sources of Variation – Etching Process

## Introduction

Before performing SPICE simulation for CMOS inverter variation, the sources of variation must first be identified.

Unless the exact parameters that vary the width (W) and length (L) of the CMOS inverter are identified, proper conclusions cannot be drawn.

The objective is:

1. Identify sources of variation.
2. Understand how they affect width and length.
3. Simulate CMOS inverter behavior under these variations.

## First Source of Variation: Etching Process

Etching is a fabrication step.

It is a very important fabrication step because:

- It defines the structure.
- It defines width and height of structures.
- It directly impacts delay.

The structures defined during etching determine transistor dimensions.

## CMOS Inverter Structure

<p align="center">
<img width="737" height="377" alt="image" src="https://github.com/user-attachments/assets/f54f9f6b-b3b4-4574-a198-ab705997324c" />
</p>

A CMOS inverter consists of:

- PMOS (top)
- NMOS (bottom)

If we deep dive into the transistor structure:

- PMOS diffusion area
- NMOS diffusion area
- Polysilicon gate
- Metal interconnect layers
- Contacts

Each of these elements is created through fabrication processes including etching.

## Layout View

<p align="center">
<img width="337" height="387" alt="image" src="https://github.com/user-attachments/assets/08670e0a-0c1a-412e-895c-f91780e6ecdd" />
</p>

Color representation in layout:

- Green → Diffusion region
- Yellow → Diffusion region
- Red → Polysilicon
- Blue → Metal lines
- Black cross → Contacts

Each color corresponds to a specific material layer.

The shape of every layer is defined by the etching process.

If etching is ideal → perfect rectangular shapes.  
If not ideal → distorted edges.

## Gate Length and Width

<p align="center">
<img width="352" height="407" alt="image" src="https://github.com/user-attachments/assets/14bcefdc-09b4-4733-a869-4baa71fbf40f" />
</p>

Gate Length (L):

- Defines technology node (20 nm, 45 nm, 65 nm, etc.)
- Critical dimension of the transistor.

Gate Width (W):

- Defined by overlap of gate on diffusion.
- Determines W/L ratio.
- Appears in all MOS equations.

## Chain of Inverters

<p align="center">
<img width="1281" height="658" alt="image" src="https://github.com/user-attachments/assets/d672ae35-37d1-4038-b2f1-39288c403478" />
</p>

A single inverter can be extended to a chain.

This chain may:

- Be part of datapath
- Be part of clock path
- Be connected to flip-flops

Variation in one inverter propagates across the chain.

## Ideal vs Real Fabrication

In an ideal case:

<p align="center">
<img width="507" height="597" alt="image" src="https://github.com/user-attachments/assets/01482ab0-ecb5-4328-917a-518182935ce2" />
</p>

- Edges are sharp.
- Width and length are exact.
- Area = W × L.

In real fabrication:

<p align="center">
<img width="965" height="575" alt="image" src="https://github.com/user-attachments/assets/a8fae994-ba02-4c7b-8296-4e388595ed8b" />
</p>

Due to:

- Chemicals
- Gases
- Process conditions

Edges become distorted.

Effects:

- Width changes → W'
- Length changes → L'
- Area becomes W' × L'
- Edges are not well defined.

## Accumulated Variation in Chain

<p align="center">
<img width="1231" height="327" alt="image" src="https://github.com/user-attachments/assets/42614119-ba0d-489e-8d99-65910a5b24d6" />
</p>

If one inverter has small variation:

In a long chain:

- Variations accumulate.
- Each inverter may have different distortion.
- Distortion is not repetitive.

Center gates:

- Surrounded by similar structures.
- Likely to have similar distortion patterns.

Edge gates:

- Connected to different structures.
- May experience different distortions.

Thus, variation depends on surrounding layout context.

## Impact on Drain Current

Drain current equation of MOSFET:

<p align="center">
<img width="830" height="71" alt="image" src="https://github.com/user-attachments/assets/96c39c15-5655-4909-8b76-565cabef7f8e" /> </p>

Important observation:

<p align="center">
<img width="888" height="483" alt="image" src="https://github.com/user-attachments/assets/e43c8c00-d5a3-4a40-9052-916562c236c9" /></p>

Therefore:

- Any variation in W
- Any variation in L

Directly impacts drain current.

Thus:
Etching variation → W/L variation → Drain current variation → Delay variation.

---

# L2 Sources of Variation – Oxide Thickness

## Introduction

<p align="center">
<img width="928" height="455" alt="image" src="https://github.com/user-attachments/assets/cf23a262-685e-41b5-aa4f-c7224e9eda16" /> </p>

The second source of variation is oxide thickness.

An inverter is used again as the reference structure.

To understand oxide variation, we examine the **cross-sectional view** of a transistor.

## Cross-Sectional View of MOSFET

<p align="center">
<img width="748" height="357" alt="image" src="https://github.com/user-attachments/assets/62a2afbe-e68d-41bc-9eb3-c7c7686aaf14" />
</p>

From the cross-section:

- Polysilicon (or metal) gate
- Gate oxide beneath the gate
- Source terminal
- Drain terminal
- Diffusion regions
- Substrate

The region of interest is the **gate oxide layer**.

Oxide thickness variation occurs in this region.

## Ideal Oxidation Process

<p align="center">
<img width="716" height="592" alt="image" src="https://github.com/user-attachments/assets/7ffbc5fb-cc31-4f50-b7a9-31fa830ca09a" />
</p>

In an ideal oxidation process:

- Gate oxide thickness is constant.
- Thickness is uniform across the entire channel length.
- Channel has equal oxide height throughout.

This is the expected ideal fabrication outcome.

## Real Oxidation Process

<p align="center">
<img width="857" height="487" alt="image" src="https://github.com/user-attachments/assets/2051c6ec-2052-403b-bb75-4a07ef1b1ef8" />
</p>

In real fabrication:

- Oxide thickness is not constant.
- Thickness varies along the channel length.
- Surface may appear distorted.
- Uniformity cannot be perfectly maintained.

Worst-case variation may show significant thickness deviation.

## Variation Across Multiple Transistors

<p align="center">
<img width="1237" height="267" alt="image" src="https://github.com/user-attachments/assets/882e9954-db94-4568-bfd5-cce726d50170" />
</>

Oxide thickness variation:

- Occurs in every transistor.
- Is not identical across devices.
- Differs from transistor to transistor.

Middle transistors:

- Surrounded by similar structures.
- Show relatively smaller variation.

Edge transistors:

- Exposed to different surrounding layouts.
- Show comparatively larger variation.

Thus, oxide thickness variation is layout dependent.

## Impact on Drain Current

Drain current equation:

<p align="center">
<img width="830" height="71" alt="image" src="https://github.com/user-attachments/assets/96c39c15-5655-4909-8b76-565cabef7f8e" /> </p>

Now:

<p align="center">
<img width="796" height="72" alt="image" src="https://github.com/user-attachments/assets/6887074c-0738-4b6d-8503-4013da568ee0" />
</p>

Therefore:

- Variation in oxide thickness \( t_{ox} \)
- Causes variation in oxide capacitance \( C_{ox} \)
- Causes variation in drain current \( I_D \)

More oxide thickness variation → More drain current variation.

---

# L3 Smart SPICE Simulation for Device Variations

## Objective

The next task is to identify how change in **drain current** affects CMOS inverter behavior.

Ideally, CMOS inverter should not be highly responsive to device variation.  
CMOS inverter robustness means:

- It should be least responsive to device variation.
- It should remain stable for logic gate building.
- It should remain usable for dynamic simulations.

This must be proven using SPICE simulation.

## Experimental Plan

We test **extreme device conditions**.

### Case 1: Strong PMOS and Weak NMOS

<p align="center"> <img width="353" height="217" alt="image" src="https://github.com/user-attachments/assets/c186d65c-8453-4253-ae0c-7c22e5d71f0b" />
</p>

- PMOS width = **1.875 µm** (maximum available)
- NMOS width = **0.375 µm** (minimum available)

Strong PMOS:
- Wider device
- Lower resistance
- Provides low resistance path to charge output capacitance

Weak NMOS:
- Smaller width
- Higher resistance

Assumption:
- 1.875 µm → maximum fabricable width
- 0.375 µm → minimum fabricable width

### Case 2: Weak PMOS and Strong NMOS

<p align="center"> <img width="336" height="217" alt="image" src="https://github.com/user-attachments/assets/25717211-4215-4561-8211-01504a0d369a" />
</p>

- PMOS width = **0.375 µm**
- NMOS width = **1.875 µm**

Weak PMOS:
- Highest resistance

Strong NMOS:
- Lowest resistance

## Sweep Strategy

<p align="center"> <img width="1131" height="217" alt="image" src="https://github.com/user-attachments/assets/8a9f093a-3ce2-4c1e-a7a1-223c6baee318" />
 </p>

We sweep:

- PMOS width from **1.875 µm → 0.375 µm**
- NMOS width from **0.375 µm → 1.875 µm**

Step size = **0.375 µm**

Total iterations = **5 simulations**

For each step:
- Draw DC transfer characteristics
- Observe impact of extreme device variation

## SPICE Netlist Setup

### Device Definitions

- PMOS initial width = 0.375 µm (will be altered)
- NMOS initial width = 0.375 µm
- Channel length = 0.25 µm

## .control Section Logic

Everything between `.control` and `.endc` allows scripting.

### Variables

- `let nmoswidth = 0.375`
- `let pmoswidth = 1.875`
- `let widthvariation = 0`

Loop runs **5 times**.

### Loop Operation

For each iteration:

1. Perform DC sweep.
2. Echo current NMOS width.
3. Echo current PMOS width.
4. Increase NMOS width by 0.375 µm.
5. Decrease PMOS width by 0.375 µm.
6. Alter transistor widths using `alter`.
7. Increment variation counter.

## Simulation Output

<p align="center">
<img width="760" height="583" alt="image" src="https://github.com/user-attachments/assets/bd973e8e-8868-42e1-8e0e-6a0630e3eee1" />
</p>

Results:

- **dc1** → Strong PMOS + Weak NMOS
- **dc5** → Weak PMOS + Strong NMOS
- Other curves lie between these two extremes

These curves show inverter response under extreme width variation.

---

# L4 Conclusion

## Switching Threshold Analysis

To determine switching threshold:

<p align="center">
<img width="828" height="603" alt="image" src="https://github.com/user-attachments/assets/59263d4f-1825-4784-9c99-ec52d9469364" />
</p>

From the curves:

- One extreme case gives switching threshold ≈ 0.2 V
- Other extreme case gives switching threshold ≈ 1.4 V

Total variation ≈ 1.2 V

### Interpretation

<p align="center">
<img width="1082" height="600" alt="image" src="https://github.com/user-attachments/assets/9b87dfe6-60e3-4d52-bc0b-f1097e57f7ea" />
</p>

Even though switching threshold shifts:

- The inverter still behaves as an inverter.
- It does not convert into another logic gate.
- Operation remains intact.

If inverter was designed for:

- Switching threshold ≈ 0.4 V  
or
- Switching threshold ≈ 1.4 V  

Even with device variation:

- The shift remains within tested range.
- Inverter behavior is preserved.

The shift is minimal compared to supply voltage.


## Noise Margin Analysis

<p align="center"> <img width="1043" height="602" alt="image" src="https://github.com/user-attachments/assets/be384109-5ef5-4cd6-b46d-764a281c8852" />
 </p>

### High Noise Margin

From curve:

- VOH ≈ 2.5 V
- VIH ≈ 2.1 V

Noise Margin High:

\[
NMH = 2.5 - 2.1 = 0.4 V
\]

≈ 400 mV

This is large enough to tolerate:

- Supply noise
- Voltage ripple

### Low Noise Margin

From curve:

- VOL ≈ 0 V
- VIL ≈ 0.3 V

Noise Margin Low:

\[
NML ≈ 0.3 V
\]

≈ 300 mV

This is sufficient to tolerate:

- Ground bounce
- Voltage droop
- Low-level noise

## Behavior Under Extreme Device Variation

Even when sweeping:

- Strong PMOS → Weak PMOS
- Weak NMOS → Strong NMOS

Observations:

- Noise margin variation is small.
- High margin varies ≈ 300 mV.
- Low margin varies ≈ 100 mV.
- Still within acceptable limits.

If noise margin had shifted into the high-gain undefined region:

- Inverter could enter metastable region.
- Logic state could become undefined.

However, this does not happen. Noise margin stays outside undefined region.
Thus, inverter remains stable.

## Final Observation

<p align="center"> <img width="555" height="202" alt="image" src="https://github.com/user-attachments/assets/a8d66287-49b3-449d-a0f5-2bcf16a6f941" />
</p>

Even with:

- Supply voltage variation
- Device width variation
- Extreme corner testing

CMOS inverter operation remains intact.

It always behaves as:

- Logic inverter
- Not another logic gate
- Not an undefined element

---

# L5 Sky130 device variations labs

<p align="center">
<img width="1148" height="560" alt="image" src="https://github.com/user-attachments/assets/f1674a69-3d8a-479b-a7d1-28987fa35143" />
</p>



This demonstrates CMOS inverter robustness.
