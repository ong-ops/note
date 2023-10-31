# Nmap Scripting Engine (NSE)

## Description

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

### NSE scripts - Installing

- `sudo apt update && sudo apt install nmap`
- `sudo wget -0 /usr/share/nmap/scripts/<script-name>.nse https://svn.nmap.org/nmap/scripts/<script-name>.nse` manually downloading the script from nmap
- `nmap --script-updatedb` update script.db to contain newly script

## Syntax

- `--script=<script-name>`
- `--script-args <script-name>.<argument>` add arguments
- `--script-help <script-name>` help

## Example

- `--script=http-fileupload-exploiter` Specific script 
- `--script=smb-enum-users,smb-enum-shares` Multiple scripts 
- `nmap -p 80 --script http-put --script-args http-put.url='/dav/shell.php',http-put.file='./shell.php'`
