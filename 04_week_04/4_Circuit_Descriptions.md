# Week 4 Circuit Descriptions

## RC charging/discharging
A resistor and capacitor form a first-order network. The key parameter is τ = RC. The documented example uses 1 kΩ and 100 µF, giving 0.1 s.

## LED current limiting
Connect the LED in series with a resistor and DC source. Estimate resistance from R = (Vs − Vf)/I, then verify using the LED datasheet and actual model.

## NPN low-side switch
Intended connection:
- Positive supply → current-limiting resistor → LED → transistor collector.
- Transistor emitter → circuit ground.
- Control source → base resistor → transistor base.
- Control-source ground and circuit ground share a reference.

High control turns the transistor on; low control turns it off. The recorded simulation used a 2N2222A model.

## Voltage-divider biased common-emitter stage
A resistor divider biases the base. The emitter resistor provides DC stabilization. The collector resistor converts collector-current changes into output-voltage changes. Coupling capacitors pass AC while isolating DC bias between stages.

Check the Q-point before applying AC. Excessive input amplitude can drive the transistor into cutoff or saturation and cause clipping.

## Small-signal transient test
The recorded small-signal source was `SINE(0 5m 1k)`: 5 mV peak, 10 mV peak-to-peak at 1 kHz. An earlier 5 V peak input was too large and caused clipping. Measure input and output consistently and inspect their phase relationship.
