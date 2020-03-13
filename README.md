# diskwipe
This is a tool to verify SSD and HDD storage devices health and status and to wipe them properly without damaging SSD drives by writing zeroes all over them.

## Description
This tool has many features to diagnose and wipe your drives:

- SMART data and errors analysis
- Reporting of detected errors or values above builtin tresholds
- Autodetection of HDD/SSD
- Perform read and write tests along with IOPS benchmark with 4k 32qdepth read and writes
- Wipe using ATA secure erase to avoidf altering flash based drives lifespan
- SSD Life Remaining checks and reporting
- JSON output for further integration (historical drive health database for example)

## Reported data
Below is the data reported by the tool once ran against a storage device
- Device model number
- Device serial number
- Device type (SSD or HDD)
- Problematic SMART errors
- [On SSD] Wear leveling count estimation
- Device age (power on hours)
- Device write speed and IOPS
- Device read speed and IOPS
- Wipe method
- Wipe estimated time
- Wipe completion time
- Wipe job status

## Requirements
This script relies on a few system utilities to be able to run. This will run on RHEL and Debian based distributions.
Please also run this as root to ensure you can collect data and wipe drives.
- smartmontools (smartctl)
- hdparm
- dd
- lsblk
- jq
- fio
- basic system utilities such as grep, awk, etc...

## Installation
The tool can be deployed with the following commands:
```
wget https://raw.githubusercontent.com/gtcomm/diskwipe/master/diskwipe -O /usr/bin/diskwipe
chmod +x /usr/bin/diskwipe
```
## Usage
Launch it with the following command:
```
diskwipe /dev/sdb
```

## Notes
This tool is meant to run on a system dedicated to wipe drives. You must install this tool on a main OS drive and then connect all other drives to wipe them.

## GloboTech
GloboTech is a canadian hosting services provider based in Montreal. We offer bare metal and cloud based hosting solutions combined with best in class technical support to suit all your needs. Our team is dedicated since 1999 to $

Visit our website at www.globo.tech today to get yourself a new server!
