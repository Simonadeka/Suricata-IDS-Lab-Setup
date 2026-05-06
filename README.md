# Suricata IDS Lab Setup

## Description
This repository documents the process of setting up Suricata IDS (Intrusion Detection System) in a VirtualBox lab environment. The goal is to learn Suricata configuration, rule management, real-time alerting, and troubleshooting.

## README
### Suricata IDS Lab Setup
A step-by-step guide to setting up Suricata IDS in a VirtualBox lab environment.

**Contents:**
- Installation and configuration of Suricata
- Rule management and updates  
- Testing real-time alerting
- Troubleshooting and tuning
- Screenshots and examples

**Lab Environment:**
- VirtualBox
- Ubuntu 22.04 VM (Suricata Sensor)
- Ubuntu 22.04 VM (Suricata Controller)

## Prerequisites
* VirtualBox installed
* Ubuntu 22.04 VM (Suricata Sensor)
* Another Ubuntu 22.04 VM (Suricata Controller) 
* Basic Linux knowledge

## Step 1: Install Suricata
Run this command on your Suricata Sensor VM:
```bash
sudo apt update
sudo apt install suricata

## Step 2: Configure Suricata
Open the Suricata config file:
```bash
sudo nano /etc/suricata/suricata.yaml
'''''

Update the `rule-files` section to look like this:

```yaml
rule-files:
    - /var/lib/suricata/rules/suricata.rules

![Suricata Config Screenshot](screenshots/suricata-config.png)
### 3. Update Rules
Run the update command to get the latest rules:
```bash
sudo suricata-update
![Suricata Update Screenshot](screenshots/Suricata%20update.png)
Check the rule file configuration:
```bash
sudo nano /etc/suricata/rules/suricata.rules
![Rule File Config Screenshot](screenshots/Rule%20file%20conf.png)

### 4. Fix Rule File Path
If you get a path error, update the rule file path in `suricata.yaml`:
```bash
sudo nano /etc/suricata/suricata.yaml
![Fix Rule File Path Screenshot](screenshots/Fix%20rule%20file%20path.png)
### 5. Start Suricata
Start Suricata in IDS mode:
```bash
sudo suricata -c /etc/suricata/suricata.yaml -i eth0
![Suricata Active Screenshot](screenshots/Suricata%20Active.jpeg)
![Suricata Loaded Successfully Screenshot](screenshots/Suricata%20loaded%20successfully.jpeg)
### 6. Test Installation
Run a test to confirm Suricata is working:
```bash
sudo suricata --test -c /etc/suricata/suricata.yaml
![Install Suricata Screenshot](screenshots/Install%20suricata.png)

### Quick Reference - All Commands
```bash
# 1. Update Suricata rules
sudo suricata-update

# 2. Check rule file configuration  
sudo nano /etc/suricata/rules/suricata.rules

# 3. Fix rule file path in config
sudo nano /etc/suricata/suricata.yaml

# 4. Start Suricata in IDS mode
sudo suricata -c /etc/suricata/suricata.yaml -i eth0

# 5. Test installation
sudo suricata --test -c /etc/suricata/suricata.yaml
```
### Repository Structure
```
suricata-ids-lab-setup/
├── README.md
├── screenshots/
│   ├── Rule file conf.png
│   ├── Fix rule file path.png
│   ├── Suricata Active.jpeg
│   ├── Suricata loaded successfully.jpeg
│   └── Install suricata.png
```

---
### Connect With Me

- **LinkedIn**: simon.adeka/
- **GitHub**: Simonadeka

Built with 🚀 by Simon Friday Adeka
