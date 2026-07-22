# Trucker Bz

Trucker Bz is an Ulanzi D200 plugin for Euro Truck Simulator 2 and American Truck Simulator. It shows live truck telemetry and provides configurable control buttons for common truck actions.

This repository contains the final `com.buzs.truckerbz.ulanziPlugin` folder ready for store/community review. The TypeScript source is not included in this public distribution. The zipped `.ulanziPlugin` package is attached to GitHub Releases.

## Features

- Live truck telemetry buttons for speed, fuel, RPM, trip, rest and damage information.
- Controls for lights, beacon, wipers, windows, suspension, retarder and trailer hookup.
- Dynamic Ulanzi property inspector for per-button settings.

## Repository contents

- `com.buzs.truckerbz.ulanziPlugin/`: final plugin folder used by Ulanzi.
- `README.md`: public usage and install notes.

The repository version of the plugin folder does not commit `node_modules`. The runtime dependency `trucksim-telemetry` is declared in `com.buzs.truckerbz.ulanziPlugin/package.json`; run `npm install` inside that folder before trying to run the plugin from a clone.

## Requirements

- Windows 10 or newer.
- Ulanzi software 2.1.4 or newer.
- Euro Truck Simulator 2 or American Truck Simulator.
- The SCS telemetry SDK plugin installed in the game folder.

## Required SCS telemetry plugin

Trucker Bz reads telemetry through the Node package `trucksim-telemetry`, which depends on the SCS shared-memory telemetry plugin.

Install the SCS SDK plugin from:

https://github.com/RenCloud/scs-sdk-plugin

Place the plugin DLL inside the `bin/win_x64/plugins/` folder of the game installation. Create the `plugins` folder if it does not exist.

Common Steam locations:

```text
C:\Program Files (x86)\Steam\steamapps\common\Euro Truck Simulator 2\bin\win_x64\plugins\
C:\Program Files (x86)\Steam\steamapps\common\American Truck Simulator\bin\win_x64\plugins\
```

When the game starts, it may show an SDK activation prompt. Accept it so telemetry becomes available.

## Install

Download the `.ulanziPlugin.zip` artifact from GitHub Releases and import it in the Ulanzi software. Release ZIPs are built with runtime dependencies included.

For store/community review, the unpacked `com.buzs.truckerbz.ulanziPlugin` folder in this repository can also be inspected directly.

## Running from a clone

This public repository is a distribution repository, not the source project. If you clone it and want to run or test the unpacked plugin folder directly, install the runtime dependencies first:

```bash
cd com.buzs.truckerbz.ulanziPlugin
npm install
```

This creates `com.buzs.truckerbz.ulanziPlugin/node_modules/trucksim-telemetry/`. If `trucksim-telemetry` is missing from `node_modules`, the plugin runtime will not start correctly.

## License

Trucker Bz is distributed here as a built Ulanzi plugin package. The real source code is private and is not licensed as part of this public distribution.

Third-party dependencies keep their own licenses. The SCS telemetry plugin by RenCloud is available at `https://github.com/RenCloud/scs-sdk-plugin` and is licensed separately by that project.
