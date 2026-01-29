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

## Typical Applications:
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

### Step-by-Step Instructions

1. **Connect the Router to Power**
   - Plug in your router and ensure it is powered on. Most routers have LEDs to confirm connectivity.

2. **Set Up the Router’s Network**
   - You may skip connecting it to the internet. The router only needs to manage a local network.
   - The router’s built-in DHCP server will assign IP addresses to devices automatically.

3. **Connect Raspberry Pi 4B via Ethernet**
   - Use an Ethernet cable to link the Raspberry Pi to a LAN port on the router.

4. **Reserve a Fixed IP for the Raspberry Pi 4B**
   - Use your router’s admin interface (via browser) to find the Raspberry Pi in the connected devices.
   - Assign it a fixed (static) IP address from the DHCP settings.

5. **Obtain the IP Address of the Raspberry Pi**
   - It’s listed in the router’s admin panel under "connected devices".

6. **Connect Other Devices (iPad, PC, Mac...) to the Same Network**
   - Use Wi-Fi or Ethernet to join the same LAN created by the router.

7. **Access the Web Interface**
   - Open a browser on any connected device and go to:
     ```
     http://<RPI4B_IP_address>:1880/ui
     ```
     Example:
     ```
     http://192.168.1.100:1880/ui
     ```

## Tabs Overview

1. **Presets Tab** (`PRESETS`)

   ![Presets Panel](https://github.com/ave-audio/ave-mixer-remote-control/blob/9e37db7ad3867cccc6f01de6082015b047c4b849/images/Andante%20Remote%20Control%20V2.0%20-%20Presets%20Panel.jpg)

   - Switch between different preset configurations using buttons. Each preset button is dynamically labeled with its name.
   - The buttons also change color based on the currently selected preset.
   - **Note**: The remote control system periodically monitors the currently selected preset.

2. **Inputs Tab** (`INPUTS`)

   - Manage different audio inputs via sliders and text fields that show percentage levels for each input.
   - Each input has a fader control for volume adjustment and a display of the current percentage level.
   - Each input channel also includes a **switch** to enable or disable the channel, allowing the user to easily control the active status of the input channels.

3. **Outputs Tab** (`OUTPUTS`)

   ![Outputs Panel](https://github.com/ave-audio/ave-mixer-remote-control/blob/9e37db7ad3867cccc6f01de6082015b047c4b849/images/Andante%20Remote%20Control%20V2.0%20-%20Outputs%20Panel.jpg)

   - Adjust audio outputs, with faders for controlling the master level and individual output levels.
   - Each output has controls similar to the input interface (fader and percentage display).
   - Each output channel also includes a **switch** to enable or disable the output channel, giving full control over the active status of each output.

4. **Info Tab** (`INFO`)

   ![Info Panel](https://github.com/ave-audio/ave-mixer-remote-control/blob/9e37db7ad3867cccc6f01de6082015b047c4b849/images/Andante%20Remote%20Control%20V2.0%20-%20Info%20Panel.jpg)

   - Provides information about the device, such as the device name, firmware versions (MCU and DSP), and other status-related information.
   - No control elements, only for displaying read-only data.

## Main Functional Elements

### Presets

- **Preset Buttons**: Switch between preset configurations using labeled buttons. Each button reflects the preset name and changes its background color to indicate which preset is currently active.

### Input Control

Each input has the following controls:

- **Fader**: Adjust the volume level from 0 to 140.
- **Percentage Level**: Shows the current level as a percentage, based on the fader position.
- **Switch**: Toggle each input between active and inactive states.
- **Note**: The system periodically monitors the input levels.

### Output Control

Each output has:

- **Master Level Control**: A fader to adjust the global output level.
- **Individual Output Faders**: Adjust the level of each output channel.
- **Percentage Display**: Shows the current output level in percentage format.
- **Note**: The system periodically monitors the output levels.

## Additional Notes

- The system allows real-time adjustments, meaning changes made via the UI immediately affect the mixer settings.
- Ensure that the **USB to RS232 converter** is correctly plugged into the Raspberry Pi 4B and that the DB9 connector is securely attached to the Andante mixer’s serial port.

## License

This application is the property of AVE GmbH and all rights are reserved. Unauthorized copying, modification, or distribution of this software is strictly prohibited.

## Contact

For any questions or suggestions, please open an issue on GitHub or contact us at info@ave-stuttgart.de.

## Manufacturer

**AVE GmbH**  
Gustav-Rau-Str. 6  
74321 - Bietigheim-Bissingen  
Deutschland  
Tel.: +49 7142-78879-0  
Fax: +49 7142-78879-18  
Email: info@ave-stuttgart.de

**All rights reserved 2026.**
