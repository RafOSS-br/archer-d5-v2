# Archer D5 v2 Reverse Engineering

## Overview
This repository documents the complete reverse engineering process of the TP-Link Archer D5 v2 router.  
The goal is to provide a full reference of the hardware, firmware, and security research for the community.

## Objectives
- Document hardware components and interfaces.
- Extract and analyze the official firmware.
- Reverse engineer key binaries and services.
- Identify and report potential vulnerabilities.
- Provide tools and guides for reproducibility.
- Publish incremental progress for the community.

## Repository Structure
```

archer-d5-v2-reverse/
├── docs/
│   ├── hardware.md          # Board photos, chip info, pinouts
│   ├── uart\_logs.md         # Boot logs and UART notes
│   ├── firmware-analysis.md # Firmware extraction and structure
│   ├── reverse\_httpd.md     # Reversing the web server
│   └── security-findings.md # Vulnerabilities and exploits (if any)
├── firmware/
│   ├── original.bin         # Official firmware dump
│   └── unpacked/            # Extracted filesystems and binaries
├── tools/
│   ├── extract.sh           # Script to unpack firmware
│   └── repack.sh            # Script to rebuild firmware
└── README.md

```

## Progress (to be updated)
- [ ] Hardware teardown & photos
- [ ] UART access and boot log capture
- [ ] Firmware extraction
- [ ] Static analysis of binaries
- [ ] Reverse engineering of web server
- [ ] Vulnerability research
- [ ] Proof of concept exploits
- [ ] Community publication & write-ups

## Notes
- This work is for **educational and research purposes only**.  
- Any vulnerabilities found will follow a **responsible disclosure process**.  
- Contributions and collaboration are welcome.

## License
This repository is licensed under the GNU General Public License v2 (GPLv2).