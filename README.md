```latex
4D 61 6C 69 63 69 6F 75 73  4A 41 34  44 61 74 61 62 61 73 65
  __  __      _ _    _                  _  _  _ _    ___       _        _                  
 |  \/  |__ _| (_)__(_)___ _  _ ___  _ | |/_\| | |  |   \ __ _| |_ __ _| |__  __ _ ___ ___ 
 | |\/| / _` | | / _| / _ \ || (_-< | || / _ \_  _| | |) / _` |  _/ _` | '_ \/ _` (_-</ -_)
 |_|  |_\__,_|_|_\__|_\___/\_,_/__/  \__/_/ \_\|_|  |___/\__,_|\__\__,_|_.__/\__,_/__/\___|
```

![JA3](https://img.shields.io/badge/JA3-8A2BE2?style=flat)
![JA4](https://img.shields.io/badge/JA4-00BC65?style=flat)
![Static Badge](https://img.shields.io/badge/dataset_size-4-EA582D?style=flat)
![Static Badge](https://img.shields.io/badge/attributes-23-FAC306?style=flat)
![Commit Activity](https://img.shields.io/github/commit-activity/m/badges/shields)

<div align="left">
<picture>
<img src="img/logo.png" alt="Malicious JA4 TLS Fingerprint Dataset" width="300">
</picture>
</div>

# Malicious Network Fingerprints
## :pushpin: Introduction
This is a minimal dataset and collection of potentially malicious JA3 and JA4 TLS fingerprints collected from a wide range of blog posts, sandbox reports, and lab environments. Fingerprints were collected by searching for malicious sha-256 checksums of known Malware samples on the Internet. Furthermore, penetration testing and red teaming frameworks were evaluated in dedicated lab environments to generate fingerprints for common Command and Control (C2) frameworks.

> [!CAUTION]
> This dataset is not necessarily indicating malicious network traffic when applied within detection solutions. Solely relying on TLS fingerprints will return many False Positives (FP). It shall be used cautiously with adequate review processes in place and whenever possible with further context information available.

## :vertical_traffic_light: Coverage
- [x] Havoc
- [x] Sliver
- [x] Covenant
- [x] GraphSpy
- [x] TokenTactics
- [x] TokenTacticsV2
- [x] AADInternals
- [ ] ROADtools
- [ ] AzureHound
- [ ] Metasploit
- [ ] Mythic

## :open_file_folder: Data Sources
This is a short list of resources to gain further insights into commonly used Malware and tools that communicate over the Internet using varying protocols and libraries.

### :beetle: Malware Databases
The following providers serve Malware samples through a public database or service for research purposes.

#### [MalwareBazaar from abuse.ch and Spamhaus](https://bazaar.abuse.ch/browse)
Database with Application Programming Interface (API) to share specific Malware samples and track newly observed ones.

#### [vx-underground](https://vx-underground.org)
Collects Malware source code, samples, and papers.

### :books: Encyclopaedias
These web services convey in-depth knowledge about current Malware trends and usages.

#### [Malpedia by Fraunhofer Institute for Communication, Information Processing and Ergonomics FKIE](https://malpedia.caad.fkie.fraunhofer.de/library)
Focus is on Malware families and their recent uses in campaigns or targeted attacks by threat actors. The library links to in-depth articles.

#### [MITRE ATT&CK's Software List](https://attack.mitre.org/software)
MITRE collects tools and Malware that cover their techniques and could be or are known to be used by adversaries. While tools can refer to built-in OS Software such as `net`, `certutil` or `netstat`, Malware is intended to be used solely for malicious purposes.

#### [Malware Trends Tracker by Any.Run](https://any.run/malware-trends)
Any.Run is a sandbox service that tracks recent trends of Malware usage.

#### [Top n Malware by Center for Internet Security (CIS)](https://www.cisecurity.org/insights/blog/top-10-malware-q4-2025)
Each quarter Center for Internet Security (CIS) publishes a list of their top 10 observed Malware variants. The collection is based on CIS Cyber Threat Intelligence (CTI) and open-source research.

### :hourglass: Sandbox Services
- [Joe Sandbox by Joe Security LLC](https://www.joesandbox.com)
- [VirusTotal](https://www.virustotal.com/gui/home/search)
- [Hybrid Analysis](https://hybrid-analysis.com/#homepage-search-string)
- [Triage by Recorded Future](https://tria.ge)
- [ANY.RUN](https://app.any.run)

## :mag_right: Fingerprinting Network Traffic
[JA4 Fingerprinting by FoxIO-LLC](https://github.com/FoxIO-LLC/ja4) is a comprehensive suite of tools that can be used as a plugin within `tshark` or WireShark to monitor network traffic, fingerprinting potentially malicious clients and servers.

## :fountain: Minimal HTTPS Sink for Service Emulation
This repository contains a minimal [HTTPS sink](src/https-sink.py) which allows capturing malicious traffic that would otherwise target real services in the Internet on your local machine. The code is written in Python, follow the instructions printed in the output to generate a server certificate container to run the HTTPS webserver. The webserver does not have any functionality, the goal is simply to have a sink where requests that target specific domain names are redirected to. You will have to modify `/etc/hosts` file to direct various other domains apart from localhost itself towards `127.0.0.1:443`.