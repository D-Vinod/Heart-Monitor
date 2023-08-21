# Heart-Rate-Monitor

During our third semester, we successfully designed an Analog Heart Rate Monitor, bringing together the realms of technology and healthcare. The project was also showcased for **EXMO'23** the flagship technological exhibition of the University of Moratuwa as a biomedical application of electronics and technology. 

Our team, consisting of Malith, Ravindu, Umesha, and Dilupa, were able to apply our knowledge of circuit design, PCB design, enclosure design, and software integration to create a device that progresses from sensing the heart rate to amplifying and filtering the signal, culminating in the display of the refined waveform. The main circuitry of the device was developed utilizing analog electronic components, as a learning opportunity of analog electronics as well. 

With the user-friendly interface, we were able to output a patient's ECG waveform in real-time and also tune the signal when necessary. Our project's output results were compared favorably and accurately to a commercial patient monitor. With the wealth of practical and hands-on experience we've acquired, we are poised to continue making impactful contributions to the advancement of healthcare through technology.

What you can find here:

- Circuit Design
- Simulation Files
- Schematic Diagrams
- PCB Designs
- Enclosure Designs

  
## The Enclosure Design
The enclosure was designed by Solidworks software. It contains a removable top lid, a removable front, and the main body. The removability was integrated to fix and replace components. Holes surrounding the box are integrated to ensure that the heat flow to the outside of the box due to the power components inside. A fan is also connected inside to help with this. The front contains the display and also the knobs for tuning the filters. The switch on top switches off the device, and can be used for temporary situations. And the switch at the back, switches off the transformer as well, saving
the power loss that happens at the transformer. The enclosure also contains holes containing the adapters to connect the power cable and also to
connect the 3.5mm jack.

## The Circuit Design
The ECG circuit mainly consists of 5 blocks. Those are,
- Right Leg Drive Circuit
- Instrumentation Amplifier
- Low Pass Filter
- High Pass Filter
- Notch Filter

When we discuss our design approach to the circuit;

### The Right Leg Drive Circuit
The right leg drive circuit (DRL) is used to reduce common-mode interference. Common-mode interference is unwanted electrical noise that is picked up by the ECG electrodes and amplified along with the ECG signal. This noise can obscure the ECG signal and make it difficult to interpret.

The DRL circuit works by injecting a known voltage into the right-leg electrode. This voltage is equal to the common-mode voltage that is being picked up by the other electrodes. The ECG amplifier then subtracts this known voltage from the signal from the other electrodes, effectively canceling out the common-mode noise.

The DRL circuit is typically used in conjunction with other methods of noise reduction, such as filtering and shielding. The choice of which methods to use depends on the specific application.
![Right Leg Drive Circuit](images/Led Drive.png)

### Instrumentation Amplifier
An instrumentation amplifier is a critical component in our ECG circuit design. Its primary purpose is to amplify sensitive electrical signals originating from the body while minimizing distortion. This is crucial for accurate ECG signal acquisition since the electrical potentials generated by the heart are extremely low in amplitude.

The instrumentation amplifier consists of multiple operational amplifiers arranged in a specific configuration to achieve high common-mode rejection ratio (CMRR), which helps in removing unwanted noise that is picked up by the electrodes. By effectively amplifying the difference between two input signals while rejecting common-mode signals, the instrumentation amplifier improves the signal-to-noise ratio of the ECG measurement.

In addition to amplifying the ECG signal, the instrumentation amplifier also provides a means to adjust the gain as needed. This enables customization of the signal's amplitude for optimal visualization on the display.

### Low Pass Filter
We implemented a 5th order Bessel-Thompson low pass filter in our circuit. This filter is designed to attenuate high-frequency noise and unwanted components beyond a certain cutoff frequency while preserving the integrity of the ECG signal. The Bessel filter is chosen for its minimal group delay, which helps maintain the shape and timing of the ECG waveform.

The Bessel-Thompson filter comprises a series of cascaded first-order and second-order active filter stages. These stages collectively contribute to the filter's response, ensuring that frequencies beyond the cutoff are effectively attenuated while minimizing distortion and phase shift. By carefully selecting the filter's components and structure, we ensure that the amplified ECG signal is clean and devoid of high-frequency noise.

### High Pass Filter
Our ECG circuit incorporates a 3rd order active inverting Butterworth high-pass filter. This filter serves multiple purposes, including removing the DC offset that may develop between the electrodes and further amplifying the signal.

The high-pass filter's design focuses on attenuating low-frequency components, which typically include DC offset and slow baseline drift. The filter's configuration involves a cascade of a second-order active non-inverting stage followed by a first-order active inverting stage. The combined effect of these stages results in eliminating DC offset while providing additional signal amplification.

A variable resistor is integrated into the high-pass filter, allowing us to adjust the gain of the first-order filter stage according to the requirements of the specific ECG measurement.

### Notch Filter
To eliminate the interference caused by the 50 Hz power line frequency, we integrated a Twin-T type notch filter into our ECG circuit.

The Twin-T notch filter is known for its ability to provide a deep notch at a specific frequency, making it effective at eliminating power line interference. In our case, the notch frequency is set to 50 Hz to target the power line frequency. The filter's quality is determined by the Q factor, which influences the sharpness of the roll-off at the notch frequency.

To accommodate variations in the interference and notch frequency, we included a variable resistor that allows us to adjust the Q factor and achieve optimal filtering. This ensures that the ECG waveform remains free from the influence of power line noise, contributing to accurate and reliable heart rate measurements.

With these components and configurations, our analog heart rate monitor circuit is capable of capturing, amplifying, and filtering the ECG signal to produce a clean and accurate representation of the heart's electrical activity. The combination of the right leg drive circuit, instrumentation amplifier, low pass filter, high pass filter, and notch filter results in a robust ECG measurement system suitable for biomedical applications.
