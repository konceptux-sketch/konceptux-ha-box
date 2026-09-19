# Konceptux HA Box - Essential

A pre-built, pre-configured smart home automation server, designed and built by Konceptux Automation. This repo documents the hardware design, software stack, and setup process behind a real, shipped product - from prototype to something a non-technical customer can plug in and use.

## What it is

The Konceptux HA Box is a turnkey Home Assistant appliance. Instead of asking a customer to flash an SD card, install an OS, and configure Home Assistant from scratch, the HA Box arrives ready to go: power it on, connect to WiFi, and start adding devices.

## Hardware

- Raspberry Pi 4 (4GB) as the core compute platform
- 256GB USB SSD for fast, reliable storage (avoids the SD card wear/corruption issues common in always-on Pi deployments)
- Integrated Zigbee 3.0 coordinator for direct device pairing, no separate USB dongle required
- Onboard fast alarm buzzer, sub-800ms response time, for security/alert use cases
- Custom PETG enclosure, 3D printed and laser-engraved with the Konceptux logo
- External antenna for improved Zigbee range in real installations

## Software stack

- Home Assistant OS, pre-installed and pre-configured
- Zigbee2MQTT or Home Assistant's native Zigbee integration for device pairing
- A starter dashboard pre-loaded on first boot, showing living room status, climate, security state, energy use, and connected Zigbee device count
- Local-first by design: no cloud dependency required for core automation to function

## Why this design

Most DIY Home Assistant setups fail for non-technical users at one of three points: OS installation, SD card reliability, or Zigbee coordinator setup. The HA Box removes all three:

- Pre-installed OS means zero setup friction for the end customer
- SSD instead of SD card removes the single most common cause of Home Assistant instance corruption in long-running installs
- Integrated Zigbee coordinator means no separate USB dongle to lose, misconfigure, or place badly for range

## From prototype to shipped product

This is a real example of the gap between "it works as a demo" and "I can sell this to someone else." Getting here meant:

- Selecting and validating a storage solution that survives 24/7 operation (SSD over SD card, after testing SD card failure rates under sustained write load)
- Designing a custom enclosure with adequate ventilation, since the sealed PETG case initially caused thermal issues under sustained Zigbee coordinator load
- Building a starter dashboard that means something to a non-technical buyer on first boot, not just a blank Home Assistant install
- Sourcing and integrating a buzzer/alarm subsystem for security use cases, with configurable volume, melody, and duration

## Status

Available as a product through Konceptux Automation. This repo documents the design and architecture publicly as a build log and proof of engineering approach, not as a full bill-of-materials for replication.

## About

Built by Kevin de Souza, embedded systems engineer and founder of Konceptux Automation. Background includes production BACnet/Modbus HVAC firmware, CubeSat NB flight software (Canadian Space Agency-funded, deployed from the ISS in 2024), and custom ESP32/STM32-based smart building IoT systems.

Available for embedded firmware, hardware productization, and smart building consulting work - visit konceptux.com.
