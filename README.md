# LimaCharlie-EDR | Sliver C2 Project

## Introduction

Welcome to the LimaCharlie-EDR | Sliver C2 Project! This project aims to demonstrate the integration between the Sliver command and control (C2) framework and the LimaCharlie endpoint detection and response (EDR) platform for advanced adversarial simulations and detection engineering.

### Part 1

- **Setting up VMs**: Set up two VMs - Ubuntu VM as an attack machine and Windows VM as the victim machine.
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F853e640e-9992-44c2-875b-1d5f446facc2_690x150.png" height="40%" width="40%" /><p/></p> <br/>


- **Disabling Windows Defender**: Disabled Windows Defender on the Windows VM to avoid interference during the attack process and enable better logging and event collection.
- **Installing Sysmon**: Installed Sysmon on the Windows endpoint to gather telemetry.
- **Installing LimaCharlie EDR**: Installed and configured LimaCharlie EDR on the Windows VM to set up the Windows agent for further analysis.

#### What is LimaCharlie?

LimaCharlie is a powerful SecOps Cloud Platform featuring a cross-platform EDR agent, log shipping/ingestion capabilities, and a threat detection engine.

### Part 2

- **Generating C2 Payload**: Generated a C2 payload using Sliver-server and downloaded it into the Windows VM (victim) via a temporary Python web server.
- **Executing C2 Payload**: Executed the C2 payload on the Windows VM, enabling interaction with the C2 session.
- **Observing EDR Telemetry**: Observed EDR telemetry to identify unknown files being downloaded and analyzed their behavior.
- **Analyzing Suspected Executable**: Analyzed the suspected executable using tools like VirusTotal to determine its malicious nature.
- **Analyzing Timeline EDR Telemetry**: Analyzed Timeline EDR telemetry to understand how the malicious payload was downloaded onto the Windows agent.

### Part 3

- **Credential Theft with Sliver C2**: Used Sliver C2 for stealing credentials by dumping the lsass.exe process from memory on the victim system.
- **Creating Detection and Response Rule**: Created a Detection and Response rule in the LimaCharlie EDR for alerting on specific events related to lsass.exe.
- **Testing and Tuning Rules**: Dynamically tested and tuned the rules in the Detection and Response engine to ensure accuracy and minimize false positives before deploying them in the production environment.



