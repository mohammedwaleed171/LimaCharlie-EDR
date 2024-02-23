# LimaCharlie-EDR | Sliver C2 Project

## Introduction

Welcome to the LimaCharlie-EDR | Sliver C2 Project! This project aims to demonstrate the integration between the Sliver command and control (C2) framework and the LimaCharlie endpoint detection and response (EDR) platform for advanced adversarial simulations and detection engineering.

## Setting up Ubuntu VM(Attack machine) and Windows VM(Victim machine) | Installing Sysmon and Limacharlie EDR

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
LimaCharlie is a cloud-based security infrastructure that provides tools to build a security program at any scale. It is a cross-platform endpoint sensor that executes detection and response functionality in real-time. LimaCharlie enables organizations to detect and respond to threats, automate processes, reduce the number of vendors, and future-proof their security operations.
## Enacting adversarial activity and observing EDR Telemetry

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

## Detection Engineering - Writing and tuning detection rules for alerting/blocking the malicous activity

- **Credential Theft with Sliver C2**: Used Sliver C2 for stealing credentials by dumping the lsass.exe process from memory on the victim system for performing detection and response analysis.
- **Creating Detection and Response Rule**: Created a Detection and Response rule in the LimaCharlie EDR for alerting on specific events related to lsass.exe.
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F226aca14-9255-4040-af85-809fa7c988d5_1348x886.png" height="40%" width="40%" /><p/></p> <br/>
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5e95b67b-eba5-466a-95ad-927b00848dc7_581x392.png" height="40%" width="40%" /><p/></p> <br/>
  <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fed440bb9-b0ea-4a0c-a66b-c6017100b3d6_719x213.png" height="40%" width="40%" /><p/></p> <br/>
- **Testing and Tuning Rules**: Dynamically tested and tuned the rules in the Detection and Response engine to ensure accuracy and minimize false positives before deploying them in the production environment.
- **Hunt for Evil**: To identify malicious log activity we must first know what's normal. Knowing what’s normal on a Windows host helps cut through the noise to quickly locate potential malware.
  SANS DFIR [Hunt Evil](https://sansorg.egnyte.com/dl/oQm41D67D6) gives an overview of what normal windows activity looks like.

  ## YARA Signature Setup and Automation for Sliver C2 Payload Detection

  #### Setup YARA Signature for Sliver C2 Payload:
  - Utilize YARA signatures provided by UK National Cyber Security Centre (NCSC) for Sliver C2 payload.
  - Access LimaCharlie's "Automation" > "YARA Rules" section.
  - Add YARA rules for Sliver and Sliver process.
    <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F268295ea-fac3-453c-9d83-34da5bcbbe0a_778x790.png" height="40%" width="40%" /><p/></p> <br/>
 
  #### Configure D&R (Detect & Respond) Rules:
  - Create rules to detect YARA detections not involving a PROCESS object and those specifically involving a PROCESS object.
  - Set up actions for responding to YARA detections, such as reporting and tagging.
    <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F98a15dae-7894-490d-a2ef-824c1059d526_814x388.png" height="40%" width="40%" /><p/></p> <br/>
    <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8c37a0fb-918e-43e7-a9f8-f305be0bd2df_816x372.png" height="40%" width="40%" /><p/></p> <br/>
 
  #### Test YARA Signature:
  - Manually initiate a YARA scan using the EDR sensor on a Windows VM to test the Sliver payload detection.
    <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F97670b36-2032-4fa2-b90c-d4ccf3739a9a_774x216.png" height="40%" width="40%" /><p/></p> <br/>
    <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd59ccc4d-d539-4acb-96ca-bf93e04a6d73_814x432.png" height="40%" width="40%" /><p/></p> <br/>
    <p align="center"><img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa2bff541-94e5-40be-aa56-c43d2d6ee62f_1608x316.png" height="40%" width="40%" /><p/></p> <br/>

   #### Automate YARA Scanning:
  - Create rules to automatically scan newly downloaded EXE files and processes launched from the Downloads directory.
  - Set up actions to report and initiate YARA scans for detected files and processes.
    
    ```yaml
    #Detect Block
    event: NEW_DOCUMENT
    op: and
      rules:
        - op: starts with
     path: event/FILE_PATH
      value: C:\Users\
        - op: contains
      path: event/FILE_PATH
      value: \Downloads\
      - op: ends with
        path: event/FILE_PATH
          value: .exe
    '''yaml
        #Detect Block
        - action: report
          name: EXE dropped in Downloads directory
          - action: task
        command: >-
          yara_scan hive://yara/sliver -f "{{ .event.FILE_PATH
              }}"
          investigation: Yara Scan Exe
        suppression:
          is_global: false
          keys:
          - '{{ .event.FILE_PATH }}'
          - Yara Scan Exe
            max_count: 1
            period: 1m

   #### Test Automation Rules:
  - Simulate the creation of a new EXE file in the Downloads directory to trigger the automated YARA scan.
  - Execute the Sliver payload to generate a new process launched from the Downloads directory to trigger the automated YARA scan.

    #### Verification:
  - Check the Detections tab to verify that the automation rules correctly detected and responded to the simulated activities, including alerts for EXE file  creation and YARA detections.





