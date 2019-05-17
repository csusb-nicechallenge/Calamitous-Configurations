# Calamitous-Configurations
## Challenge Summary
Two machines require security configurations in order to be up to company standard: Windows 7 Workstation-Desk and Linux Based Prod-Web. Unfortunately, both have gaping vulnerabilities, and need to be fixed before any unforseen errors or attacks can occur. 
## Known Issues
The linux server Prod-Web occasionally fails to open programs, such as Terminal and Web Browser. To fix this issue, simply reboot the machine and log back into the playerone account.
## Viewing Enabled Windows Services
1.	"Turn Windows features on or off" within the Control Panel > Programs
## Windows Firewall Configurations
1.	Telnet and TFTP are seperate rules within the firewall 
    - Inbound Rules govern what programs and ports are able to access the machine from remote locations, including the internet
    - Outbound Rules are the program and port connections permitted (or denied) to leave the host machine
## Discovering the Linux Version
1.	/etc directory contains the system-release file, which will display the OS distribution when accessed with the command cat
## Making SSH Adjustments
1.	Within /etc is the /ssh directory, which contains the file sshd_config
2.	Edit the sshd_config file using a Linux text editor
    - Different distributions of Linux may have different text editors
    - Although many function similarly, the commands necessary to save text or exit the file will usually differ 
3.	Remove the # from PubkeyAuthentication yes, as well as AuthorizedKeysFile .ssh/authorized_keys 
4.	Change PermitEmptyPasswords to no
5.	Change UsePAM to yes
6.	Change PermitRootLogin to without-password
