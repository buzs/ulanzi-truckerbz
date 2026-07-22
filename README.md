<p align="center">
  <img src="assets/gh_logo.png" alt="Trucker Bz" width="600">
</p>

<p align="center">
  <img alt="Version" src="https://img.shields.io/badge/version-0.2.0-ff8a00?style=for-the-badge">
  <img alt="Ulanzi D200" src="https://img.shields.io/badge/Ulanzi-D200-111827?style=for-the-badge">
  <img alt="Windows" src="https://img.shields.io/badge/platform-Windows%2010%2B-2f81f7?style=for-the-badge">
  <img alt="ETS2 and ATS" src="https://img.shields.io/badge/ETS2%20%7C%20ATS-telemetry-ff8a00?style=for-the-badge">
  <img alt="Node.js" src="https://img.shields.io/badge/runtime-Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white">
</p>

<p align="center">
  <strong>Live ETS2/ATS telemetry and truck controls for the Ulanzi D200.</strong>
</p>

---

## Overview

Trucker Bz turns the Ulanzi D200 into a compact truck telemetry dashboard and control panel for Euro Truck Simulator 2 and American Truck Simulator.

This repository is a public distribution package. It contains the final `com.buzs.truckerbz.ulanziPlugin` folder for store/community review, but it does not include the real TypeScript source code.

## Features

- Live telemetry buttons for speed, fuel, RPM, trip, rest and damage information.
- Truck controls for lights, beacon, wipers, windows, suspension, retarder and trailer hookup.
- Dynamic Ulanzi property inspector for per-button configuration.
- Public unpacked plugin folder for review and GitHub Release ZIPs for normal installation.

## Actions

Trucker Bz currently includes 18 Ulanzi actions. The preview column is reserved for future button screenshots/images.

| Preview     | Action                | What it does                                                                                                                                                          |
| ----------- | --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Coming soon | Lights / Blinker      | Configurable left, right or hazard indicator button. Shows the live indicator state and sends the configured hotkey when pressed. Defaults: `Q`, `E`, `F`.            |
| Coming soon | Lights / Main Switch  | Main light switch button. Shows off, parking lights or low beam based on telemetry and sends the configured hotkey. Default: `L`.                                     |
| Coming soon | Lights / High Beam    | High beam toggle. Shows whether high beam is active and sends the configured hotkey. Default: `K`.                                                                    |
| Coming soon | Lights / Beacon       | Beacon light toggle. Shows beacon off/on state, including an animated on icon, and sends the configured hotkey. Default: `B`.                                         |
| Coming soon | Windows               | Configurable left/right window open/close button. Uses the configured hotkey to trigger the game window command.                                                      |
| Coming soon | Parking Brake         | Parking brake toggle. Shows parking brake on/off state and sends the configured hotkey. Default: `Space`.                                                             |
| Coming soon | Trailer Hookup        | Trailer attach/detach button. Shows whether a trailer is attached and sends the configured hotkey. Default: `T`.                                                      |
| Coming soon | Fuel                  | Telemetry display for fuel level, fuel range or fuel consumption. Pressing the key cycles between modes. Supports metric units for ETS2 and imperial display for ATS. |
| Coming soon | Trip                  | Route information display. Cycles between estimated route time, real-time estimate and remaining distance. Uses miles for ATS and kilometers for ETS2.                |
| Coming soon | Speed Limit Indicator | Shows the current route speed limit in `km/h` or `mph`. Pulses red when the truck is over the configured tolerance.                                                   |
| Coming soon | Rest                  | Shows time remaining until the next rest stop. Turns red near the limit and shows `ASAP` when overdue.                                                                |
| Coming soon | Retarder              | Configurable retarder status, increase or decrease button. Status mode shows current retarder level and availability.                                                 |
| Coming soon | Cruise Control        | Configurable cruise control status, increase or decrease button. Status mode shows current cruise target speed or `OFF`.                                              |
| Coming soon | Suspension            | Configurable suspension command button: front up/down, rear up/down or reset. Sends the configured hotkey.                                                            |
| Coming soon | Speed                 | Live speed display. Cycles between base and digital layouts. Uses `KM/H` for ETS2 and `MPH` for ATS.                                                                  |
| Coming soon | Gear                  | Live gear mode indicator. Shows neutral, reverse or drive when the engine is enabled.                                                                                 |
| Coming soon | Wipers                | Wipers toggle. Shows wipers on/off state and sends the configured hotkey. Default: `P`.                                                                               |
| Coming soon | Electric              | Electrical/battery toggle. Shows electric system on/off state and sends the configured hotkey. Default: `E`.                                                          |

## Requirements

- Windows 10 or newer.
- Ulanzi software 2.1.4 or newer.
- Euro Truck Simulator 2 or American Truck Simulator.
- SCS telemetry SDK plugin installed in the game folder.
- `trucksim-telemetry` installed when running from a cloned repository.

## Install From Release

Download the ZIP asset from the latest GitHub Release:

```text
com.buzs.truckerbz.ulanziPlugin.zip
```

Import that ZIP in the Ulanzi software. Release ZIPs are built with runtime dependencies included, so end users do not need to run `npm install` for normal installation.

## Required SCS Telemetry Plugin

Trucker Bz reads telemetry through the Node package `trucksim-telemetry`, which depends on the SCS shared-memory telemetry plugin.

Install the SCS SDK plugin from:

```text
https://github.com/RenCloud/scs-sdk-plugin
```

Place the plugin DLL inside the `bin/win_x64/plugins/` folder of your ETS2 or ATS installation. Create the `plugins` folder if it does not exist.

Common Steam locations:

```text
C:\Program Files (x86)\Steam\steamapps\common\Euro Truck Simulator 2\bin\win_x64\plugins\
C:\Program Files (x86)\Steam\steamapps\common\American Truck Simulator\bin\win_x64\plugins\
```

When the game starts, it may show an SDK activation prompt. Accept it so telemetry becomes available.

## Running From A Clone

This public repository does not commit `node_modules`.

If you clone the repository and want to run or inspect the unpacked plugin folder directly, install runtime dependencies inside the plugin folder:

```bash
cd com.buzs.truckerbz.ulanziPlugin
npm install
```

This creates:

```text
com.buzs.truckerbz.ulanziPlugin/node_modules/trucksim-telemetry/
```

If `trucksim-telemetry` is missing from `node_modules`, the plugin runtime will not start correctly.

## Repository Layout

```text
.
├── CHANGELOG.md
├── LICENSE
├── README.md
└── com.buzs.truckerbz.ulanziPlugin/
    ├── manifest.json
    ├── package.json
    ├── plugin/
    ├── property-inspector/
    ├── resources/
    └── libs/
```

## License

Trucker Bz is distributed here as a built Ulanzi plugin package. The real source code is private and is not licensed as part of this public distribution.

Third-party dependencies keep their own licenses. The SCS telemetry plugin by RenCloud is available at `https://github.com/RenCloud/scs-sdk-plugin` and is licensed separately by that project.
