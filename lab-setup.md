# Snort IDS Lab Setup

This project includes a small virtual lab used to test custom Snort intrusion detection rules.

## Environment

The testing environment consisted of:

- Kali Linux virtual machine
- Snort running in **NIDS mode**
- Windows host machine generating test traffic
- Host-only network adapter for controlled traffic monitoring

## Installing Snort

Snort can be installed on Kali Linux using:

sudo apt update
sudo apt install snort

## Running Snort in NIDS Mode

To start Snort listening on a network interface:

snort -i 3 -c /etc/snort/snort.conf -A console

Parameters:

- `-i` : network interface
- `-c` : configuration file
- `-A console` : print alerts to the console

## Custom Rules

Custom rules were added to the `local.rules` file.

Example rule detecting TCP SYN port scanning:

alert tcp any any -> $HOME_NET any
(
flags: S;
msg:"TCP SYN Flag Detected!";
sid:1000000;
rev:1;
)

## Generating Test Traffic

To test the detection rules, port scanning traffic was generated using **Nmap**:

nmap -sS <target-ip>

This produced TCP SYN packets which triggered alerts in Snort.

## Observing Alerts

When the rule was triggered, Snort produced console output similar to:

[**] TCP SYN Flag Detected! [**]

This confirmed that the custom rule was functioning correctly.