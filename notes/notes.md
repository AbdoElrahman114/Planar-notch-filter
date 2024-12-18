# Planar Notch Filter for Wi-Fi Interference Suppression

## **Project Overview**

### **Objective:**

Design a notch filter to suppress Wi-Fi signals at 2.4 GHz with a rejection >30 dB.

### **Application:**

Reduces interference in Bluetooth and ZigBee communication systems.

---

## **1. Analysis Section**

### **1.1 Theoretical Explanation**

- **What is a Notch Filter?**  
  A notch filter is a bandstop filter designed to attenuate signals in a narrow frequency range while allowing signals outside this range to pass.

- **Relevance to Wi-Fi Interference Suppression:**  
  Wi-Fi operates at 2.4 GHz (IEEE 802.11 b/g/n) and often interferes with Bluetooth and ZigBee communication systems, which also operate in the same ISM band. Suppressing Wi-Fi signals enhances the performance and reliability of these systems.

### **1.2 Mathematical Models and Equations**

- **Quality Factor (Q):**

    ```math
    Q = \frac{f_0}{\Delta f}
    ```

    where \( f_0 \) is the center frequency (2.4 GHz) and \( \Delta f \) is the bandwidth.

- **Impedance Matching:**

    ```math
    Z_{in} = Z_0
    ```

    ensures optimal power transfer.

- **Transfer Function:**

    ```math
    H(s) = \frac{s^2 + \omega_0^2}{s^2 + \frac{\omega_0}{Q}s + \omega_0^2}
    ```

    where \( \omega_0 = 2\pi f_0 \).

- **Resonance Condition:**
    ```math
    f_0 = \frac{1}{2\pi \sqrt{LC}}
    ```

### **1.3 Importance in Microwave Engineering**

- Mitigates interference in shared-spectrum environments.
- Enhances system reliability and signal integrity for Bluetooth and ZigBee.

---

## **2. Design Section**

### **2.1 Tools**

- Use simulation software like **HFSS**, **ADS**, or **CST Studio Suite**.

### **2.2 Circuit Design**

- **Topology:** A microstrip-based planar design for compactness and easy fabrication.
- **Substrate Selection:**

    - FR4 or Rogers RO4003C for optimal dielectric properties.
    - Dielectric constant (\( \epsilon_r \)): ~4.4 (FR4).
    - Thickness (\( h \)): 1.6 mm.

- **Resonant Elements:**
  The filter design employs resonators, which are structures that create standing wave patterns at specific frequencies. These resonators are essential for achieving the desired frequency selectivity and attenuation.
  In this case:

    - **Open-loop resonators** or **stub resonators** are commonly used due to their sharp frequency response.
    - Resonators create the rejection band by introducing a high impedance path or a short circuit at the desired frequency (2.4 GHz).
    - **Stub resonators:** These are quarter-wavelength transmission lines connected either in series or parallel to the main line. They are effective for creating narrowband notch filters.

- **Key Metrics:**
    - Center frequency (\( f_0 \)): 2.4 GHz.
    - Bandwidth (\( \Delta f \)): Narrow, ensuring high rejection (>30 dB).

### **2.3 Schematics and Calculations**

- Calculate resonator dimensions based on substrate properties and frequency:
    ```math
    \lambda_g = \frac{\lambda_0}{\sqrt{\epsilon_r}}
    ```
    Design the resonator length close to \( \lambda_g/4 \).

---

## **3. Implementation Section**

### **3.1 Simulation**

- Simulate the filter in **HFSS**, **ADS**, or **CST**:
- Validate the **S-parameters** (\( S*{11} \), \( S*{21} \)): Look for a sharp dip in \( S\_{21} \) at 2.4 GHz.
- Ensure the reflection coefficient (\( S\_{11} \)) is minimal outside the rejection band.

### **3.2 Physical Prototype (Optional)**

- Fabricate the filter on a planar substrate using PCB etching or milling.
- Test performance using a **Vector Network Analyzer (VNA)**.

### **3.3 Performance Analysis**

- Key metrics:
    - **Rejection:** >30 dB.
    - **Bandwidth:** Evaluate to ensure it doesn’t affect adjacent frequencies.
    - **Resonance Frequency Accuracy:** Validate alignment with 2.4 GHz.

---

## **4. Final Report**

### **Structure:**

1. **Introduction:** Overview of the project’s objective and relevance.
2. **Theory:** Detailed explanation, mathematical background, and importance.
3. **Design:** Include schematics, calculations, and justification for design choices.
4. **Simulation Results:** Show simulation data, including \( S \)-parameters and rejection plots.
5. **Implementation:** If applicable, include fabrication details and prototype testing results.
6. **Conclusion and Future Work:** Summarize findings and suggest improvements.

### **Visual Aids:**

- Frequency response plots.
- Circuit diagrams and resonator layouts.

---
