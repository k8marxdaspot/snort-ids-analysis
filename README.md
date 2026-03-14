# Snort IDS Analysis

This repository contains a research project exploring **Snort**, an open-source intrusion detection and prevention system.

The project examines how intrusion detection systems analyze network traffic, apply rule sets, and generate alerts when suspicious activity is detected.

## Overview

Intrusion Detection Systems (IDS) are an important component of modern network security infrastructure. This project explores how Snort functions as a Network Intrusion Detection System (NIDS) and demonstrates how custom rules can be used to detect malicious activity.

## Contents

📄 **Research Paper**

- [Full Research Paper](https://github.com/k8marxdaspot/snort-ids-analysis/raw/main/paper/snort-ids-analysis.pdf)

📖 **Project Summary**

- [Readable Summary](paper/summary.md)

## Example Snort Rule

Detect potential TCP port scanning activity:

```snort
alert tcp any any -> $HOME_NET any
(
flags: S;
msg:"TCP SYN Flag Detected!";
sid:1000000;
rev:1;
)
```
## Tools Used

- Snort
- Kali Linux
- Nmap
- Virtual Machine networking

## Future Improvements

- Implement additional Snort detection rules
- Test anomaly detection approaches
- Analyze real network traffic datasets
- Compare Snort with Suricata

## References

- Cisco Talos. *Snort 3 Rule Writing Guide*  
  https://docs.snort.org

- Scarfone, K., & Mell, P. *Guide to Intrusion Detection and Prevention Systems (NIST SP 800-94)*  
  https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-94.pdf

- IBM Security. *What is an Intrusion Detection System (IDS)?*  
  https://www.ibm.com/think/topics/intrusion-detection-system
