# Meshtastic develop fork for Hydra boards (2.8.3-hdev)

Fork of the Meshtastic firmware `develop` branch for Hydra boards (ESP32 with a LoRa E22P-868M30S radio).
Two hardware variants are built from this tree:

- `hydraE22P` - ESP32 without PSRAM.
- `hydraE22P_psram` - Freenove ESP32-WROVER board with PSRAM (up to 1000 nodes).

Main additions over upstream: node statistics on demand (OnDemand), telemetry and position limiters,
opportunistic flooding, NodeMod / SignalReply, Wi-Fi and Bluetooth TX power settings, and extra
diagnostics (channel utilization, flash and heap counters, relay and duplicate counters).
Based on upstream `develop` from 2026-11-02.

## Change log

### Build 38 (2026-11-07)
- NodeMod, SignalReply, noise floor field in OnDemand.
- New LoRa config fields `wifi_power` (108) and `bt_power` (109), exposed in CLI and firmware.
- Admin origin gate (from upstream): admin messages with `from=0` accepted only from local clients.

### Builds 30-37 (2026-11-06)
- Store & Forward off by default; byte counters; quieter UDP relay log.
- PSRAM variant on the Freenove WROVER board; build labels `vNN` and `vNNp`.
- Opportunistic flooding (ported from the fork).
- NodeModAdmin included in the config dump (build hdev-v3).

### Builds 2-8 (2026-11-05)
- FW+ port: airtime windows, CPU sampler, port counters, telemetry, admin.
- `local_stats` chain, `local_stats_extended` (used and total flash on ESP32), RX history, limiters.
- Develop build numbering.

### Submodule `protobufs` (commit 777faea)
- `LoRaConfig.wifi_power = 108`, `LoRaConfig.bt_power = 109`, `NodeStats.noise_floor = 40`, and NodeStats counters.
