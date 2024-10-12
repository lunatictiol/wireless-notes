**Mobile Radio Propagation: Introduction Notes**

1. **Definition**:  
   Mobile radio propagation refers to how radio signals travel from a transmitter to a receiver in mobile communication environments. This includes interactions with obstacles such as buildings, vehicles, and other objects in urban, suburban, or rural settings.

2. **Challenges in Mobile Radio Propagation**:
   - **Multipath Propagation**: Signals can take multiple paths due to reflections, refractions, and scattering from obstacles, leading to signal fading or phase shifting.
   - **Shadowing**: Large obstacles, like buildings or hills, can block signals, causing attenuation (signal loss) known as shadowing.
   - **Doppler Shift**: Movement of the receiver or transmitter causes a frequency shift (Doppler effect), which affects signal quality.
   
3. **Propagation Models**:
   - **Free-space model**: Idealized model assuming no obstacles, where signal strength decreases with the square of the distance from the source.
   - **Empirical models**: Based on observations in specific environments (e.g., urban or rural), including models like Okumura-Hata and COST 231.
   - **Ray tracing models**: Used in complex environments to simulate the paths a signal might take, including reflections, diffractions, and scatterings.

4. **Types of Propagation Environments**:
   - **Line-of-sight (LOS)**: A direct, unobstructed path between the transmitter and receiver. This is the simplest form of radio propagation.
   - **Non-line-of-sight (NLOS)**: Occurs when obstacles block the direct path, causing the signal to reach the receiver via reflections or diffraction.

5. **Propagation Mechanisms**:
   - **Reflection**: Occurs when a wave encounters a large, smooth object (e.g., buildings), causing the wave to bounce off the surface.
   - **Diffraction**: Bending of waves around obstacles, allowing signals to be received even when there's no direct LOS.
   - **Scattering**: Happens when the radio wave hits small objects or irregular surfaces, leading to the dispersal of the signal in many directions.

6. **Signal Fading**:
   - **Fast Fading**: Rapid fluctuations in signal strength over short time periods or small distances, often due to multipath propagation.
   - **Slow Fading (Shadowing)**: Signal strength varies slowly as the receiver moves through large objects or areas with heavy obstructions.

7. **Path Loss**:  
   Path loss describes the reduction in power density of a signal as it propagates through space. Path loss depends on frequency, distance, and the propagation environment. Some models to calculate path loss include:
   - **Free-Space Path Loss Model**.
   - **Log-Distance Path Loss Model**.
   - **Log-Normal Shadowing Model**.

8. **Impact of Frequency**:  
   Higher frequencies generally experience greater path loss, more susceptibility to blockage, and reduced range, but can carry more data. Lower frequencies travel further and penetrate obstacles better but have lower data capacity.

9. **Radio Wave Propagation in Different Environments**:
   - **Urban Areas**: High building density causes significant reflection and diffraction, leading to NLOS propagation and high path loss.
   - **Suburban Areas**: Less dense than urban areas, with a mix of LOS and NLOS conditions, moderate path loss.
   - **Rural Areas**: Mostly LOS conditions with fewer obstacles, resulting in lower path loss but over greater distances.

10. **Key Factors Influencing Propagation**:
    - **Frequency of operation**.
    - **Environment type (urban, suburban, rural)**.
    - **Transmitter and receiver heights**.
    - **Distance between transmitter and receiver**.
    - **Power of the transmitted signal**. 

These notes give a basic overview of mobile radio propagation, introducing its key concepts and challenges in communication systems.

### **Large Scale Path Loss: Free Space Propagation Model**

The Free Space Propagation Model is used to predict the signal strength over a distance in an idealized, obstacle-free environment. This model assumes there is a clear, unobstructed line-of-sight (LOS) between the transmitter and receiver, making it one of the simplest radio propagation models.

#### **Key Concepts**:

