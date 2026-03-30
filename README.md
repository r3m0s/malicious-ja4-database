```latex
4D 61 6C 69 63 69 6F 75 73  4A 41 34  44 61 74 61 62 61 73 65
  __  __      _ _    _                  _  _  _ _    ___       _        _                  
 |  \/  |__ _| (_)__(_)___ _  _ ___  _ | |/_\| | |  |   \ __ _| |_ __ _| |__  __ _ ___ ___ 
 | |\/| / _` | | / _| / _ \ || (_-< | || / _ \_  _| | |) / _` |  _/ _` | '_ \/ _` (_-</ -_)
 |_|  |_\__,_|_|_\__|_\___/\_,_/__/  \__/_/ \_\|_|  |___/\__,_|\__\__,_|_.__/\__,_/__/\___|
```

# Malicious Network Fingerprints
This is a minimal dataset and collection of potentially malicious JA3 and JA4 TLS fingerprints collected from a wide range of blogs and sandbox reports. Fingerprints were collected by searching for malicious sha-256 checksums of known Malware samples on the Internet.

## Data Sources
This is a short list of resources to gain further insights into commonly used Malware and tools that communicate over the Internet using varying protocols and libraries.

### Malware Databases
The following providers serve Malware samples through a public database or service for research purposes.

#### [MalwareBazaar from abuse.ch and Spamhaus](https://bazaar.abuse.ch/browse)
Database with Application Programming Interface (API) to share specific Malware samples and track newly observed ones.

#### [vx-underground](https://vx-underground.org)
Collects Malware source code, samples, and papers.

### Encyclopaedias
These web services convey in-depth knowledge about current Malware trends and usages.

#### [MITRE ATT&CK's Software List](https://attack.mitre.org/software)
MITRE collects tools and Malware that cover their techniques and could be or are known to be used by adversaries. While tools can refer to built-in OS Software such as `net`, `certutil` or `netstat`, Malware is intended to be used solely for malicious purposes.

#### [Malpedia by Fraunhofer Institute for Communication, Information Processing and Ergonomics FKIE](https://malpedia.caad.fkie.fraunhofer.de/library)
Focus is on Malware families and their recent uses in campaigns or targeted attacks by threat actors. The library links to in-depth articles.

#### [Malware Trends Tracker by Any.Run](https://any.run/malware-trends)
Any.Run is a sandbox service that tracks recent trends of Malware usage.

#### [Top n Malware by Center for Internet Security (CIS)](https://www.cisecurity.org/insights/blog/top-10-malware-q4-2025)
Each quarter Center for Internet Security (CIS) publishes a list of their top 10 observed Malware variants. The collection is based on CIS Cyber Threat Intelligence (CTI) and open-source research.

### Context Information
#### [VirusTotal](https://www.virustotal.com/gui/home/search)
VirusTotal can be used to get further context information about a specific Malware sample based on its sha-256 file hash.

## Fingerprinting Network Traffic
[JA4 Fingerprinting by FoxIO-LLC](https://github.com/FoxIO-LLC/ja4) is a comprehensive suite of tools that can be used as a plugin within `tshark` or WireShark to monitor malicious network traffic and fingerprint clients and servers.