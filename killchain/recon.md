## T1595.001 (Scanning IP Blocks)
Attacker confirms services: SSH, HTTP are running on the host machine

**NMAP Command**

NMAP -sV (detect services on ports) -p- (all ports) -A (Operating system detection) <br>

<img width="830" height="796" alt="Screenshot 2026-04-30 at 10 05 07 AM" src="https://github.com/user-attachments/assets/34af6a4f-5a3c-48f5-aaa6-d4fe4bf3b195" />

Associated Detection: <a href="../architecture/splunk/portscan-report.md">DET0817</a>

Associated Mitigation: Cannot be easily mitigated with preventative controls. Focus should be on limit exposed services and data, while
proactively identifying adversaries and vulnerabilities.
