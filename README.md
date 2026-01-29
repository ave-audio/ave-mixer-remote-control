# AVE Digital Mixer Andante V2.0 - Remote Control - User Manual

**AVE Mixer Remote Control** from [AVE GmbH](https://ave-audio.de/en) is a versatile and user-friendly web application designed to manage and control the settings of your AVE Digital Mixer Andante V2.0. This powerful application runs on a Raspberry Pi 4B and is easily accessible via any standard web browser, allowing the mixer’s end-user to seamlessly manage audio configurations.

This manual provides an overview of the user interface (UI) for controlling the **AVE Digital Mixer Andante V2.0** series via the Node-RED platform running on a Raspberry Pi 4B (RPI 4B).

## Main Features

- Web-based access (browser-based, no special client required)
- Access over LAN network
- Intuitive user interface with sliders, buttons, and switches
- Real-time control without technical expertise
- Real-time monitoring and remote control
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

<p align="center">
  <img src="https://github.com/ave-audio/ave-mixer-remote-control/blob/7a6c2350dd967b06446d3150658b27d24e57101b/images/Andante%20Remote%20Control%20V2.0%20-%20Setup%20Diagram.jpg" alt="AVE Mixer Remote Control - Setup Diagram" width="85%" />
</p>

### Step-by-Step Instructions

1. **Connect the Router to Power**
2. **Set Up the Router’s Network**  
   Let the router assign IP addresses using DHCP (no internet required).
3. **Connect Raspberry Pi 4B via Ethernet**
4. **Reserve a Fixed IP for the Raspberry Pi 4B**  
   Use your router’s admin interface to make the current IP static.
5. **Obtain the IP Address of the Raspberry Pi**
6. **Connect Other Devices (iPad, PC, Mac...) to the Same Network**
7. **Access the Web Interface**  
   Open a browser and visit:  
   ```
   http://<RPI4B_IP_address>:1880/ui
   ```

### Notes

- A fixed IP address makes reconnection easy.
- Ethernet is more stable than Wi-Fi for RPi use.

## Tabs Overview

1. **Presets Tab (`PRESETS`)**  
   - Dynamic preset buttons that reflect the current configuration.  
   - Active preset is highlighted.  
   - Periodically monitored for status sync.

2. **Inputs Tab (`INPUTS`)**  
   - Control audio input levels with sliders and switches.  
   - Enable/disable individual input channels.

3. **Outputs Tab (`OUTPUTS`)**  
   - Adjust master and individual output levels.  
   - Toggle output channels on or off.

4. **Info Tab (`INFO`)**  
   - Display-only tab showing device details like firmware versions.

## Main Functional Elements

### Presets

- Clickable preset buttons  
- Color-coded for current status  
- Change mixer config instantly

### Input/Output Control

- Faders for each channel  
- Display of percentage levels  
- Enable/disable channels  
- Real-time interaction and monitoring

## Additional Notes

- Changes via the UI apply instantly to the mixer  
- USB-RS232 connection is critical for proper communication

## License

This application is the property of AVE GmbH and all rights are reserved. Unauthorized copying, modification, or distribution of this software is strictly prohibited.

## Contact

For any questions or suggestions, please open an issue on GitHub or contact us at [info@ave-stuttgart.de](mailto:info@ave-stuttgart.de)

## Manufacturer

**AVE GmbH**  
Gustav-Rau-Str. 6  
74321 - Bietigheim-Bissingen  
Deutschland  
Tel.: +49 7142-78879-0  
Fax: +49 7142-78879-18  
Email: info@ave-stuttgart.de

**All rights reserved 2026.**
