# Nmap Scripting Engine (NSE)

- Extending nmap functionality
- Written in the **Lua**
- Used for many things (e.g. scan vuln, auto exploit, recon)

### Categories

- `safe` won't effect the target
- `intrusive` not safe, affect the target
- `vuln` scan vuln
- `exploit` attempt to exploit vuln
- `auth` attempt to bypass authen (e.g. Log into an FTP server anonymously)
- `brute` attempt to bruteforce credentials
- `discovery` attempt to query running services for info about network (e.g. query SNMP server)
- https://nmap.org/book/nse-usage.html

### NSE scripts

- https://nmap.org/nsedoc/scripts/ On site
- `/usr/share/nmap/scripts` Find scripts that are stored in Linux
- `/usr/share/nmap/scripts/script.db` Search installed scripts

## Command

Install an nmap script
```
Step 1: Update apt and install nmap
sudo apt update && sudo apt install nmap

Step 2: Manually download the scritp from nmap
sudo wget -0 /usr/share/nmap/scripts/<script_name>.nse https://svn.nmap.org/nmap/scripts/<script_name>.nse

Step 3: Update the script.db to contain newly script
nmap --script-updatedb
```

Nmap script document
```
nmap --script-help <script_name>
```

Specific scripts
```
nmap --script=<script_name_1>[,<script_name_2>]
```

Add script arguments
```
nmap -p 80 --script <script_name> --script-args <script_name>.<arg1>='<value>'[,<script_name>.<arg2>='<value>']```

