# Snort IDS Analysis – Summary

This project explores the architecture and functionality of **Snort**, an open-source network intrusion detection and prevention system (IDS/IPS).

The research examines how intrusion detection systems operate, how Snort processes network traffic, and how custom detection rules can be written and tested.

📄 **Full Paper:** [Full Paper (PDF)](https://github.com/k8marxdaspot/snort-ids-analysis/blob/main/paper/snort-ids-analysis.pdf)

---

## Key Concepts Covered

- Intrusion Detection Systems (IDS) vs Intrusion Prevention Systems (IPS)  
- Signature-based detection  
- Anomaly-based detection  
- Stateful protocol analysis  
- Network packet inspection

---

## Snort Architecture

Snort processes packets through several major components:

1. **Packet Capture (DAQ)** – captures packets from the network  
2. **Preprocessors** – prepare packets for analysis (e.g., reassembling fragments)  
3. **Detection Engine** – compares traffic against rule sets  
4. **Alert / Logging System** – records suspicious activity

---

## Example Detection Rule

Example rule detecting potential TCP SYN port scanning:

```snort
alert tcp any any -> $HOME_NET any
(
flags: S;
msg:"TCP SYN Flag Detected!";
sid:1000000;
rev:1;
)
```
This rule generates an alert whenever a TCP packet with a SYN flag is detected targeting the monitored network.

---

## Lab Environment

Testing was performed using:

- Kali Linux virtual machine
- Snort running in NIDS mode
- Nmap used to generate scanning traffic
- Custom rules stored in `local.rules`

---

## What This Demonstrates

This project demonstrates how rule-based intrusion detection systems analyze packet metadata and payloads to detect suspicious network activity.

It also highlights the importance of maintaining updated rule sets and combining multiple detection approaches to improve network security.
