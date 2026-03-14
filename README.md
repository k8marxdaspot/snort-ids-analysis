# Snort IDS Analysis

This project explores the architecture and functionality of Snort, an open-source intrusion detection and prevention system.

## Topics Covered

• Intrusion Detection Systems (IDS) vs Intrusion Prevention Systems (IPS)
• Signature-based vs anomaly-based detection
• Snort architecture and workflow
• Writing custom Snort rules
• Testing detection rules in a virtual lab

## Lab Setup

Testing was performed using:

• Kali Linux virtual machine
• Snort running in NIDS mode
• Nmap used to generate scanning traffic

## Example Detection Rule

Detect potential TCP port scanning activity:

alert tcp any any -> $HOME_NET any
(
flags: S;
msg:"TCP SYN Flag Detected!";
sid:1000000;
rev:1;
)
