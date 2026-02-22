Assets
	•	EC2 instances
	•	Credentials / IAM roles
	•	Network access
	•	Logs and telemetry

Threat Actors
	•	External attacker
	•	Compromised cloud credentials
	•	Misconfigured IAM permissions

Attack Techniques
Mapped to MITRE ATT&CK, for example:
	•	SSH brute force (T1110)
	•	Privilege escalation (T1068)
	•	Persistence (T1053)
	•	Cloud API abuse (T1098)

Assumptions
	•	Single AWS account
	•	No internal malicious users
	•	Limited lateral movement

Out of Scope
	•	Physical access
	•	Zero-day kernel exploits
	•	Multi-account compromise

Reducing false positives
	•	Correlating multiple signals
	•	Detecting sequences (e.g., API change → SSH → privilege escalation)
	•	Making detections defendable
