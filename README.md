# Basic LED Circuit Simulation Using LTspice

## 1. Project Objective

The objective of this project was to design and simulate a simple DC LED circuit in LTspice in order to understand the relationship between voltage, current, and resistance, and to learn how a resistor can be used to limit the current flowing through an LED.

## 2. Circuit Components

The circuit consists of:

* DC voltage source: 5 V
* Red LED: approximately 2 V forward voltage
* Resistor: 150 Ω
* Switch

## 3. Design Calculation

The resistor was selected using Ohm's Law.

The voltage that must be dropped across the resistor is:

**Vr = Vs − Vf**

Where:

* Vs = supply voltage = 5 V
* Vf = LED forward voltage = 2 V

Therefore:

**Vr = 5 − 2 = 3 V**

The desired LED current was selected as:

**I = 20 mA = 0.020 A**

Using:

**R = Vr / I**

Therefore:

**R = (5 − 2) / 0.020**

**R = 150 Ω**

Therefore, a **150 Ω resistor** was selected.

## 4. How the Circuit Works

When the switch is open, the circuit is incomplete and current cannot flow through the LED. Therefore, the LED remains OFF.

When the switch is closed, the circuit becomes complete. Current flows from the 5 V source through the resistor and LED and returns to the voltage source.

The resistor limits the current flowing through the LED. Without appropriate current limiting, excessive current could flow through the LED and potentially damage it.

## 5. What I Learned

From this simulation, I learned that:

1. Voltage provides the electrical potential difference that drives current through a circuit.
2. Current is the flow of electric charge through the circuit.
3. Resistance limits the amount of current flowing through the circuit.
4. Ohm's Law can be used to calculate the relationship between voltage, current, and resistance.
5. An LED requires appropriate current limiting.
6. Circuit simulation allows an engineer to test a design before physically building it.

## 6. Engineering Questions

### What happens if the resistor is removed?

The resistance in the circuit would become very small, allowing excessive current to potentially flow through the LED. In a practical circuit, this could damage the LED or other components.

### What happens if the resistor value is increased?

The current through the LED decreases.

### What happens if the resistor value is decreased?

The current through the LED increases.

### What happens if the supply voltage is increased?

Assuming the resistor remains 150 Ω, the current through the LED would increase because there would be a greater voltage across the resistor.

## 7. Engineering Significance

Although this is a simple circuit, the principles demonstrated here are fundamental to more complex electrical and automation systems.

The same concepts of voltage, current, resistance, and signal control appear in:

* Sensors
* PLC inputs and outputs
* Relay circuits
* Industrial control panels
* Motor-control circuits
* Embedded systems
* Instrumentation
* Electronic control systems

This project therefore represents my first practical exercise in understanding electrical systems as part of Project TITAN.

## 8. Possible Improvements

Future versions of this project could include:

* Measuring the actual simulated current through the LED.
* Testing different resistor values.
* Comparing different supply voltages.
* Adding multiple LEDs.
* Replacing the mechanical switch with a transistor or MOSFET.
* Building the circuit physically on a breadboard.

## 9. Tools Used

**Software:** LTspice

**Simulation Type:** Transient analysis

**Circuit Type:** Simple DC LED circuit

## 10. Next Step

The next step is to investigate how voltage, current, and resistance behave in series and parallel circuits and verify the relationships experimentally using circuit simulations.