1. **Free Space**:  
   Free space refers to an environment where no objects (buildings, terrain, etc.) cause reflection, diffraction, or scattering of the radio waves. The propagation of electromagnetic waves occurs directly without interference from obstacles.

2. **Path Loss**:  
   Path loss represents the reduction in signal power as the signal propagates through space. In free space, the signal strength decreases as the distance between the transmitter and receiver increases.

3. Free Space Path Loss (FSPL) Formula:

   FSPL (dB) = 20 log10(d) + 20 log10(f) - 147.55

   Where:
   - d = distance between the transmitter and receiver (in meters).
   - f = frequency of the signal (in MHz).
   - The constant 147.55 converts the result into dB based on specific units.

   Alternatively, it can be written as:

   FSPL (dB) = 32.44 + 20 log10(d) + 20 log10(f)

   - The constant 32.44 assumes the frequency is in MHz, and distance is in kilometers.

4. Explanation of the Equation:
   - The first term 20 log10(d) accounts for the loss as the signal travels over distance. Signal strength decreases with the square of the distance.
   - The second term 20 log10(f) reflects how higher frequencies suffer more attenuation in free space. Higher frequencies lead to greater path loss.
   - The constant term adjusts the equation for practical units and ensures that the result is in decibels (dB).


4. **Explanation of the Equation**:
   - The **first term** \( 20 \log_{10}(d) \) accounts for the loss as the signal travels over distance. Signal strength decreases with the square of the distance.
   - The **second term** \( 20 \log_{10}(f) \) reflects how higher frequencies suffer more attenuation in free space. Higher frequencies lead to greater path loss.
   - The **constant** term adjusts the equation for practical units and ensures that the result is in decibels (dB).

#### **Assumptions of the Free Space Propagation Model**:
- **No obstacles** between the transmitter and receiver (perfect line-of-sight).
- **Isotropic antennas**: The model assumes the transmitter radiates energy uniformly in all directions.
- **Homogeneous medium**: The signal is propagating in a vacuum or an idealized space where atmospheric effects like refraction, diffraction, and scattering are neglected.

#### **Advantages of the Free Space Model**:
- **Simple and easy to calculate**.
- **Effective for satellite communications** and high-frequency line-of-sight links like microwave links, where obstacles are minimal.

#### **Limitations**:
- **Idealized**: It doesn’t account for the real-world complexities like buildings, trees, or terrain, which may affect signal propagation.
- **Only applicable in LOS scenarios**: It cannot predict signal loss in environments where multipath, reflection, or diffraction occur (e.g., urban settings).

#### **Applications**:
- **Satellite communications**: Where signals travel through space without interference.
- **Microwave links**: Often involve LOS propagation over large distances.
- **Outdoor communication systems**: In rural or flat areas where obstacles are limited.

The Free Space Propagation Model offers a foundational understanding of how signals behave in the simplest scenario. However, in practical mobile communication systems, more complex models that account for obstacles and environmental factors are typically required.

### **Outdoor Propagation Models: Longley-Rice Model and Okumura Model**

Both the Longley-Rice and Okumura models are used to predict signal propagation in real-world environments where obstacles, terrain, and other factors play a role. These models help in understanding how radio signals attenuate over different distances and through various terrain types, which is crucial for designing reliable communication systems.

---

### **1. Longley-Rice Model** (Irregular Terrain Model - ITM)

#### **Overview**:
The Longley-Rice model is a widely used empirical model for predicting radio signal propagation over irregular terrain. It is designed to work in both **line-of-sight (LOS)** and **non-line-of-sight (NLOS)** conditions. The model accounts for variations in terrain, ground cover, and other environmental factors, making it more applicable to real-world scenarios than simpler models like the Free Space Propagation Model.

#### **Key Characteristics**:
- **Frequency Range**: Typically works between 20 MHz and 20 GHz.
- **Distance**: Works for distances between 1 km and 2000 km.
- **Terrain Consideration**: Takes into account terrain profiles, including hills, mountains, valleys, and other surface irregularities.
- **Two Modes of Operation**: 
  - **Point-to-point mode**: Provides a detailed prediction for specific transmitter-receiver pairs, considering the exact terrain profile.
  - **Area mode**: Provides general predictions over a broad area using statistical data for terrain and other factors.

