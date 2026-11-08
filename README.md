<div align="center" markdown="1">

<img src=".github/meshtastic_logo.png" alt="Meshtastic Logo" width="80"/>

<h1>Meshtastic develop fork for Hydra boards (2.8.3-hdev)</h1>

</div>

## Overview

Fork of the Meshtastic firmware `develop` branch, built for Hydra boards: ESP32 with a LoRa E22P-868M30S radio.
Two hardware variants come from this tree:

- `hydraE22P` - ESP32 without PSRAM.
- `hydraE22P_psram` - Freenove ESP32-WROVER board with PSRAM (up to 1000 nodes).

Main additions over upstream: node statistics on demand (OnDemand), telemetry and position limiters,
opportunistic flooding, NodeMod / SignalReply, Wi-Fi and Bluetooth TX power settings, and extra
diagnostics (channel utilization, flash and heap counters, relay and duplicate counters).
Based on upstream `develop` from 2026-11-02.

## Change log

Full change log: [HYDRA.md](HYDRA.md).

- **Build 38 (2026-11-07):** NodeMod, SignalReply, noise floor in OnDemand, `wifi_power` / `bt_power` LoRa fields, admin origin gate.
- **Builds 30-37 (2026-11-06):** Store & Forward off by default, PSRAM variant on Freenove WROVER, opportunistic flooding, NodeModAdmin in the config dump.
- **Builds 2-8 (2026-11-05):** FW+ port (airtime windows, CPU sampler, port counters, telemetry, admin), `local_stats` chain, limiters.



## Credits

- Fork description: [musznik](https://github.com/musznik/firmware) (FW+ / Meshtastic+, [loranet.pl](https://loranet.pl)).
- Upstream firmware: the [Meshtastic](https://meshtastic.org) project and its contributors.
- Board designs: [NanoVHF/Meshtastic-DIY](https://github.com/NanoVHF/Meshtastic-DIY/tree/main).
