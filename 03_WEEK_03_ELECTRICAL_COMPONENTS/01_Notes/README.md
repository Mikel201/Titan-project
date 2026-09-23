# Week 3 — Electrical Components & Real-World Behavior

## Overview

Week 3 focused on understanding electrical and electronic components and observing their behavior through calculations and LTspice simulations.

The main components and concepts studied were:

- Resistors
- Capacitors
- Inductors
- Diodes
- LEDs
- Transistors
- Voltage dividers
- RC circuits
- LED current limiting
- Transistor switching
- Component ratings
- Datasheet interpretation

The practical objective was to move beyond theoretical calculations and verify circuit behavior through simulation.

---

# Learning Objectives

The objectives for Week 3 were to:

- Understand the behavior of common electrical components.
- Calculate resistor values and power dissipation.
- Understand voltage-divider circuits.
- Understand capacitor charging and the RC time constant.
- Understand diode and LED forward-bias behavior.
- Calculate an appropriate current-limiting resistor for an LED.
- Understand how an NPN transistor can be used as an electronic switch.
- Read important specifications from a transistor datasheet.
- Compare theoretical calculations with LTspice simulation results.
- Observe differences between simplified calculations and component models.

---

# Tools Used

- LTspice
- Engineering calculations
- Handwritten engineering notes
- Component datasheets

---

# Lab 1 — Voltage Divider

## Objective

To verify the voltage-divider relationship using different resistor values and compare calculated output voltages with LTspice simulation results.

## Circuit Parameters

Supply voltage:

\[
V_{in}=12V
\]

Fixed resistor:

\[
R_1=1k\Omega
\]

The second resistor was varied:

- \(R_2=1k\Omega\)
- \(R_2=500\Omega\)
- \(R_2=2k\Omega\)

## Formula

The output voltage of a voltage divider is:

\[
V_{out}=V_{in}\frac{R_2}{R_1+R_2}
\]

## Results

| R1 | R2 | Calculated Vout | Simulated Vout |
|---:|---:|---:|---:|
| 1 kΩ | 1 kΩ | 6 V | 6 V |
| 1 kΩ | 500 Ω | 4 V | 4 V |
| 1 kΩ | 2 kΩ | 8 V | 8 V |

## Observation

The calculated and simulated values matched for all three configurations.

When \(R_2\) was reduced to 500 Ω, the output voltage became 4 V.

When \(R_2\) was increased to 2 kΩ, the output voltage became 8 V.

This demonstrated how changing the resistor ratio changes the output voltage of a voltage-divider circuit.

## Conclusion

The LTspice simulation verified the voltage-divider calculations.

---

# Lab 2 — RC Charging Circuit

## Objective

To observe capacitor charging behavior and verify the relationship between resistance, capacitance and the time constant.

## Circuit Parameters

Supply voltage:

\[
V_{in}=12V
\]

Resistance:

\[
R=1k\Omega
\]

Capacitance:

\[
C=100\mu F
\]

## Time Constant Calculation

The time constant is:

\[
\tau=RC
\]

Therefore:

\[
\tau=(1000)(100\times10^{-6})
\]

\[
\boxed{\tau=0.1s}
\]

The capacitor voltage during charging is described by:

\[
V_C=V_{in}(1-e^{-t/\tau})
\]

## Expected Charging Behavior

| Time | Approximate charge |
|---:|---:|
| 1τ | 63.2% |
| 2τ | 86.5% |
| 3τ | 95.0% |
| 4τ | 98.2% |
| 5τ | 99.3% |

A capacitor approaches its final voltage gradually and is considered practically fully charged at approximately 5τ.

## LTspice Results

| Time | Simulated Capacitor Voltage |
|---:|---:|
| 1τ = 0.1 s | 7.8 V |
| 2τ = 0.2 s | 10.4 V |
| 5τ = 0.5 s | ≈12 V |

## Observation

The simulation showed the expected exponential charging behavior.

The capacitor initially charged quickly and then approached the 12 V supply voltage more gradually.

At approximately 5τ, the capacitor reached approximately 12 V in the simulation.

## Conclusion

The calculated time constant of 0.1 s was verified through LTspice simulation.

The practical result demonstrated that the time constant represents the charging rate of an RC circuit rather than the exact time required for the capacitor to become fully charged.

