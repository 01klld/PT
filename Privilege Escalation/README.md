#  **Privilege Escalation Techniques**

> **"With great power comes great responsibility!"** 🕷️

## User Privileges Types :

![User Privileges](https://i.pinimg.com/736x/79/3f/3b/793f3b27e00d7926546ce1a3018fe397.jpg)

## 📚 **Resources**

###  **General**
- [Hack The Box Academy - Linux Privilege Escalation](https://academy.hackthebox.eu/course/preview/linux-privilege-escalation)
- [GTFOBins](https://gtfobins.github.io/) *(Bypass restrictions with system binaries!)*
- [Awesome Privilege Escalation](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md)
- [TryHackMe - Common Linux Privilege Escalation](https://www.secjuice.com/tryhackme-common-linux-privilege-escalation/)
- [PEASS (Privilege Escalation Awesome Scripts Suite)](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite)
- [Watson (Windows Privilege Escalation)](https://github.com/rasta-mouse/Watson)
- [Evil-WinRM](https://github.com/Hackplayers/evil-winrm)
- [LOLBAS (Living Off The Land Binaries and Scripts)](https://lolbas-project.github.io/)

---

## 🐧 **Linux Privilege Escalation**
- [Basic Linux Privilege Escalation](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/)
- [Abusing Sudo - Linux Privilege Escalation](https://touhidshaikh.com/blog/2018/04/11/abusing-sudo-linux-privilege-escalation/)
- [Docker Privilege Escalation](https://www.hackingarticles.in/docker-privilege-escalation/)
- [Quick and Dirty Linux Privilege Escalation](https://johnjhacking.com/blog/linux-privilege-escalation-quick-and-dirty/)

---

## 🖥️ **Windows Privilege Escalation**
- [FuzzySecurity - Windows Privilege Escalation](http://www.fuzzysecurity.com/tutorials/16.html)
- [Windows Privilege Escalation - guif.re](https://guif.re/windowseop)
- [Windows Privilege Escalation Methods for Pentesters](https://pentest.blog/windows-privilege-escalation-methods-for-pentesters/)
- [Windows Local Privilege Escalation - HackTricks](https://book.hacktricks.xyz/windows/windows-local-privilege-escalation)

---

## 💡 **Pro Tips for Privilege Escalation** 

1. **Enumerate Everything** 🔍 - Use `linpeas`, `winpeas`, `pspy`, and `enum4linux`.
2. **Check for Misconfigurations** 🛠️ - Inspect `sudo -l`, `capabilities`, `SUID`/`SGID` binaries.
3. **Leverage GTFOBins & LOLBAS** 🤖 - Exploit system binaries for privilege escalation.
4. **Monitor Running Processes** 🏃 - Use `pspy` to detect exploitable cron jobs.
5. **Abuse Kernel Exploits** ⚠️ - Check kernel versions (`uname -a`, `systeminfo`).
6. **Pivot Smartly** 🔄 - Look for SSH keys or stored credentials.
7. **Stay Updated** 📅 - Follow security blogs, CTF writeups, and GitHub repos.

> _"Exploit smart, not hard!"_ 

