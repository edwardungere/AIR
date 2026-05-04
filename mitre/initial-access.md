## T1110.001 (Brute force: Password Guessing)

Hydra can be used to crack passwords. Specifying the -l and -p will prompt for specific login user and password information.<br>
Using -L and -P allows you to use a list of usernames and passwords <br>

In this stage, the attacker is attempting initial access by running a list of passwords against a common user account name root. <br>
By default, Linux systems will not allow ssh into a machine using the root account.

<img width="1764" height="230" alt="image" src="https://github.com/user-attachments/assets/76b57143-dc34-4e69-85d2-d678a2c2b69b" /> <br>

Associated Detection: <a href=../architecture/splunk/DET0551/>DET0551</a>

Associated Mitigation: <a href=../architecture/splunk/DET0551/brute-force-alert.md>DET0551</a>

