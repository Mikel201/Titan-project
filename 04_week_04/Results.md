# Week 4 Results and Analysis

## 1. RC circuit
For 1 kΩ and 100 µF, calculated τ = 0.1 s. Recorded charging observations were approximately 7.8 V after 1τ, 10.4 V after 2τ and approximately 12 V after 5τ, consistent with the exponential charging trend. The ideal discharge calculation gives 4.41 V, 1.62 V, 0.60 V, 0.22 V and 0.08 V at 1τ through 5τ.

## 2. NPN LED switching
Recorded on-state LTspice values:
- IB = 1.922 mA
- IC = 23.8 mA
- VBE = 770.44 mV
- VCE = 60.3 mV

The low VCE is consistent with saturation in the switching condition. Recorded off-state values were approximately 11.99 nV at the base, 11.99 V at the collector, 12 pA LED current and 91 fW LED power.

The 470 Ω resistor dissipated approximately 266 mW. A 0.5 W resistor is more suitable than a 0.25 W part before further thermal derating.

## 3. Common-emitter DC bias
Recorded: VB = 2.43 V, VE = 1.77 V, VC = 6.48 V, IB = 8.5 µA, IC = 1.75 mA and VCE = 4.71 V. The collector-emitter voltage is neither near zero nor near the full supply, supporting an active-region interpretation for the recorded circuit.

## 4. Common-emitter transient gain
Base waveform ≈ 10.02 mVpp. Collector waveform ≈ 20.0 mVpp. Gain magnitude ≈ 1.996, or 2.00. Common-emitter topology is expected to invert the signal; record signed gain as approximately -2 only after confirming the waveforms are opposite in phase.

Tests at 100 Hz, 1 kHz and 10 kHz were reported near 1.98. These points alone do not establish bandwidth or cutoff frequencies.

## 5. AC-analysis discrepancy — unresolved
A separate AC plot was reported near 28.91 dB with phase near 78.9°. This conflicts with the transient measurement and expected phase behaviour. The plot setup and node references were not verified. This result is **unverified** and must not be presented as confirmed performance.

## 6. Lessons
- Hand calculations are design estimates; device models and real components can differ.
- Do not confuse datasheet active-region gain with forced beta in saturation.
- Component power ratings require margin and derating.
- Establish the DC Q-point before small-signal measurements.
- Excessive input amplitude causes clipping and invalidates small-signal gain measurements.
- A frequency-response claim requires a valid sweep and measured cutoff points.

## 7. Evidence 
check the attachment for original screenshots of RC response, switch on/off states, common-emitter DC operating point and transient input/output waveforms. No screenshots or LTspice source files were allowed to be uploaded during this section preparation.
