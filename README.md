Project: Portable Contest Logging Laptop Setup

Project Status: Completed (Ready for Field Deployment)

1. Summary (Product Vision)

This project details the build and configuration of a highly-optimized, low-power portable laptop setup for amateur radio contesting. The primary goal was to create a reliable and efficient system for un-assisted contest logging, prioritizing battery longevity and a minimal resource footprint while retaining the ability to key the radio.

2. System Requirements

The "product" requirements for this build were:

Primary Goal: Very low power consumption to extend battery life for long portable operations.

Key Function: Must be able to key the radio for CW (Morse Code).

Software: Must run a lightweight, efficient logger that can be used in a minimal environment (non-graphical).

Connectivity: Internet (Wi-Fi/Bluetooth) is not required; focus is on un-assisted contesting.

Nice-to-Have: CAT control for frequency/mode logging.

3. Solution: Hardware & Software Stack

Hardware

Laptop: HP EliteBook 840 G2 (i5-5300U, 16GB RAM, 240GB SSD). Specs are overkill, but it's a robust multi-use machine.

Battery: New official HP extended battery.

Radio Interface: A custom-built USB to Serial (FTDI) interface with an optoisolator. The optoisolator is critical to prevent noise transfer from the laptop's switched-mode power supply to the radio's sensitive receiver.

Software Stack

Operating System: Debian 13 (Trixie), configured to boot into a headless TTY (terminal) environment to conserve maximum power.

Desktop Environment: XFCE (available via startx but not loaded by default).

Logging Software:

yfktest: (by Fabian Kurz, DJ5CW) A minimal, powerful contest logger written in Perl. It runs directly in the terminal and uses almost no resources.

tlf: An alternative logger (written in C) to be tested for even greater resource efficiency.

Terminal Environment: tmux (terminal multiplexer) is used to create a minimal "dashboard," splitting the screen into multiple terminal instances (e.g., one for the logger, one for system monitoring).

System Monitoring: btop (resource monitor) running in a separate tmux pane.

Power Management: TLP (Linux power management utility) running to manage battery and CPU frequency scaling.

4. Known Issues & Limitations

CAT Control: This is the main unresolved issue.

My EGV-9B transceiver does not support CAT.

My RGO-ONE transceiver's CAT (TS480 protocol) works perfectly in Windows (with OmniRig) but could not be made to cooperate with Hamlib in Linux, despite multiple attempts. This integration is beyond my current ability and I hope it will be added by the hamlib team.

Workaround: The absence of CAT is a low-priority problem. In yfktest, the band and frequency can be logged manually by typing them into the callsign field. This is an acceptable extra step for an un-assisted, single-band QRP category.

5. Field Test 1: Performance Baseline (HF Championship)

Test Setup: Participated in the HF Championship for ~3 hours in the QRP un-assisted category.

Environment: Ran the yfktest logger within a minimal tmux session.

Power Settings:

Wi-Fi & Bluetooth: OFF

CPU: Set to "power saving" governor.

Screen Brightness: 20% for the first hour, 10% for the remaining two.

Results (Power Consumption):

Battery went from 50% to 30% in approximately 3 hours.

btop reported a consistent power draw of 5-6 watts.

Conclusion: This setup can run for over 12 hours on a full charge, consuming only ~7% of the battery per hour. The requirements have been successfully met.

6. Field Test 2: Successfully tested during the SSB IARU 1 Field Day in September 2025. The logger ran FB!

7. Photos

![Image](https://github.com/user-attachments/assets/ec68d3ae-0ce1-4485-945b-5b5c5a1aa4af)

![Image](https://github.com/user-attachments/assets/82f4d743-bc0f-4219-a75f-5a9079d7cc2a)

![Image](https://github.com/user-attachments/assets/e80826b2-66aa-4ca6-9ac0-7fcd1834d357)

![Image](https://github.com/user-attachments/assets/a37342e7-48e2-43af-8c1e-68f56b521e05)

![Image](https://github.com/user-attachments/assets/55ca950d-5efc-4956-8dba-ff581cbe1389)

73 de Nik SV1SYY
