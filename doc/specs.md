# Konceptux HA Box - Essential: Technical Specifications

## Compute

| Component | Spec |
|---|---|
| SBC | Raspberry Pi 4, 4GB RAM |
| Storage | 256GB USB SSD (boot + storage) |
| OS | Home Assistant OS, pre-installed |

## Connectivity

| Component | Spec |
|---|---|
| Zigbee | Integrated Zigbee 3.0 coordinator, external antenna |
| Network | Gigabit Ethernet, WiFi fallback |
| Local protocols | MQTT, Zigbee2MQTT / native ZHA |

## Physical

| Component | Spec |
|---|---|
| Enclosure | Custom PETG, 3D printed, laser-engraved logo |
| Ventilation | Vented top panel (added in Rev B after thermal testing under sustained Zigbee load) |
| Alarm | Onboard buzzer, less than 800ms trigger response |

## Software features (out of the box)

- Pre-loaded starter dashboard: living room status, climate, security/armed state, energy monitoring, Zigbee device count
- Configurable alarm: volume, melody, and duration via Home Assistant entities
- Local-first operation: core automations run without internet access

## Design notes

- SSD chosen over SD card after observed failure rates under sustained write load in 24/7 testing - SD card corruption is the most common cause of Home Assistant instance failure in long-running home installs
- Rev A enclosure ran hot under sustained Zigbee coordinator load in a sealed case; Rev B added top ventilation and repositioned the coordinator away from the Pi's own heat output
