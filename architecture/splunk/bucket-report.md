## Bucket listing report

<img width="1442" height="303" alt="image" src="https://github.com/user-attachments/assets/0094bbd1-f888-48f0-8f27-7e5d70137344" /> <br>


`index="main" sourcetype="auth-3" "Accepted"` <br>
`| eval ssh_login_time = _time` <br>
`| eval attacker_ip = rhost` <br>
`| join type=left attacker_ip [` <br>
    `search index="aws" sourcetype="aws:cloudtrail"` <br>
    `(eventName="ListBuckets" OR eventName="GetObject")` <br>
    `| rename sourceIPAddress as attacker_ip` <br>
    `| eval api_time = _time` <br>
    `| stats min(api_time) as api_time, values(eventName) as api_events by attacker_ip` <br>
`]` <br>
`| where api_time > ssh_login_time` <br>
`| table attacker_ip, host, ssh_login_time, api_time, api_events`
