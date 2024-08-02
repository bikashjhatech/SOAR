# SOAR

Security teams manage the increasing volume of alerts and incidents by automating many of the manual processes involved in threat detection and response. This project utilizes Tines as the SOAR platform and LimaCharlie as the EDR solution to streamline these processes.

## Project Details

- **Windows 10 Virtual Machine Setup**: Created a Windows 10 virtual machine in Microsoft Azure cloud.


- **LimaCharlie EDR Account** Creation: Set up an account on the LimaCharlie EDR platform to manage endpoint security.
- **Installation Keys Creation**: Generated installation keys in LimaCharlie to ensure that only authorized devices connect to the EDR environment.
- **Agent Installation**: Downloaded the LimaCharlie agent on the Windows 10 VM and installed it using the sensor key to establish secure communication with LimaCharlie.
- **LaZagne Execution**: LaZagne, a tool capable of extracting passwords from various operating systems, browsers, and applications, was downloaded and executed on the Windows 10 VM to simulate a security incident.
- **D&R Rule Configuration**: Configured a D&R (Detection & Response) rule in LimaCharlie to detect the execution of LaZagne. Upon execution, the rule triggered detections that logged details such as Time, Title, Command Line, File Hash, File Path, Hostname, and IP Address.
- **Tines And LimaCharlie Integration**: Registered an account on Tines and integrated it with LimaCharlie by copying the Webhook URL from a Tines Story (Playbook) and pasting it into the destination host in LimaCharlie’s outputs section. This enabled the transfer of detections from LimaCharlie to Tines for further automation.
- **Slack and Tines Integration**: Created a Slack account and set up a new channel named alerts for security notifications. Added Tines to Slack under the Apps section and configured the Slack integration in Tines by adding credentials and copying the Channel ID of the alerts channel. This setup allowed events from LimaCharlie to be forwarded to Tines, which then sends detailed notifications to the Slack alerts channel.
- **Incident Response Workflow**: A user prompt was created in Tines with the option to isolate the device (Yes/No). If the user selects "No", a Slack message is sent saying, "Your computer was not isolated, please investigate."
- **Isolation**: Sensor ID and API key were added to Tines. If the user selects "Yes", the workflow isolates the host computer and sends a Slack message saying, "Your computer is isolated now."