---

# Lab 3 — LED Current-Limiting Circuit

## Objective

To calculate an appropriate resistor for an LED circuit and compare the theoretical current with the LTspice simulation.

## Circuit Parameters

Supply voltage:

\[
V_S=12V
\]

Assumed LED forward voltage:

\[
V_F=2V
\]

Target current:

\[
I=10mA
\]

## Resistor Calculation

The required resistor was calculated using:

\[
R=\frac{V_S-V_F}{I}
\]

Substituting the values:

\[
R=\frac{12-2}{0.01}
\]

\[
\boxed{R=1k\Omega}
\]

Therefore, the calculated current-limiting resistor was:

\[
\boxed{R=1k\Omega}
\]

## LTspice Results

The simulation produced:

- Operating current = **11.28 mA**
- Dissipating power = **8.098 mW**

## Comparison

| Parameter | Calculated | Simulated |
|---|---:|---:|
| Resistor | 1 kΩ | 1 kΩ |
| LED current | 10 mA | 11.28 mA |
| Power | — | 8.098 mW |

## Observation

The calculated current was 10 mA, while the LTspice operating current was 11.28 mA.

The difference demonstrates that the simplified calculation uses an assumed LED forward voltage, while the simulated component has its own electrical characteristics.

This shows why component datasheets and actual component models are important when designing practical circuits.

## Conclusion

The LED current-limiting circuit successfully operated in LTspice.

The simulation also demonstrated that theoretical calculations based on simplified component assumptions may differ from simulated component behavior.

---

# Lab 4 — NPN Transistor Switching

## Objective

To use an NPN transistor as an electronic switch and verify both ON and OFF operating states through LTspice.

## Component

Transistor:

**2N2222A**

The transistor was configured as a low-side switch.

The control voltage was applied to the transistor's base through the base resistor.

When the control voltage was HIGH, the transistor conducted and allowed current to flow through the LED.

When the control voltage was LOW, the transistor stopped conducting.

---

## ON State

Control voltage:

\[
V_{control}=5V
\]

### LTspice Results

| Parameter | Result |
|---|---:|
| Base voltage \(V_B\) | 802.25 mV |
| Collector voltage \(V_C\) | 48.89 mV |
| LED current | 25.98 mA |
| LED power dissipation | 87.71 mW |

## Observation

With the control voltage HIGH, the base-emitter junction was forward biased.

The transistor turned ON and provided a low-resistance path between the collector and emitter.

The collector voltage dropped close to ground:

\[
V_C=48.89mV\approx0V
\]

This allowed current to flow through the LED.

Therefore:

\[
Control\ HIGH
\rightarrow
Transistor\ ON
\rightarrow
LED\ ON
\]

---

# OFF State

Control voltage:

\[
V_{control}=0V
\]

### LTspice Results

| Parameter | Result |
|---|---:|
| Base voltage \(V_B\) | 11.99 nV |
| Collector voltage \(V_C\) | 11.99 V |
| LED current | 12 pA |
| LED power dissipation | 91 fW |

The base voltage was effectively zero:

\[
11.99nV\approx0V
\]

The LED current was also effectively zero:

\[
12pA\approx0A
\]

The collector voltage rose to approximately the supply voltage:

\[
V_C=11.99V\approx12V
\]

Therefore:

\[
Control\ LOW
\rightarrow
Transistor\ OFF
\rightarrow
LED\ OFF
\]

## ON/OFF Comparison

| Parameter | ON State | OFF State |
|---|---:|---:|
| Control voltage | 5 V | 0 V |
| \(V_B\) | 802.25 mV | 11.99 nV |
| \(V_C\) | 48.89 mV | 11.99 V |
| LED current | 25.98 mA | 12 pA |
| LED power | 87.71 mW | 91 fW |
| Transistor state | ON | OFF |
| LED state | ON | OFF |

## Conclusion

The LTspice simulation successfully demonstrated the operation of the 2N2222A as an electronic switch.

The circuit responded correctly to both HIGH and LOW control signals.

---

# 2N2222A Datasheet Study

## Objective

To identify important electrical and physical specifications of the transistor used in Lab 4.

The selected transistor was the:

**2N2222A**

## Datasheet Specifications

