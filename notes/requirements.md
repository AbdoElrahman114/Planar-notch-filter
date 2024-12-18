# **Real-World Planar Notch Filter Requirements**

When designing a planar notch filter, several parameters and requirements must be clearly specified to ensure the design meets its intended purpose. Below is a list of commonly required specifications and details based on real-world scenarios:

---

## **Core Requirements**

1. **Center Frequency ( f_0 )**:

    - Our Design: 2.4 GHz (Wi-Fi suppression).
    - Determines the frequency at which the filter exhibits maximum attenuation.

2. **Bandwidth ( Delta f )**:

    - Example: 20 MHz to 50 MHz.

        - A bandwidth of 50 MHz (2.375 GHz to 2.425 GHz) is a good choice for selectively suppressing interference in the 2.4 GHz Wi-Fi band ,
          while minimally affecting adjacent frequencies like Bluetooth (2.402–2.480 GHz).
        - Passband Bandwidth = 2 \* StopBand Bandwidth
        - fs1 = 2.425 Ghz, fs2 = 2.375 Ghz, fp1 = 2.45 Ghz, fp2 = 2.35 Ghz

    - Defines the range of frequencies around ( f0 ) that are suppressed. Narrow bandwidth ensures minimal impact on adjacent frequencies.

3. **Rejection Level & Attenuation**:

    - As = 30dB, Ap = 0.5dB
    - Rejection level outside the band:

        - Passband attenuation: Keep the attenuation low (e.g., <1 dB) for frequencies outside the rejection band to minimize signal loss.

    - Minimum Attenuation at f0
        - Suggested Value: >30 dB
        - Ensures significant suppression of unwanted signals at the center frequency.
        - For high-interference environments, aim for 40 dB.

4. **Insertion Loss**:

    - Example: <1 dB outside the notch band.
    - Ensures minimal loss for frequencies outside the suppressed range.

5. **Reflection Coefficient ( S{11} )**:

    - Example: < -15 dB outside the notch band.
    - Ensures good impedance matching for frequencies outside the suppression range.

6. **Characteristic Impedance**:
    - Standard Value: 50 Ω.
        - Ensures compatibility with most RF systems, such as antennas, cables, and measurement equipment

---

## **Substrate and Physical Parameters**

1. **Substrate Material**:

    - Examples: FR4, Rogers RO4003C, or Duroid 5880.
    - Key Properties:
        - Dielectric constant `epsilon_r`: 4.4 (FR4), 3.38 (RO4003C).
        - Thickness `h`: 1.6 mm.
        - Loss tangent `tan(delta)`: 0.0027 (RO4003C).

2. **Conductor Properties**:

    - Example: Copper with 35 µm thickness.
    - Determines the quality of signal transmission and skin effect losses.

3. **Resonator Geometry**:
    - Examples: Open-loop, hairpin, or stub resonators.
    - Defines the type of resonant structure to achieve the notch characteristics.

---

## **Simulation and Testing Requirements**

1. **Simulation Tool**:

    - Example: HFSS, CST Studio Suite, or Keysight ADS.
    - Essential for designing and optimizing the filter before fabrication.

2. **Performance Metrics**:

    - `S{21}` : Evaluate notch depth and bandwidth.
    - `S{11}`: Ensure proper impedance matching.

3. **Measurement Equipment**:
    - Vector Network Analyzer (VNA) to measure the fabricated prototype.

---

## **Environmental and Application-Specific Requirements**

1. **Operating Temperature**:

    - Example: -40°C to 85°C for industrial environments.
    - Ensures stability under varying conditions.

2. **Power Handling**:

    - Example: Up to 1 W for standard communication systems.
    - Determines the maximum input power the filter can handle without degradation.

3. **Size Constraints**:

    - Example: Maximum dimensions of \( 20 \, \text{mm} \times 20 \, \text{mm} \).
    - Especially critical for integration into compact devices.

4. **Cost Considerations**:
    - FR4 is cost-effective but has higher losses compared to RO4003C.

---

## **Potentially Missed Details**

If the above requirements are incomplete, ensure the following are addressed:

1. **Fractional Bandwidth**:

    - \( \text{FBW} = \Delta f / f_0 \).
    - Provides a normalized measure of bandwidth.

2. **Tolerance Levels**:

    - Specify allowable deviations in center frequency and bandwidth after fabrication.

3. **Q Factor**:

    - High Q factor indicates a sharp notch and minimal bandwidth, important for interference suppression.

        - Q-factor of the filter:
        - The quality factor (Q) determines the sharpness of the notch:
            - Q= f0/Bandwidth
        - For a 20 MHz bandwidth at 2.4 GHz2.4GHz, Q ≈ 120.

4. **Coupling Mechanism**:

    - E.g., edge coupling or direct-coupled resonators.
    - Impacts the bandwidth and insertion loss.

5. **EM Shielding Requirements**:

    - If the filter is used in noisy environments, shielding might be necessary.

6. **Design Margin**:
    - Account for variations due to manufacturing tolerances or environmental factors.

---

Let me know if you’d like more specific examples or guidance on any of the parameters!
