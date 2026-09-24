## Secure Server

### Step 1: Patching
* **Command:** 'sudo apt update && sudo apt upgrade'
* **Troubleshooting:** ran command with 1 sudo and ran into
* **Note:** 'apt' would be 'dnf' for Red Hat distros

### Step 2: SSH Hardening
* **EC2 Security rules:** Inbound security rules were restricted to my IP and the AWS EC2 instance prefix,
* Ran 'sudo sshd -T' to verify proper configuration