| Parameter | Value |
|---|---:|
| Maximum collector current \(I_C\) | 800 mA |
| \(V_{CEO}\) | 40 V |
| \(V_{CBO}\) | 75 V |
| \(h_{FE}\) | 75 |
| Power dissipation at 25°C | 500 mW |
| Package | TO-18 metal |
| Pin 1 | Emitter |
| Pin 2 | Base |
| Pin 3 | Collector |

## Pin Configuration

The TO-18 package used for the selected 2N2222A has:

- Pin 1 → Emitter
- Pin 2 → Base
- Pin 3 → Collector

The physical pin configuration must always be checked against the specific manufacturer's datasheet before using a transistor in a physical circuit.

---

# Datasheet Parameter Interpretation

## Maximum Collector Current

The datasheet specifies:

\[
I_C(max)=800mA
\]

This represents the specified maximum collector current under the conditions given by the manufacturer.

It should not automatically be treated as a normal operating current.

---

## Collector-Emitter Voltage

The datasheet specifies:

\[
V_{CEO}=40V
\]

This is the specified maximum collector-emitter voltage under the manufacturer's stated conditions.

---

## Collector-Base Voltage

The datasheet specifies:

\[
V_{CBO}=75V
\]

This is the specified maximum collector-base voltage under the manufacturer's stated conditions.

---

## DC Current Gain

The datasheet gives:

\[
h_{FE}=75
\]

This represents the transistor's DC current gain under the specified test conditions.

---

## Power Dissipation

The specified power dissipation at 25°C was:

\[
P_D=500mW
\]

The power rating is important when evaluating whether the transistor can safely dissipate the heat produced during operation.

---

# Theory vs Simulation

One of the main purposes of the practical work was to compare calculated values with simulated behavior.

### Lab 1

Calculated:

\[
V_{out}=4V
\]

Simulation:

\[
V_{out}=4V
\]

The results matched.

### Lab 2

Calculated:

\[
\tau=0.1s
\]

The simulation demonstrated the expected capacitor charging behavior.

### Lab 3

Calculated:

\[
I=10mA
\]

Simulation:

\[
I=11.28mA
\]

The difference demonstrated that the simulated LED model does not behave exactly like the simplified 2 V LED assumption used in the calculation.

### Lab 4

The transistor simulation demonstrated both:

**HIGH control → ON**

and

**LOW control → OFF**

The collector voltage and LED current changed accordingly.

---

# Engineering Lessons

The practical work in Week 3 demonstrated several important engineering principles:

1. Electrical calculations provide expected circuit behavior.
2. LTspice can be used to verify circuit calculations before physical implementation.
3. Components do not always behave exactly like simplified textbook models.
4. LED forward voltage is not necessarily a fixed value.
5. Capacitor charging follows an exponential relationship.
6. A transistor can be used as an electronic switch.
7. Datasheets provide important information required for component selection.
8. Maximum component ratings should not automatically be treated as normal operating values.
9. Simulation results should be investigated when they differ from calculations.
10. Engineering requires comparing theory, simulation and component specifications.

---

# Engineering Workflow

The workflow used during Week 3 was:

**Learn → Calculate → Simulate → Compare → Investigate → Document**

This workflow will continue to be used in future Project Titan work.

---

# Week 3 Practical Status

| Task | Status |
|---|---|
| Voltage Divider | ✅ Completed |
| RC Charging Circuit | ✅ Completed |
| LED Current Limiting | ✅ Completed |
| NPN Transistor Switching | ✅ Completed |
| 2N2222A Datasheet Study | ✅ Completed |
| Week 3 Assessment | 🔄 In Progress |

---

# Conclusion

Week 3 provided practical experience with passive and semiconductor components and introduced the importance of understanding real component behavior.

The four LTspice laboratories allowed theoretical calculations to be compared with simulated circuit behavior.

The 2N2222A transistor experiment demonstrated how a transistor can function as an electronic switch, while the datasheet study introduced the process of checking component ratings and physical pin configuration before using a component.

The main engineering principle developed during this week was:

> **Do not stop at the calculation. Verify the behavior, investigate differences, check the component specifications, and document the result.**

---

# Next Step

The Week 3 assessment is being completed separately to verify understanding of the concepts covered during the week.

After the assessment is completed, the results and lessons learned will be added to this documentation.
