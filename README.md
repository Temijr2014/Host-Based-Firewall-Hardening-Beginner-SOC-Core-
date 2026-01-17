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
