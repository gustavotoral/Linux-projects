## Secure Server

### Step 1: Patching
* **Command:** ```sudo apt update && sudo apt upgrade```
* **Goal**: update packages before installing or configuring services
* **Troubleshooting:** ran command with 1 sudo and ran into
* **Note:** ```apt``` would be ```dnf``` for Red Hat distros

### Step 2: SSH Hardening
* **EC2 Security rules:** Inbound security rules were restricted to my IP and the AWS EC2 instance prefix required for browser based SSH
* **Audit SSH config:** ```sudo sshd -T``` to verify proper configuration

### Step 3: Reviewed SSH logs
* Given I was slow to verify SSH configuration, I was curious if there was enough time for bots to attempt logins so I checked for suspicious logins and did not find any.
* Command: ```sudo journactl -u -ssh --since "today"``` + ```last```

### Step 3: Audited Listening Ports
* **Command:** ```sudo ss -tulpn```
* Learned: tupln = tcp / udp / listening / process / numeric and that ss replaced netstat
