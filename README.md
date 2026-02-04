# AVE Digital Mixer Andante V2.0 - Remote Control - User Manual

**AVE Mixer Remote Control** from [AVE GmbH](https://ave-audio.de/en) is a versatile and user-friendly web application designed to manage and control the settings of your AVE Digital Mixer Andante V2.0. This powerful application runs on a Raspberry Pi 4B and is easily accessible via any standard web browser, allowing the mixer’s end-user to seamlessly manage audio configurations.

This manual is intended for **system integrators, installers, and end-users** responsible for configuring and operating AVE Digital Mixer Andante V2.0 systems.

This manual provides an overview of the user interface (UI) for controlling the **AVE Digital Mixer Andante V2.0** series via the Node-RED platform running on a Raspberry Pi 4B (RPI 4B).

## Main Features

- Web-based access (browser-based, no special client required)
- Access over LAN network
- Intuitive user interface with sliders, buttons, and switches
- Real-time control and monitoring without requiring technical expertise
- Input/Output level adjustment
- Preset selection
- Channel activation/deactivation
- Controllable from any device on the network (Android, macOS, Windows, etc.)
- Supports multiple devices simultaneously
- Very easy to integrate into existing systems

## Typical Applications

- Conference rooms
- Multi-zone audio systems
- Events & installations
- Remote support / technical assistance
- Multimedia productions

## Overview & Requirements

The UI is structured into various tabs and sections that allow the user to control the inputs, outputs, and presets of the AVE Digital Mixer Andante V2.0, with specific sliders, buttons, and switches for different parameters. The system also **periodically monitors the input/output levels and the currently selected preset**.

### What You’ll Need

- **Router + Access Point**: A standard home router with LAN ports.
- **Raspberry Pi 4B**: Connected to the network via an Ethernet cable.
- **USB to RS232 Adapter (FTDI or Prolific chip recommended)**: For reliable serial communication between the Raspberry Pi and the mixer.  
  ⚠️ Ensure the adapter operates in **RS232 mode**. **RS485 adapters are not compatible** with the Andante V2.0 serial interface.
  
  *Tested and recommended example:*  
  [UGREEN USB to Serial Adapter (DB9 Male, PL2303 chipset, 1 m cable)](https://a.co/d/0f9uRHFO) — compatible with **Windows, macOS, and Linux**.
- **AVE Digital Mixer Andante V2.0**: Connected to the Raspberry Pi 4B via the USB to RS232 converter.
- **Ethernet Cable**: To connect the Raspberry Pi 4B to the router.

## System Setup

To get started, follow these steps in order:

### 1. Download the Preconfigured Image

The AVE Mixer Remote Control is distributed as a **preconfigured Raspberry Pi 4B system image**, which includes:

- Operating system
- Node-RED runtime
- Required Node-RED flows
- All necessary dependencies for Andante V2.0 remote control

#### Download Location

Download the ZIP file from the following Dropbox link:

[Download the Raspberry Pi 4B system image (Dropbox)](https://www.dropbox.com/scl/fi/ygcqzvo4ys8bq5b24k0k8/mediaAVE_V1.1_08-10-2024.zip?rlkey=hem2p9laiwqhjms1pz432l38j&dl=0)

### 2. Flash the Image to a microSD Card

1. Extract the downloaded ZIP file to get the `.img` file.
2. Use a tool such as [Raspberry Pi Imager](https://www.raspberrypi.com/software/) or [balenaEtcher](https://etcher.io/) to write the image to a **32 GB or larger microSD card**.
3. Insert the programmed microSD card into your Raspberry Pi 4B.

### 3. Hardware Connections

- Connect a **USB–RS232 adapter** to any USB port on the Raspberry Pi 4B.
- Plug the **DB9 connector** (the other end of the adapter) into the **RS232 serial port** on the rear of the AVE Digital Mixer Andante V2.0.
- Power on both the Raspberry Pi and the mixer.

> 💡 We recommend using an RS232 adapter based on the **FTDI** or **Prolific** chip for best compatibility and performance.

This setup enables direct communication between the Raspberry Pi and the mixer for real-time remote control.

## Setting Up a Minimal LAN Network

This section explains how to set up a basic LAN (Local Area Network) using a common router and connecting your Raspberry Pi 4B to the network via Ethernet.

> **Note**: Connecting the Raspberry Pi 4B to the router via Wi-Fi is not recommended. Always use a wired Ethernet connection for stability.

![AVE Mixer Remote Control - Setup Diagram](https://github.com/ave-audio/ave-mixer-remote-control/blob/7a6c2350dd967b06446d3150658b27d24e57101b/images/Andante%20Remote%20Control%20V2.0%20-%20Setup%20Diagram.jpg)

> *Note: Screenshots and diagrams reflect the UI layout at the time of release and may differ slightly from future software versions.*

### Step-by-Step Instructions

1. **Connect the Router to Power**
   - Plug your router into a power outlet and ensure it is switched on. Most routers have LEDs that indicate power and network connectivity.

2. **Set Up the Router's Network**
   - Connect the router to your modem (if needed) to provide internet access, or simply use it to create a local area network without internet.
   - The router will automatically assign IP addresses to connected devices using DHCP.

3. **Connect the Raspberry Pi 4B via Ethernet**
   - Connect one end of an Ethernet cable to one of the LAN ports on your router.
   - Connect the other end of the cable to the Ethernet port on your Raspberry Pi 4B.
   - The Raspberry Pi will automatically receive an IP address from the router.

4. **Reserve a Fixed IP Address for the Raspberry Pi 4B**
   - It is recommended to reserve a **fixed IP address** for the Raspberry Pi 4B to avoid changes in its IP address when reconnecting to the network.
   - Access your router’s admin settings (typically via `192.168.1.1` or `192.168.0.1`).
   - Locate the **DHCP** or **LAN settings** section and reserve the Raspberry Pi’s IP address.

5. **Obtain the Raspberry Pi 4B's IP Address**
   - The assigned IP address can be found in the router's admin interface under connected devices.

6. **Connect Other Devices to the Same Network**
   - Ensure that any computer, tablet, or smartphone used to access the UI is connected to the same LAN.

7. **Accessing the User Interface**
   - Open a web browser and enter:
     ```
     http://<RPI4B_IP_address>:1880/ui
     ```
     Replace `<RPI4B_IP_address>` with the actual IP address of the Raspberry Pi 4B.

## Tabs Overview

### Presets Tab (`PRESETS`)

![Presets Panel](https://github.com/ave-audio/ave-mixer-remote-control/blob/9e37db7ad3867cccc6f01de6082015b047c4b849/images/Andante%20Remote%20Control%20V2.0%20-%20Presets%20Panel.jpg)

- Switch between different preset configurations using dynamically labeled buttons.
- Buttons change color to indicate the currently selected preset.
- The system periodically monitors the active preset.

### Inputs Tab (`INPUTS`)

- Manage audio inputs using sliders and percentage level indicators.
- Each input includes a fader and an enable/disable switch.

### Outputs Tab (`OUTPUTS`)

![Outputs Panel](https://github.com/ave-audio/ave-mixer-remote-control/blob/9e37db7ad3867cccc6f01de6082015b047c4b849/images/Andante%20Remote%20Control%20V2.0%20-%20Outputs%20Panel.jpg)

- Adjust master and individual output levels using faders.
- Each output includes a percentage display and enable/disable switch.

### Info Tab (`INFO`)

![Info Panel](https://github.com/ave-audio/ave-mixer-remote-control/blob/9e37db7ad3867cccc6f01de6082015b047c4b849/images/Andante%20Remote%20Control%20V2.0%20-%20Info%20Panel.jpg)

- Displays device information such as firmware versions and system status.
- Read-only section with no control elements.

## Additional Notes

- All changes made via the UI are applied in real time.
- Ensure the USB–RS232 adapter is correctly connected and securely attached.

## License

This software is the property of **AVE GmbH** and is provided **exclusively for use with AVE Digital Mixer Andante V2.0 products**.  
All rights are reserved. Unauthorized copying, modification, or distribution of this software is strictly prohibited.

## Contact

For questions or suggestions, please open an issue on GitHub or contact:

info@ave-stuttgart.de

## Manufacturer

**AVE GmbH**  
Gustav-Rau-Str. 6  
74321 Bietigheim-Bissingen  
Germany  

Tel.: +49 7142-78879-0  
Fax: +49 7142-78879-18  
Email: info@ave-stuttgart.de  

**All rights reserved 2026.**
