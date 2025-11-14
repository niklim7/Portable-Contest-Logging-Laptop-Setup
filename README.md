Project: Portable Contest Logging Laptop Setup

Project Status: Completed (Ready for Field Deployment)

1. Summary (Product Vision)

This project details the build and configuration of a highly-optimized, low-power portable laptop setup for amateur radio contesting. The primary goal was to create a reliable and efficient system for un-assisted contest logging, prioritizing battery longevity and a minimal resource footprint while retaining the ability to key the radio. This involved defining a custom system architecture based on Musl Void Linux and optimizing a complete TUI (Text-User Interface) application stack.

2. System Requirements

The "product" requirements for this build were:

Primary Goal: Very low power consumption to extend battery life for long portable operations.

Key Function: Must be able to key the radio for CW (Morse Code).

Software: Must run a lightweight, efficient logger that can be used in a minimal environment (non-graphical).

Connectivity: Internet (Wi-Fi/Bluetooth) is not required; focus is on un-assisted contesting.

3. Solution: Hardware & Software Architecture

Hardware

Laptop: HP EliteBook 840 G2 (i5-5300U, 16GB RAM, 240GB SSD).

Battery: New official HP extended battery.

Radio Interface: Custom-built USB to Serial (FTDI) interface with an optoisolator to prevent noise transfer from the laptop to the radio.

Operating System & TUI Stack (The Minimalist Architecture)

Architecture: Void Linux (musl), utilizing the runit init system for maximum efficiency. System configured to boot into a headless TTY environment.

Core Workflow: Architected a complete TUI (Text-User Interface) workflow using tmux (session manager) and fbterm (terminal emulator) for a stable, keyboard-driven environment.

Application Stack: A curated selection of terminal-based tools to fulfill daily driver and contest needs:

Contest/Logging: yfktest, tlf (compiled from source).

Daily Use: aerc (Email Client), rbw (Password Manager), w3m (Web Browser), wordgrinder (Word Processor), nnn (File Manager).

4. Technical Achievements & Optimization (NFR Validation)

This section highlights the success in meeting Non-Functional Requirements (NFRs) through low-level system configuration:

Resource Optimization: Achieved a steady-state power consumption of 5–6 watts, extending battery life for specialized portable operations to over 12 hours. This was validated through BIOS/CPU tuning and running a completely headless TTY environment.

Low-Level Integration: Successfully configured acpid to map laptop keys (Sleep, Volume, Mute) to system functions (amixer), demonstrating competence in hardware event handling and system customization.

Software Customization: Identified specialized logging software (tlf) not available in the minimal repository and successfully compiled the application from source code, demonstrating control over the entire software delivery pipeline.

5. Key Technical Challenges & Resolutions

System stability required significant low-level troubleshooting:

Service Dependency Debugging: Diagnosed and fixed complex dependency chain issues for services like Bluetooth (dbus -> bluetoothd -> bluez).

Compiling Dependencies: Solved issues integrating specialized TUI applications (like aerc) with external password management (rbw) to ensure secure, uninterrupted workflow.

System Fixes: Solved the "corrupted screen" bug on system resume by implementing the tmux refresh-client command, ensuring visual state consistency post-suspend.

6. Results & Field Test

Performance Baseline: Confirmed the setup can run for over 12 hours on a full charge, consuming only ~7% of the battery per hour.

Conclusion: This setup can run for over 12 hours on a full charge, consuming only ~7% of the battery per hour. The requirements have been successfully met.

Successfully tested during the SSB IARU 1 Field Day in September 2025. The logger ran FB!

7. Photos

![Image](https://github.com/user-attachments/assets/ec68d3ae-0ce1-4485-945b-5b5c5a1aa4af)

![Image](https://github.com/user-attachments/assets/82f4d743-bc0f-4219-a75f-5a9079d7cc2a)

![Image](https://github.com/user-attachments/assets/e80826b2-66aa-4ca6-9ac0-7fcd1834d357)

![Image](https://github.com/user-attachments/assets/a37342e7-48e2-43af-8c1e-68f56b521e05)

![Image](https://github.com/user-attachments/assets/55ca950d-5efc-4956-8dba-ff581cbe1389)

73 de Nik SV1SYY