#### **Factors Considered**:
- **Terrain roughness**: Elevation, type of terrain, and irregularities are incorporated.
- **Atmospheric effects**: Refraction, diffraction, and other atmospheric effects are included.
- **Ground conductivity and dielectric constants**: The properties of the ground affect the propagation of the signal.
- **Fresnel zones**: Determines the influence of obstacles near the line-of-sight path.

#### **Path Loss Calculation**:
The Longley-Rice model doesn't have a simple closed-form equation like the Free Space model. Instead, it uses complex numerical methods and terrain data to predict the signal's attenuation over a given path.

#### **Applications**:
- **Television broadcast planning**.
- **Point-to-point communication links**.
- **Long-distance communication systems** over various terrains.

#### **Limitations**:
- Requires detailed information about the terrain profile.
- Computationally intensive compared to simpler models.

---

### **2. Okumura Model**

#### **Overview**:
The Okumura model is an empirical model developed in the 1960s, primarily for predicting radio signal strength in urban, suburban, and rural areas. It is particularly useful for mobile communications, providing predictions for both LOS and NLOS conditions. The model is based on extensive field measurements taken in Tokyo and surrounding areas, making it highly effective in environments with obstacles.

#### **Key Characteristics**:
- **Frequency Range**: Applicable for frequencies between 150 MHz and 1920 MHz (though extensions for higher frequencies exist).
- **Distance**: Best for distances between 1 km and 100 km.
- **Environment Types**: Works in urban, suburban, and rural environments. 
- **Correction Factors**: Provides correction factors for different types of terrain and environmental conditions (e.g., urban clutter, rural flat areas).

#### **Okumura’s Path Loss Formula**:
The basic formula for path loss in the Okumura model is:

\[
L = L_f + A_m(u) - G_h(b) - G_h(m) - G_{\text{area}}
\]

Where:
- \( L \) = path loss (in dB).
- \( L_f \) = free-space path loss at a distance \( d \) (in dB).
- \( A_m(u) \) = median attenuation relative to free space (obtained from empirical curves).
- \( G_h(b) \) = base station antenna height gain factor.
- \( G_h(m) \) = mobile station antenna height gain factor.
- \( G_{\text{area}} \) = gain due to the type of environment (urban, suburban, rural).

#### **Key Parameters**:
- **Base Station Antenna Height**: Higher antennas reduce path loss.
- **Mobile Station Antenna Height**: Similar to the base station, a higher mobile antenna helps improve signal reception.
- **Distance**: Path loss increases with distance, but the rate of increase varies based on the environment.
- **Frequency**: Path loss increases with frequency, as higher frequencies are more susceptible to attenuation.

#### **Environment Types**:
- **Urban Areas**: High path loss due to buildings and other obstacles.
- **Suburban Areas**: Moderate path loss, less than urban areas but more than rural areas.
- **Rural Areas**: Least path loss due to fewer obstacles like buildings.

#### **Advantages**:
- **Real-world measurements**: Based on extensive field data, making it more accurate for mobile systems.
- **Broad applicability**: Effective in a variety of environments, especially for mobile networks in urban, suburban, and rural settings.
  
#### **Limitations**:
- **Outdated for modern systems**: It was developed in the 1960s, so adjustments are needed for modern higher-frequency systems (above 2 GHz).
- **Complexity**: Requires interpolation from empirical curves, making it less straightforward than some other models.

#### **Extensions**:
- **Hata Model**: The Okumura model was later simplified and extended by Hata to make it more manageable for practical use in designing cellular systems.

#### **Applications**:
- **Cellular network planning**: Widely used for predicting signal strength and coverage in mobile communications.
- **Broadcast systems**: Effective for planning radio and TV broadcasts over a broad geographic area.

