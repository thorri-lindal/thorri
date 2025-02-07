A quick and effective setup guide for optimizing Ubuntu/Linux Mint with security, performance, and stability improvements.

---

> [!Enable Automatic Updates  ]
> ```bash
> sudo apt install unattended-upgrades -y
> sudo dpkg-reconfigure unattended-upgrades
> ```
> This enables **automatic security updates** in the background.

---

> [!warning]
> 
> ## 🔒 Secure SSH  
>  **By default, SSH allows root login and runs on the standard port 22, making it a target for attacks. These changes will harden SSH security.**
> 
> Edit the SSH configuration file:
> ```bash
> sudo nano /etc/ssh/sshd_config
> ```
> Modify these lines (or add them if missing):
> ```
> PermitRootLogin no
> Port 2222
> ```
> Restart SSH to apply changes:
> ```bash
> sudo systemctl restart ssh
> ```
> 

---

> [!warning]
> ## 🔥 Enable Firewall 
> To install and configure UFW (Uncomplicated Firewall), run:
> ```bash
> sudo apt install ufw -y
> sudo ufw enable
> sudo ufw default deny incoming
> sudo ufw default allow outgoing
> ```
> Check firewall status:
> ```bash
> sudo ufw status verbose
> ```
> 

---

> [!NOTE]
> ## 🚀Optimize Swap Usage  
> > **Reducing reliance on swap improves system performance, especially on systems with SSDs.**
> 
> To lower swappiness (default is often too high):
> ```bash
> echo 'vm.swappiness=10' | sudo tee -a /etc/sysctl.conf
> sudo sysctl -p
> ```
> 

---

> [!NOTE]
> ## ⚡ Enable App Preloading  
> > **Preload frequently used applications to improve launch speeds.**
> 
> To install preload:
> ```bash
> sudo apt install preload -y
> ```
> Preload runs automatically in the background after installation.

---

> [!NOTE]
> ## 📡 Disable Wi-Fi Power Saving  
> >  **Prevents Wi-Fi disconnections caused by aggressive power-saving settings.**
> 
> To disable power saving for Intel Wi-Fi adapters:
> ```bash
> echo 'options iwlwifi power_save=0' | sudo tee /etc/modprobe.d/iwlwifi.conf
> sudo systemctl restart NetworkManager
> ```
> 

---