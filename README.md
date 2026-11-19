# Wireless Smart Trash Bin

## Fill-Level Monitoring System

CS 578 Wireless Networks project at San Diego State University — Group 15.

**Team:** Hongzhen Xu, Sparsh Mody, Chinmay Patel

## Overview

This project aims to add low-cost sensing and Wi-Fi connectivity to a regular trash bin. An ultrasonic sensor measures the distance to the trash surface, and an ESP32 processes the readings to estimate the fill level. A web dashboard will display the approximate status as **25%, 50%, 75%, or Full**.

**Status:** Initial project setup. Hardware integration, the dashboard, and performance testing are planned. This repository does not yet include a working implementation or measured results.

## Motivation

Maintenance staff need to know which bins require emptying. Checking fill levels remotely could help staff prioritize collections and reduce unnecessary checks. The prototype will explore whether a simple wireless system can provide useful approximate fill information.

## Planned system

```text
Ultrasonic sensor <----> ESP32 ---- Wi-Fi ----> Web dashboard
                         |
                    USB power
```

1. Mount the ultrasonic sensor near the top of the bin, facing down toward the trash.
2. Measure the distance from the sensor to the trash surface.
3. Use the ESP32 to estimate the fill level and classify the result.
4. Send the status over Wi-Fi for display in a browser.

## Planned hardware

- ESP32 development board with Wi-Fi
- Ultrasonic distance sensor
- Compatible jumper wires and a USB data cable
- A trash bin or suitable container for the prototype

The sensor model, wiring, and supply requirements will be documented after hardware selection. Signal voltage compatibility must be checked before connecting the sensor to the ESP32.

## Technical challenges

- **Calibration:** Define the empty-bin reference and the threshold for emptying.
- **Uneven trash surfaces:** Test how trash arrangements affect the estimate.
- **Stable readings:** Filter fluctuating measurements to reduce frequent status changes.
- **Connection reliability:** Show the last update time and flag stale data.

Fill levels are approximate estimates based on measured surface height, rather than precise measurements of occupied volume.

## Repository structure

| Folder | Purpose |
| --- | --- |
| `firmware/` | ESP32 code and device configuration examples |
| `dashboard/` | Web dashboard and optional simulation interface |
| `hardware/` | Component list, wiring, and assembly notes |
| `docs/` | Design notes, diagrams, and project documentation |
| `tests/` | Test procedures, measurements, and results |

These folders are starting points for future work. Setup and run instructions will be added alongside each implementation.