---

### **Comparison of Longley-Rice and Okumura Models**

| **Feature**                     | **Longley-Rice Model**                  | **Okumura Model**                  |
|----------------------------------|-----------------------------------------|------------------------------------|
| **Frequency Range**              | 20 MHz - 20 GHz                         | 150 MHz - 1920 MHz                |
| **Distance Range**               | 1 km - 2000 km                          | 1 km - 100 km                     |
| **Terrain**                      | Highly detailed (irregular terrain)      | Urban, suburban, rural (generalized terrain) |
| **Accuracy**                     | High for long distances and irregular terrain | Empirical, effective for urban and suburban environments |
| **Computational Complexity**     | High (numerical methods, terrain data)   | Moderate (requires interpolation from curves) |
| **Use Case**                     | Long-distance point-to-point communication | Mobile communication systems (urban/suburban) |

---

Both models provide crucial insights into radio wave propagation in outdoor environments, but each has its strengths depending on the terrain and the communication system's requirements. The Longley-Rice model is well-suited for complex terrain, while the Okumura model is more practical for mobile communication in built-up areas.

### **Small Scale Fading and Multipath Propagation**

**Small-scale fading** refers to the rapid fluctuations in signal strength over short distances or time intervals. It occurs due to **multipath propagation**, where a transmitted signal reaches the receiver through multiple paths (direct, reflected, diffracted, or scattered). The superposition of these paths leads to constructive and destructive interference, causing the signal strength to vary significantly.

---

### **Factors Influencing Small Scale Fading**

Several factors contribute to small-scale fading:

1. **Multipath Propagation**:
   - The signal arrives at the receiver through multiple paths, such as direct paths, reflected paths (from buildings, ground, etc.), diffracted paths (around obstacles), and scattered paths (off irregular objects).
   - These multipath signals combine at the receiver, leading to either constructive or destructive interference. Destructive interference causes signal cancellation (fading), while constructive interference enhances the signal.

2. **Relative Speed between the Transmitter and Receiver**:
   - When the transmitter or receiver is in motion, the frequency of the received signal changes due to the **Doppler Effect**. This frequency shift affects the signal quality and contributes to fading.
   - The faster the movement, the more rapid the fluctuations in signal strength.

3. **Transmission Bandwidth**:
   - Signals with larger bandwidths are more resilient to small-scale fading. However, narrowband signals (single frequency or small range) are more prone to destructive interference caused by multipath propagation.

4. **Receiver Antenna Position**:
   - Small movements of the receiver can result in significant changes in the received signal strength due to the constructive and destructive interference from multipath signals.

5. **Environment and Obstacles**:
   - The type of environment (urban, suburban, rural) affects the degree of small-scale fading. Obstacles like buildings, vehicles, or hills can block, reflect, or scatter the signal, contributing to the variation in received signal strength.

---

### **Doppler Shift**

The **Doppler Shift** refers to the change in frequency of a signal when the transmitter, receiver, or objects in the environment are in motion. This effect causes a shift in the observed frequency of the received signal.

Here’s the Doppler Shift Equation and its effects in plain text:

---

**Doppler Shift Equation**:

f_d = (v / λ) * cos(θ)

Where:
- f_d = Doppler shift (Hz).
- v = relative velocity between the transmitter and receiver (m/s).
- λ = wavelength of the signal (m).
- θ = angle between the direction of motion and the direction of the wave propagation.

**Effects of Doppler Shift**:
- **Positive Doppler Shift**: Occurs when the transmitter and receiver move towards each other, resulting in an increase in frequency.
- **Negative Doppler Shift**: Occurs when the transmitter and receiver move away from each other, leading to a decrease in frequency.
- The Doppler shift can cause frequency distortion and affect the signal quality, contributing to fast fading.

---

