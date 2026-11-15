## 1. RC example
Given R = 1 kΩ and C = 100 µF:
τ = RC = 1000 × 100 × 10⁻⁶ = 0.1 s

At 12 V, stored energy:
E = 1/2 × 100 µF × 12² = 7.2 mJ

Ideal discharge: V(t) = V0 exp(−t/τ).

| Time | Approx. voltage |
|---|---:|
| 1τ = 0.1 s | 4.41 V |
| 2τ = 0.2 s | 1.62 V |
| 3τ = 0.3 s | 0.60 V |
| 4τ = 0.4 s | 0.22 V |
| 5τ = 0.5 s | 0.08 V |

## 2. NPN LED switch
Hand-check values: Vs = 12 V, assumed LED Vf = 2 V, VCE(sat) = 0.2 V, R = 470 Ω.

IC ≈ (12 − 2 − 0.2)/470 = 20.9 mA.

Recorded LTspice values: IB = 1.922 mA, IC = 23.8 mA, VBE = 770.44 mV, VCE = 60.3 mV. The difference from the hand estimate is expected because the model's LED forward voltage and transistor operating point differ from simplified assumptions.

Forced beta = IC/IB = 23.8/1.922 ≈ 12.4. This is the forced beta in the saturated switching condition, not the transistor's datasheet active-region gain.

Recorded power checks:
- LED: approximately 17.56 mW.
- 470 Ω resistor: approximately 266 mW.
- Transistor: VCE × IC = 0.0603 × 0.0238 ≈ 1.44 mW.

The resistor dissipates more than a 0.25 W nominal rating. A 0.5 W part is the more appropriate practical selection, subject to temperature and manufacturer derating.

## 3. Common-emitter divider-bias example
Given VCC = 10 V, R1 = 30 kΩ, R2 = 10 kΩ, RE = 1 kΩ, RC = 2 kΩ, VBE ≈ 0.7 V:

VB = 10 × 10/(30 + 10) = 2.5 V
VE = 2.5 − 0.7 = 1.8 V
IE ≈ 1.8/1000 = 1.8 mA
IC ≈ 1.8 mA
VC = 10 − (0.0018 × 2000) = 6.4 V
VCE = 6.4 − 1.8 = 4.6 V

## 4. Recorded LTspice bias point
VB = 2.43 V; VC = 6.48 V; VE = 1.77 V; IB = 8.5 µA; IC = 1.75 mA; VCE = 4.71 V.

A later recorded setup gave VB = 2.436 V, IB = 8.4 µA, VC = 6.45 V and IC = 1.75 mA. IC/IB ≈ 208 for that simulated operating point; it is not a guaranteed design value.

## 5. Transient gain
Recorded base signal: 2.44126 − 2.43124 = 10.02 mVpp.
Recorded collector signal: 6.493 − 6.473 = 20.0 mVpp.

|Av| = 20.0/10.02 ≈ 1.996 ≈ 2.00.

If the waveforms are confirmed inverted, signed gain is approximately −2. For a midband gain magnitude of 1.98, the -3 dB level is 1.98 × 0.707 ≈ 1.40. The recorded 1.3999 is consistent.

## 6. Capacitive reactance
For C = 10 µF, XC = 1/(2πfC).

| Frequency | Reactance |
|---|---:|
| 100 Hz | 159 Ω |
| 1 kHz | 15.9 Ω |
