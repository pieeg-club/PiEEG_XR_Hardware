# PiEEG_XR  

<div align="center">  
  <img src="https://github.com/pieeg-club/PiEEG_XR_Hardware/blob/main/Images/pieeg_back.png" width="30%" alt="IronBCI Demo">  
</div>  


<div align="center">
  <img src="https://github.com/Ildaron/PiEEG_XR/raw/main/Images/pieeg_xr_1.gif" width="30%" alt="IronBCI Demo">
</div>



## 🛠️ Mask Details. Electrodes Location.    
10 flat dry silver-silver chloride (Ag/AgCl) electrodes are specialized biosignal sensors used for recording surface biopotentials, ECG/EMG monitoring, and EEG research without requiring messy conductive gels  

<div align="center">
  <img src="https://github.com/pieeg-club/PiEEG_XR_Hardware/blob/main/Images/Electrodes.jpeg  " width="30%" alt="IronBCI Demo">  
</div>

Mask - Material：silicone    

<div align="center">
  <img src="https://github.com/pieeg-club/PiEEG_XR_Hardware/blob/main/Images/electrodes%20location.png" width="70%" alt="IronBCI Demo">
</div>



## 🛠️ Technical Specifications

### Hardware Architecture
*   **Analog-to-Digital Converter (ADC):** Dual **ADS1299** (supporting up to 16 (depends of version) simultaneous channels of high-resolution biopotential data).
*   **Microcontroller (MCU):** **STM32WB** series (Dual-core ARM Cortex-M4/M0+ for robust application processing and dedicated wireless stacks).
*   **Wireless Connectivity:** **Bluetooth Low Energy (BLE 5)** for low-latency, ultra-low-power data transmission.

### Signal Integrity & Electrodes
*   **Ultra-Low Noise:** **1.0 µVₚₚ** (Peak-to-Peak Noise), ensuring clean signal baselines even in challenging environments.
*   **Electrode Compatibility:** Supports both **Gel** (wet) and **Dry** electrode systems for flexible deployment.

### Software Ecosystem
*   **Backend Server:** **PiEEG Server** (for seamless data streaming, processing, and visualization).



#### Warnings
>[!WARNING]
> PiEEG_XR is not medical device. You are fully responsible for your personal decision to purchase this device and, ultimately, for its safe use. PiEEG_XR is not a medical device and has not been certified by any government regulatory agency for use with the human body. Use it at your own risk.  

>[!CAUTION]
> The device must operate only from a battery - 5 V. Complete isolation from the mains power is required! The device MUST not be connected to any kind of mains power, via USB or otherwise.   
> Power supply - only battery 5V, please read the [liability](https://pieeg.com/liability/)
>
>
#### Contacts   
https://pieeg.com/   
pieeg@pieeg.com  

#### Support
PiEEG [Discord](https://discord.gg/tEezqHXWp) 

To cite 
El Abbassi, Y.; Rakhmatulin, I. PiEEG XR: A WebXR Brain-Computer Interface Platform for Neural-Adaptive Avatar Control in Mixed Reality. Preprints 2026, 2026060016. https://doi.org/10.20944/preprints202606.0016.v1  