#### **Effects of Doppler Shift**:
- **Positive Doppler Shift**: Occurs when the transmitter and receiver move towards each other, resulting in an increase in frequency.
- **Negative Doppler Shift**: Occurs when the transmitter and receiver move away from each other, leading to a decrease in frequency.
- The Doppler shift can cause frequency distortion and affect the signal quality, contributing to fast fading.

---

### **Fast and Slow Fading**

Fading is categorized into **fast fading** and **slow fading** based on the rate at which the signal strength varies. These are influenced by factors like relative motion, multipath propagation, and Doppler shift.

#### **1. Fast Fading**:
- **Definition**: Fast fading occurs when the signal amplitude changes rapidly over short distances or time intervals, typically a fraction of a wavelength.
- **Cause**: Fast fading is primarily caused by multipath propagation, where the constructive and destructive interference of the multiple paths occurs very quickly.
- **Influence of Doppler Shift**: The Doppler shift due to relative motion between the transmitter and receiver results in rapid variations in the received signal's amplitude and phase.
- **Characteristics**:
  - High variation in signal strength within short time intervals.
  - Affects narrowband signals more severely.
  - Happens when the coherence time of the channel (the time over which the channel response is constant) is shorter than the signal duration.
  - Often experienced in high-speed environments like vehicular communication.
  
  **Example**: A signal fluctuating significantly as a user moves in a car or train.

#### **2. Slow Fading** (Shadow Fading):
- **Definition**: Slow fading occurs when the signal strength varies slowly over longer distances or time periods, often due to large obstacles like buildings, trees, or hills.
- **Cause**: Slow fading is caused by the obstruction of the signal path by large obstacles that block or attenuate the signal.
- **Influence of Doppler Shift**: Slow fading is not significantly influenced by Doppler shift because the changes in signal strength happen over longer periods and distances.
- **Characteristics**:
  - Slow, gradual variation in signal strength.
  - Caused by large objects shadowing the signal.
  - The coherence time of the channel is longer than the signal duration.
  - Affects both narrowband and wideband signals but is more noticeable in wide-area coverage.
  
  **Example**: Signal attenuation when moving behind a large building or hill, or when entering a tunnel.

---

### **Summary Table: Fast Fading vs. Slow Fading**

| **Characteristic**       | **Fast Fading**                                      | **Slow Fading**                                      |
|--------------------------|-----------------------------------------------------|-----------------------------------------------------|
| **Cause**                | Multipath propagation and Doppler shift              | Obstruction by large objects (buildings, hills)      |
| **Rate of Variation**     | Rapid changes in signal strength over short periods | Slow, gradual changes over longer periods            |
| **Environment**           | High-speed environments (e.g., vehicular movement)  | Large-scale obstructions (e.g., urban canyons, rural hills) |
| **Coherence Time**        | Short (less than the signal duration)               | Long (greater than the signal duration)              |
| **Impact**                | Affects narrowband systems more                     | Affects both narrowband and wideband systems         |
| **Doppler Effect**        | Strongly influenced by Doppler shift                | Minimal impact from Doppler shift                   |

---

Understanding small-scale fading and its causes, like multipath and Doppler shift, is essential for designing robust mobile communication systems. Techniques like diversity, equalization, and coding can mitigate the effects of fast and slow fading to improve signal quality and reliability.


### **Rayleigh Fading Distribution**

**Rayleigh fading** is a statistical model used to describe the effect of a propagation environment where there are many scattered multipath signals, and no dominant line-of-sight (LOS) component exists between the transmitter and receiver. In such environments, the signal undergoes multipath propagation, and the resulting received signal is the sum of many small reflected or scattered components. These components cause rapid fluctuations in the amplitude of the received signal.

Rayleigh fading is particularly common in urban areas or environments where signals reflect off buildings, vehicles, or other obstacles, and it is often used to model the small-scale fading effects in mobile communication systems.

---

### **Key Characteristics of Rayleigh Fading**:

1. **Multipath Propagation without Line-of-Sight**:
   - Rayleigh fading assumes no direct path between the transmitter and receiver, meaning the received signal is composed solely of reflected, scattered, and diffracted components.
   
