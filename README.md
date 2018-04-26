# Project 9 - Honeypot

Time spent: **3-4** hours spent in total

> Objective: Setup a honeypot and intercept some attempted attacks in the wild.

## Dionaea with HTTP
> "Dionaea is 'meant to be a nepenthes successor, embedding python as scripting language, using libemu to detect shellcodes, supporting ipv6 and tls.'"
- Any issues you encountered
  - Couldn't immediately load the webpage to my MHN admin portal using my public IP address. This was solved following instructions on this codepath discussion post: https://discussions.codepath.com/courses/cybersecurity_university/questions/can-t-connect-to-mhn-admin-web-app
  - The problem here was that my GCP firewall was configured by default to block TCP port 80 which allows http traffic, and this resulted in the webpage not loading in my browser
  - Going into the "Firewall Rule Details" in the GCP interface and creating a new rule to allow tcp port 80 traffic, helped solve the problem
- A summary of the data collected: number of attacks, number of malware samples, etc
  - Number of attacks: 1263 and counting
  - Number of malware samples: 0
    - My assumption is that maleware samples are found in the "Payloads" tab
  - Deployment time: ~1am on 4/26/18 EST
- Any unresolved questions raised by the data collected:
  - When scanning for open ports using nmap, I found that more than just three ports open
    
## Snort
> "Snort is an 'open source intrusion prevention system capable of real-time traffic analysis and packet logging.'"
- Any issues you encountered
  - When creating a new VM for honeypot-2, the quotation mark wrapping the VM name in the command kept italicizing by itself, thus giving me an error that the name was unacceptable
  - This was too subtle to catch right away, but to solve, I pasted the entire command into a texteditor and made sure the command was pasted into the terminal without the quotation mark italicizing
- A summary of the data collected: number of attacks, number of malware samples, etc
  - Number of attacks: 339 and counting
  - Number of malware samples: 39 pages worth
    - My assumption is that maleware samples are found in the "Payloads" tab
    - Payload filter was set to "snort.alerts"
  - Deployment time: ~3am on 4/26/18 EST
  
## Wordpot
> "Wordpot is a 'Wordpress honeypot which detects probes for plugins, themes, timthumb and other common files used to fingerprint a Wordpress installation.'"
- Any issues you encountered
  - None
- A summary of the data collected: number of attacks, number of malware samples, etc
  - Number of attacks: 0
  - Number of malware samples: 0
  - Deployment time: ~3:30am on 4/26/18 EST
- Any unresolved questions raised by the data collected
  - Based on the plethora of attacks that we saw for Wordpress in week 7, I assumed this honeypot would accumulate the most attacks of the 3 honeypots set up, despite it being deployed last. Why did this honeypot not attract any (known) attacks/attackers? 

