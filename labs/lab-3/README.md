# Lab 3 - Investigating Lab Scenario
## Prerequisites
Before starting in this lab, you should import the necessary virtual machines which are available [here](https://drive.google.com/file/d/14I4InbVUhiAAeYTR-jW9cjbH59U1vjVH/view?usp=sharing)
* Once you start up the machines, the necessary service should start

The login creds for the machines are as follows:
```
VM01 - SSHMimik:
sshmimik:deathcon2025-decepticon-sshmimik
root:deathcon2025!

VM02 - Beacon Instance:
beacon:deathcon2025-beacon-sshmimik
```

## Lab Scenario
Your network has been compromised and attackers have breached several of your internet-accessible networking devices and logs have been wiped clean. Since the devices primarily stored data within the RAM, there were no artifacts that could be easily captured since the adversary power cycled the devices. Luckily, you deployed `sshmimik` on one of the compromised devices and logs were forwarded to your logging instance. Your job, analyze the captured log file from the compromised device and figure out what the attackers did. 

This scenario will be broken down into various tasks to analyze the attack chain and learn more about the attacker's infrastructure and their capabilities.

The log file to analyze is `ssh.json`. You can also query it on the Splunk instance by using the `sshmimik` index.
# Task 1: Find the Persistence
*Task*: Write a query that'll find the most ran command within the logged commands file. This query can be written using Splunk (`index=sshmimik`) or Bash-Fu & using `jq` to parse the JSON file
# Task 2: Unraveling Communication
*Task*: Decode the most ran command and take note of the way that the victim host communicates with the attacker's infrastructure. Answer the following about the communication:
- Q: What is the filename that the beacon is reaching out to download?
- Q: What is the IP address of the system being reached out to?
- Q: Where is the file being saved to?
# Task 3: File Analysis
*Task*: Analyze the initial file being downloaded and figure out what it's doing. Answer the following questions:
* Q: What is the purpose of the downloaded file?
* Q: What's the flag stored within the file?
# Task 4: Talking to the Attacker
*Task*: Visit the attacker's infrastructure and analyze it. Answer the following questions and find an additional flag.
* Q: Are there any other files hosted on the attacker's server?
* Q: What is the functionality of any other files hosted on the server?
# Task 5: Talking to the Attacker
*Task*: Replicate the initial communication we analyzed from lab 1 with the beacon server and analyze the output.