2. **Received Signal as a Sum of Random Variables**:
   - The amplitude of the received signal is modeled as the sum of many independent and identically distributed (i.i.d.) random components. When these components are summed, their amplitudes follow a Rayleigh distribution.

---

### **Rayleigh Distribution**:

The probability distribution of the signal amplitude in a Rayleigh fading channel is given by the **Rayleigh probability density function (PDF)**. The Rayleigh distribution is applicable when the in-phase and quadrature components of the received signal are independent and normally distributed (Gaussian) with zero mean.

#### **Rayleigh PDF**:

\[
f(r) = \frac{r}{\sigma^2} e^{-\frac{r^2}{2\sigma^2}}, \quad r \geq 0
\]

Where:
- \( f(r) \) = probability density function for the received signal amplitude \( r \).
- \( r \) = received signal amplitude.
- \( \sigma \) = scale parameter, related to the variance of the underlying Gaussian components.
  
The Rayleigh PDF describes how the signal amplitude varies with probability in a multipath environment.

#### **Cumulative Distribution Function (CDF)**:

The cumulative distribution function (CDF), which gives the probability that the received signal amplitude is less than or equal to a specific value, is given by:

\[
F(r) = 1 - e^{-\frac{r^2}{2\sigma^2}}
\]

#### **Mean and Variance**:

- **Mean amplitude** (\( E[r] \)):  
  \[
  E[r] = \sigma \sqrt{\pi / 2}
  \]
  
- **Variance** (\( \text{Var}(r) \)):  
  \[
  \text{Var}(r) = (2 - \pi/2) \sigma^2
  \]

---

### **Rayleigh Fading in Communication Systems**:

Rayleigh fading models are used to simulate and analyze communication systems in environments where there is no LOS, and the signal is affected by multipath propagation. Some key aspects include:

1. **Signal Fading**:
   - Due to the superposition of multiple reflected and scattered waves, the received signal strength fluctuates rapidly, causing **fast fading**.
   - The Rayleigh distribution models the variations in the amplitude of the received signal.

2. **Flat vs. Frequency-Selective Fading**:
   - **Flat Rayleigh Fading**: Occurs when the bandwidth of the transmitted signal is smaller than the coherence bandwidth of the channel, meaning all frequency components of the signal experience similar fading.
   - **Frequency-Selective Rayleigh Fading**: Occurs when the bandwidth of the signal exceeds the coherence bandwidth, causing different frequency components to experience different levels of fading.

3. **Doppler Shift**:
   - When the receiver or transmitter is moving, the Doppler effect causes shifts in the frequency of the received signal. This leads to **Doppler spread**, which affects the coherence time and can exacerbate fast fading.

4. **BER (Bit Error Rate)**:
   - Rayleigh fading typically results in a higher bit error rate (BER) compared to channels with no fading. To combat this, techniques such as diversity, coding, and equalization are employed.

---

### **Practical Implications**:

- **Performance Degradation**: Rayleigh fading leads to significant performance degradation in wireless communication systems, especially when no countermeasures like diversity or error-correction coding are used.
- **Diversity Techniques**: One of the most effective ways to mitigate Rayleigh fading is through diversity techniques such as space, time, or frequency diversity, which aim to reduce the likelihood of all signal paths being simultaneously affected by deep fades.
- **Model Applicability**: The Rayleigh fading model is most appropriate in environments without a direct path (e.g., dense urban areas) and is less accurate for rural areas or situations where a line-of-sight path exists (where Rician fading would be more appropriate).

---

### **Summary**:

Rayleigh fading models the small-scale fading effects in environments dominated by multipath propagation, without a line-of-sight component. The amplitude of the received signal follows a Rayleigh distribution, and this model is widely used in urban environments and mobile communication systems to analyze and predict signal behavior in fading channels. Techniques like diversity and coding are used to mitigate its negative effects on communication quality.
