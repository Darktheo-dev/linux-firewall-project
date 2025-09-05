# linux-firewall-project
Ubuntu VM firewall lab project – using UFW, iptables, and DNS overrides to block specific sites
# Linux Firewall Project

## Overview
This project configures an Ubuntu virtual machine as a basic firewall. It demonstrates how to block specific websites and IP ranges using UFW, iptables, and DNS overrides. The goal was to apply networking and security fundamentals in a hands-on environment.

## Motivation
As a sophomore at Drexel University preparing for my first co-op, I built this project to gain practical experience with Linux firewall tools and to demonstrate the ability to configure, test, and document network security features. This project goes beyond coursework by simulating a real-world security control scenario.

## Tools & Technologies
- Ubuntu Linux (running in a UTM VM on macOS with Apple Silicon)
- UFW (Uncomplicated Firewall)
- iptables
- DNS overrides (`/etc/hosts`)
- Ping (ICMP) and Firefox browser for verification

## Implementation Steps
1. Enabled the firewall:
   ```bash
   sudo ufw enable

 ## blocked website ip ranges using subnet masks

  sudo ufw deny out to 157.240.0.0/16

## blocks All Facebook servers in that range.
  3.	Redirected domains locally for stronger blocking:
	•	Edited /etc/hosts to point domains like facebook.com to 127.0.0.1
	4.	Verified blocking:
	•	ping facebook.com → 100% packet loss
	•	Browser attempted to load → error: Unable to connect

Results
	•	Successfully blocked access to targeted sites such as Facebook and WWE.
	•	Verified blocking both at the command-line level and in the web browser.
	•	Demonstrated understanding of firewall rules, subnetting, and DNS resolution.

How to Explore the Project
	•	Project Documentation (PDF): Linux-Firewall-Showcase.pdf
	•	Screenshots Folder: Includes outputs of firewall rules, ping results, and browser error messages.

Lessons Learned
	•	Using subnet masks (e.g., /16) allows blocking of large ranges of IP addresses efficiently.
	•	DNS redirection through /etc/hosts provides additional control at the hostname level.
	•	Clear documentation and testing are critical for proving firewall effectiveness.

Future Improvements
	•	Automate firewall rule setup with shell scripts.
	•	Explore logging and monitoring to track blocked attempts.
	•	Expand project to compare UFW with other Linux firewall tools such as nftables.
