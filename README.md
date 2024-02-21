# LimaCharlie-EDR | Sliver C2 Project
<h3>PART 1</h3>
-Set up 2 VMs - Ubuntu VM as an attack machine and Windows VM as the victim machine.<br/>
-Disabling Windows defender on Windows VM for no interference during the attack process to enable collecting logs and events for further analysis.<br/>
-Installed Sysmon for gathering telemetry on windows endpoint.<br/>
-Install LimaCharlie EDR on Windows VM and setting up for the windows agent where we perform further analysis.<br/>
-LimaCharlie is a very powerful “SecOps Cloud Platform”. It not only comes with a cross-platform EDR agent, but also handles all of the log shipping/ingestion 
  and has a threat detection engine.<br/>
-Setting up attack system on Linux VM - Sliver C2 Framework.<br/>
