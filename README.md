# LimaCharlie-EDR | Sliver C2 Project

## Introduction

Welcome to the LimaCharlie-EDR | Sliver C2 Project! This project aims to demonstrate the integration between the Sliver command and control (C2) framework and the LimaCharlie endpoint detection and response (EDR) platform for advanced adversarial simulations and detection engineering.

### Part 1

- **Setting up VMs**: Set up two VMs - Ubuntu VM as an attack machine and Windows VM as the victim machine.
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F853e640e-9992-44c2-875b-1d5f446facc2_690x150.png" height="40%" width="40%" /><p/></p> <br/>
- **Disabling Windows Defender**: Disabled Windows Defender on the Windows VM to avoid interference during the attack process and enable better logging and event collection.
- **Installing Sysmon**: Installed Sysmon on the Windows endpoint to gather telemetry.
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F230b8e32-b1e1-4a8e-b593-37e395951e2f_456x94.png" height="40%" width="40%" /><p/></p> <br/>
- **Installing LimaCharlie EDR**: Installed and configured LimaCharlie EDR on the Windows VM to set up the Windows agent for further analysis.
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff821e410-d4d3-4161-a426-9d8ff348806c_610x392.png" height="40%" width="40%" /><p/></p> <br/>
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4741261f-691a-4f4f-9b9a-588d8eabd0a2_653x528.png" height="40%" width="40%" /><p/></p> <br/>

#### What is LimaCharlie?

LimaCharlie is a powerful SecOps Cloud Platform featuring a cross-platform EDR agent, log shipping/ingestion capabilities, and a threat detection engine.
LimaCharlie is a cloud-based security infrastructure that provides tools to build a security program at any scale. It is a cross-platform endpoint sensor that executes detection and response functionality in real-time. LimaCharlie enables organizations to detect and respond to threats, automate processes, reduce the number of vendors, and future-proof their security operations4. The platform is API-driven, allowing users to build the security they need and want.

### Part 2

- **Generating C2 Payload**: Generated a C2 payload using Sliver-server and downloaded it into the Windows VM (victim) via a temporary Python web server.
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb80969a7-5f41-48e9-9f38-3436ac4137ea_590x287.png" height="40%" width="40%" /><p/></p> <br/>
- **Executing C2 Payload**: Executed the C2 payload on the Windows VM, enabling interaction with the C2 session.
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3a465b98-3714-4ae0-9a96-064e39c4417c_621x131.png" height="40%" width="40%" /><p/></p> <br/>
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F083ddf4e-e1d7-4fee-a3ed-c57dbb3d7dd2_1033x111.png" height="40%" width="40%" /><p/></p> <br/>
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd0045b40-e5af-4527-8c11-f981e319c6d3_578x898.png" height="40%" width="40%" /><p/></p> <br/>
- **Observing EDR Telemetry**: Observed EDR telemetry to identify unknown files being downloaded and analyzed their behavior.
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5d490105-aa92-4075-81fd-cabc544ce55e_811x603.png" height="40%" width="40%" /><p/></p> <br/>
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fef8bec9c-1fbf-4d74-bf61-ffe21c3bda2e_787x324.png" height="40%" width="40%" /><p/></p> <br/>
- **Analyzing Suspected Executable**: Analyzed the suspected executable using tools like VirusTotal to determine its malicious nature.
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6baf71f9-387e-4255-bd49-5fc8c0b2dd36_1002x664.png" height="40%" width="40%" /><p/></p> <br/>
- **Analyzing Timeline EDR Telemetry**: Analyzed Timeline EDR telemetry to understand how the malicious payload was downloaded onto the Windows agent.
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff042ab3d-fc43-45f9-b02f-2a7a0bc0e047_1063x466.png" height="40%" width="40%" /><p/></p> <br/>
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8715db71-8990-43a5-b9d6-e47e0c5c6562_1125x290.png" height="40%" width="40%" /><p/></p> <br/>

### Part 3

- **Credential Theft with Sliver C2**: Used Sliver C2 for stealing credentials by dumping the lsass.exe process from memory on the victim system for performing detection and response analysis.
- **Creating Detection and Response Rule**: Created a Detection and Response rule in the LimaCharlie EDR for alerting on specific events related to lsass.exe.
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F226aca14-9255-4040-af85-809fa7c988d5_1348x886.png" height="40%" width="40%" /><p/></p> <br/>
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5e95b67b-eba5-466a-95ad-927b00848dc7_581x392.png" height="40%" width="40%" /><p/></p> <br/>
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fed440bb9-b0ea-4a0c-a66b-c6017100b3d6_719x213.png" height="40%" width="40%" /><p/></p> <br/>
- **Testing and Tuning Rules**: Dynamically tested and tuned the rules in the Detection and Response engine to ensure accuracy and minimize false positives before deploying them in the production environment.
- **Hunt for Evil**: Knowing what’s normal on a Windows host helps cut through the noise to quickly locate potential malware.
  [Download PDF](https://sansorg.egnyte.com/dl/oQm41D67D6)




