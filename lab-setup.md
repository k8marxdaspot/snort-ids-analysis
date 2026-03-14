# Lab Setup

This project tested Snort detection rules using a virtual lab environment.

## Environment

- Kali Linux virtual machine
- Snort running in NIDS mode
- Host-only network adapter
- Windows host machine running Nmap

## Running Snort

Example command:

snort -i 3 -c /etc/snort/snort.conf -A console

## Testing Detection

To generate alerts, Nmap was used to perform port scanning against the monitored host.