<div align="center">

# PiEEG XR

**Bring your brain and face signals into virtual reality.**

A brain-computer interface for VR headsets: a silicone face mask with 10 dry Ag/AgCl electrodes and a Bluetooth BCI box.

[📖 Documentation](https://docs.pieeg.com/hardware/devices/PiEEG_XR/) ·
[🚀 How to Start](https://docs.pieeg.com/hardware/devices/PiEEG_XR/setup/) ·
[🌐 Try in the browser](https://cloud.pieeg.com) ·
[💬 Discord](https://discord.gg/5Ps24p47)

<img src="https://raw.githubusercontent.com/pieeg-club/PiEEG-docs/main/public/images/hardware/2026/10/pieegxr_render.jpg" alt="PiEEG XR on a Meta Quest 3: face mask and BCI box" width="560">

</div>

> [!WARNING]
> PiEEG XR is a **research device, not a medical device**, and has not been certified by any regulator for use with the human body. You use it at your own risk.

> [!CAUTION]
> **Battery only.** Power the BCI box from a **5 V power bank or a battery head strap**. Never from a wall charger, and never through a cable to a computer on mains power. Don't charge the headset while wearing it with PiEEG XR. Read the [Safety page](https://docs.pieeg.com/hardware/devices/PiEEG_XR/safety/) and the [liability notice](https://pieeg.com/liability/).

## At a glance

| | |
|---|---|
| **Channels** | 8 (PiEEG XR) or 16 (PiEEG XR-16), plus reference and bias |
| **Electrodes** | 10 flat dry Ag/AgCl in a silicone mask: 8 channels, reference, bias |
| **Converter** | TI ADS1299, 24-bit (dual ADS1299 on 16-channel versions) |
| **Sample rate** | 250 SPS |
| **Noise** | 1.0 µV peak-to-peak |
| **Microcontroller** | STM32WB (Cortex-M4 + Cortex-M0+ radio core) |
| **Wireless** | Bluetooth LE 5, appears as `PiEEG XR` |
| **Power** | 5 V over USB-C, from a power bank or battery head strap |
| **Headsets** | Meta Quest 3, Meta Quest, PICO and others. Each unit is made for one model. |
| **Software** | BodyPress (Quest, Android), [PiEEG Cloud](https://cloud.pieeg.com), [PiEEG Server](https://github.com/pieeg-club/PiEEG-server), VRChat OSC |

## How it works

```
 Face mask ──cable──► BCI box ──BLE──► Quest (BodyPress app)
 10 dry electrodes    ADS1299 +        ├ cloud.pieeg.com
 (8 ch, ref, bias)    STM32WB          ├ PiEEG Server ─OSC─► VRChat
                         ▲             └ Android (BodyPress)
     5 V power bank ─────┘
```

<img src="https://raw.githubusercontent.com/pieeg-club/PiEEG-docs/main/public/images/hardware/2026/10/pieegxr_back.jpg" alt="PiEEG XR mask and BCI box" width="560">

## Quick start

1. **Replace the face mask:** remove the headset's facial interface and snap in the PiEEG XR mask (two back buckles, then two front buckles). Or fit just the silicone insert into your own mask.
2. **Mount the BCI box** against the headset under the head strap and route the cable from the mask.
3. **Power** the box with a **USB-A to USB-C** cable from a power bank or battery strap. It starts advertising as `PiEEG XR`.
4. **Clean** the forehead and temples with an alcohol pad, put the headset on and tighten the strap.
5. **Connect:**

| Option | How |
|---|---|
| **On the Quest** | [BodyPress on the Meta Quest Store](https://www.meta.com/en-gb/experiences/bodypress/1271355469389420/) |
| **In the browser** | [cloud.pieeg.com](https://cloud.pieeg.com) in Chrome or Edge → **PiEEG Devices** → **PiEEG XR** |
| **On Android** | [BodyPress on Google Play](https://play.google.com/store/apps/details?id=com.bodypress.governorhq) |
| **PiEEG Server** | `pip install "pieeg-server[ironbci]"` then `pieeg-server --device ironbci8` |

6. **Blink hard 3–5 times.** You should see large spikes on the forehead channels.

<img src="https://raw.githubusercontent.com/pieeg-club/PiEEG-docs/main/public/images/hardware/2026/10/pieegxr_mask_steps.jpg" alt="Replacing the face mask in four steps" width="300"> <img src="https://raw.githubusercontent.com/pieeg-club/PiEEG-docs/main/public/images/hardware/2026/10/pieegxr_mount_steps.jpg" alt="Mounting the BCI box under the head strap" width="300">

Full walkthrough: **[docs.pieeg.com → PiEEG XR → How to Start](https://docs.pieeg.com/hardware/devices/PiEEG_XR/setup/)**

## Mask and electrodes

10 flat dry silver / silver-chloride electrodes, no gel needed (a little gel or saline helps during movement). Mask material: silicone.

<img src="https://raw.githubusercontent.com/pieeg-club/PiEEG-docs/main/public/images/hardware/2026/10/pieegxr_electrodes.jpg" alt="Flat dry Ag/AgCl electrodes" width="220">

<img src="https://raw.githubusercontent.com/pieeg-club/PiEEG-docs/main/public/images/hardware/2026/10/pieegxr_electrode_map.png" alt="PiEEG XR electrode positions on the mask" width="650">

| Position on the mask (as drawn) | Electrodes | Picks up |
|---|---|---|
| Left side | Ch1, Ch2 | Temple: eye movement, jaw and temple muscles |
| Left forehead | Ch3, Ch4 | Frontal EEG, blinks |
| Centre forehead | Ref, Bias | Reference and bias |
| Right forehead | Ch5, Ch6 | Frontal EEG, blinks |
| Right side | Ch7, Ch8 | Temple: eye movement, jaw and temple muscles |

All electrodes are on the front of the head, so PiEEG XR is strongest at **frontal EEG, blinks, eye movements and facial expressions**.

## Power

Use a **USB-A to USB-C** cable: some USB-C supplies don't power the box over a USB-C to USB-C cable. A **headset strap with a built-in battery** can power both the headset and PiEEG XR.

<img src="https://raw.githubusercontent.com/pieeg-club/PiEEG-docs/main/public/images/hardware/2026/10/pieegxr_cable.jpg" alt="USB-A to USB-C cable" width="200"> <img src="https://raw.githubusercontent.com/pieeg-club/PiEEG-docs/main/public/images/hardware/2026/10/pieegxr_headset.jpg" alt="Headset strap with a built-in battery" width="320">

## Brain-reactive VRChat avatar

```
 PiEEG XR ─BLE─► PiEEG Server (PC) ─OSC, UDP 9000─► VRChat ─► avatar animator
```

```bash
pip install "pieeg-server[ironbci]"
pieeg-server --device ironbci8 --osc
```

PiEEG Server sends `/avatar/parameters/EEG_Delta`, `EEG_Theta`, `EEG_Alpha`, `EEG_Beta` and `EEG_Gamma` (floats 0–1). Enable OSC in VRChat's Action Menu, add the five parameters to your avatar in Unity, and drive an animation or a PhysBone with `EEG_Alpha`. On a Meta Quest, run VRChat on the PC via Air Link or Steam Link.

Step-by-step manual: [`Docs/PiEEG_XR_VRChat_Manual.docx`](Docs) · [Tutorial](https://www.pieeg.com/tutorials/brain-reactive-vrchat-avatar) · [Video](https://www.youtube.com/watch?v=uKa9QgcLvSA)

## Example signal

Blinking 4, 3, 2 and 1 times, dry electrodes, band-pass 1–40 Hz:

<img src="https://raw.githubusercontent.com/pieeg-club/PiEEG-docs/main/public/images/hardware/2026/10/pieegxr_blink.png" alt="8 channels, blinking 4-3-2-1 times" width="700">

**Dataset** in [`Datasets`](Datasets): raw and 1–40 Hz band-pass versions of the same blink test (8 channels, ~250 SPS, µV, columns `timestamp, ch1…ch8`).

## Firmware

If the device doesn't connect over Bluetooth, update the firmware:

1. Connect an **ST-Link V2** to the SWD header inside the box (GND, RST, SWDIO, SWCLK).
2. In **STM32CubeProgrammer**, connect and flash the latest `.hex` from [`Firmware/hex`](Firmware/hex).
3. Disconnect and reset the device.

<img src="https://raw.githubusercontent.com/pieeg-club/PiEEG-docs/main/public/images/hardware/2026/10/pieegxr_swd_wiring.jpg" alt="SWD header on the PiEEG XR board" width="400">

The STM32WB Bluetooth stack ([`Firmware/stm32wb5x_BLE_Stack_full_fw.bin`](Firmware), address `0x080CE000`) normally never needs updating. Step by step: [Firmware & Service](https://docs.pieeg.com/hardware/devices/PiEEG_XR/Service/) · [Video](https://youtu.be/zU82j_DZxko)

## Videos

- [Software quick test and data quality](https://www.youtube.com/watch?v=khi54mGcJUk)
- [Face Trainer mini-game](https://www.youtube.com/watch?v=g-XgVWwQzwE)
- [Running PiEEG XR on Meta Quest](https://www.youtube.com/watch?v=ycL2kZpIdvM)
- [Playing tennis with PiEEG XR and BodyPress](https://www.youtube.com/watch?v=vkuwRFJJNxQ)
- More on the [PiEEG YouTube channel](https://www.youtube.com/@pieeg/videos)

## What's in this repository

| Folder | Content |
|---|---|
| [`Firmware`](Firmware) | Application `.hex` and the STM32WB Bluetooth stack |
| [`Datasets`](Datasets) | Blink test, raw and band-pass filtered |
| [`Docs`](Docs) | VRChat avatar manual |
| [`Images`](Images) | Images used in the original README |
| [`3D_Design`](3D_Design), [`SDK`](SDK) | Coming soon |

## Documentation

| Page | |
|---|---|
| [PiEEG XR Intro](https://docs.pieeg.com/hardware/devices/PiEEG_XR/) | Overview and specs at a glance |
| [What's in the Box](https://docs.pieeg.com/hardware/devices/PiEEG_XR/required-equipment/) | Headset compatibility, power, cables |
| [How to Start](https://docs.pieeg.com/hardware/devices/PiEEG_XR/setup/) | Fitting, connecting and the blink test |
| [Mask & Electrodes](https://docs.pieeg.com/hardware/devices/PiEEG_XR/connections/) | Electrode layout and getting good contact |
| [Software](https://docs.pieeg.com/hardware/devices/PiEEG_XR/software/) | BodyPress, PiEEG Cloud, PiEEG Server, VRChat |
| [Recording During Activity](https://docs.pieeg.com/hardware/devices/PiEEG_XR/Application/) | Clean signals while moving |
| [Signals & Projects](https://docs.pieeg.com/hardware/devices/PiEEG_XR/examples/) | Example recording, dataset, projects |
| [Specification](https://docs.pieeg.com/hardware/devices/PiEEG_XR/Specification/) | Hardware and Bluetooth data format |
| [Firmware & Service](https://docs.pieeg.com/hardware/devices/PiEEG_XR/Service/) | Firmware update, mask fit |
| [Troubleshooting & FAQ](https://docs.pieeg.com/hardware/devices/PiEEG_XR/FQA/) | Power, Bluetooth, signal and mask fixes |
| [Safety](https://docs.pieeg.com/hardware/devices/PiEEG_XR/safety/) | Battery-only operation and VR safety |

## Citation

If you use PiEEG XR in research, please cite:

```
Y. El Abbassi, I. Rakhmatulin. PiEEG XR: A WebXR Brain-Computer Interface Platform
for Neural-Adaptive Avatar Control in Mixed Reality. Preprints 2026, 2026060016.
DOI: 10.20944/preprints202606.0016.v1
```

## Contact

- 🌐 [pieeg.com](https://pieeg.com/)
- 📖 [docs.pieeg.com](https://docs.pieeg.com/)
- 💬 [Discord](https://discord.gg/5Ps24p47)
- ✉️ [pieeg@pieeg.com](mailto:pieeg@pieeg.com)
