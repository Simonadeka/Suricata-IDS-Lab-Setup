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
