# 🛡️ Host-Based Firewall Hardening (Beginner → SOC Core)
🎯 Goal
Secure an Ubuntu server using UFW, log attacks, and prove it works.
# 🔧 Setup
- Kali VM (attacker)
- Ubuntu VM (protected host)
# 🧪 Tasks
- Enable UFW
- Set default deny inbound
- Allow only required services
- Test attacks from Kali
- Analyze logs

# 📃Step-by-step Commands
```
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow ssh
sudo ufw allow 443
sudo ufw enable
```
![](https://github.com/Temijr2014/Host-Based-Firewall-Hardening-Beginner-SOC-Core-/blob/main/screen%20shot%201.png?raw=true)
# 🔥Attack Simulation
From Kali:
```
nmap -sS 192.168.1.11
```
The command nmap -sS <ubuntu_ip> is a Stealth Scan (also known as a SYN Scan). It is the most popular type of scan because it is fast and can often bypass simple firewalls.
# Summary of the command parts
- nmap: The tool itself (Network Mapper).
- -s: Stands for "Scan."
- S: Stands for "SYN."
- 192.168.1.11 The target you are testing.
![](https://github.com/Temijr2014/Host-Based-Firewall-Hardening-Beginner-SOC-Core-/blob/main/screen%20shot%203.png?raw=true)
# Log Analysis
```
sudo ufw logging high
sudo tail -f /var/log/ufw.log
```
(sudo ufw logging high)
This command tells the firewall how much "talking" it should do in its log files.
What it does: It sets the logging verbosity to High. In this mode, UFW records almost every packet that hits the firewall, regardless of whether it was allowed or denied, and it does so without "rate limiting" (meaning it won't skip entries even if there are thousands of them).

(sudo tail -f /var/log/ufw.log)
This is how you actually watch those logs.
tail: A command that shows the end (the "tail") of a file.
-f: Stands for "follow." It keeps the file open and updates your screen instantly as new lines are written to the log.
/var/log/ufw.log: The standard location where UFW stores its history.
![](https://github.com/Temijr2014/Host-Based-Firewall-Hardening-Beginner-SOC-Core-/blob/main/screen%20shot%202.png?raw=true)
