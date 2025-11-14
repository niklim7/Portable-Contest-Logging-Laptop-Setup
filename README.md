Project: Portable Contest Logging Laptop Setup

Project Status: Completed (Ready for Field Deployment)

1. Summary (Product Vision)

This project details the build and configuration of a highly-optimized, low-power portable laptop setup for amateur radio contesting. The primary goal was to create a reliable and efficient system for un-assisted contest logging, prioritizing battery longevity and a minimal resource footprint.

2. System Requirements

Primary Goal: Very low power consumption (sub-6 watts) to extend battery life.

Key Function: Must be able to key the radio for CW.

Software: Must run a lightweight, non-graphical logger.

Connectivity: Offline-first for un-assisted contesting.

3. Solution: Hardware & Software Architecture

Hardware

Laptop: HP EliteBook 840 G2 (i5-5300U, 16GB RAM, 240GB SSD).

Radio Interface: Custom-built USB to Serial (FTDI) interface with an optoisolator to prevent noise transfer.

Software Architecture

OS: Minimal Debian 13 (headless TTY) installation, booting directly to a terminal. (Note: You can update this to mention Void, or keep it as Debian if that was the original state).

Environment: tmux for session/window management.

Core Logger: yfktest (Perl-based) and tlf (C-based), chosen for their extremely low resource usage.

System Management: btop for resource monitoring, tlp for battery management.

4. Results & Validation

Performance Baseline: System stability confirmed.

Power Consumption: Validated a steady-state draw of 5-6 watts (with screen at 10-20% brightness, Wi-Fi/Bluetooth off), resulting in a projected 12+ hour battery life for extended portable operations.

Current Status: Ready for final field deployment validation.

5. Photos

![Image](https://github.com/user-attachments/assets/ec68d3ae-0ce1-4485-945b-5b5c5a1aa4af)

![Image](https://github.com/user-attachments/assets/82f4d743-bc0f-4219-a75f-5a9079d7cc2a)

![Image](https://github.com/user-attachments/assets/e80826b2-66aa-4ca6-9ac0-7fcd1834d357)

![Image](https://github.com/user-attachments/assets/a37342e7-48e2-43af-8c1e-68f56b521e05)

![Image](https://github.com/user-attachments/assets/55ca950d-5efc-4956-8dba-ff581cbe1389)

73 de Nik SV1SYY
