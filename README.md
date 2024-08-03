# WSL

Here's a comprehensive list of WSL-specific commands and utilities for managing and using Windows Subsystem for Linux (WSL).

# Comprehensive List of WSL Commands

## WSL-Specific Commands

- **List all available WSL distributions:**
  ```bash
  wsl --list --verbose
  ```

- **Set a default WSL distribution:**
  ```bash
  wsl --set-default <DistributionName>
  ```

- **Install a new WSL distribution from the Microsoft Store:**
  ```bash
  wsl --install -d <DistributionName>
  ```

- **Unregister (uninstall) a WSL distribution:**
  ```bash
  wsl --unregister <DistributionName>
  ```

- **Run a specific command in a WSL distribution:**
  ```bash
  wsl -d <DistributionName> -- <command>
  ```

- **Convert a WSL distribution to WSL 2:**
  ```bash
  wsl --set-version <DistributionName> 2
  ```

- **Set WSL 2 as the default version:**
  ```bash
  wsl --set-default-version 2
  ```

- **Export a WSL distribution to a tar file:**
  ```bash
  wsl --export <DistributionName> <file.tar>
  ```

- **Import a WSL distribution from a tar file:**
  ```bash
  wsl --import <DistributionName> <InstallLocation> <file.tar>
  ```

- **Update WSL kernel:**
  ```bash
  wsl --update
  ```

- **Terminate a running WSL instance:**
  ```bash
  wsl --terminate <DistributionName>
  ```

- **Check the WSL status:**
  ```bash
  wsl --status
  ```

- **Access WSL filesystem from Windows:**
  ```bash
  explorer.exe .
  ```

- **Access a specific WSL distribution’s filesystem from Windows:**
  ```bash
  explorer.exe \\wsl$\<DistributionName>
  ```

- **Get WSL environment variables:**
  ```bash
  wsl -e env
  ```

- **Configure WSL network settings:**
  ```bash
  wsl --set-network <NetworkSettings>
  ```

## General Linux Commands in WSL

### System Information and Management

- **Get system information:**
  ```bash
  uname -a
  ```

- **Get detailed system information:**
  ```bash
  lsb_release -a
  ```

- **List hardware information:**
  ```bash
  lshw
  ```

- **Check available disk space:**
  ```bash
  df -h
  ```

- **Check memory usage:**
  ```bash
  free -h
  ```

- **List all running processes:**
  ```bash
  ps aux
  ```

- **Get detailed information about a specific process:**
  ```bash
  ps -p <PID> -o pid,comm,%cpu,%mem,etime
  ```

- **List all installed packages:**
  ```bash
  dpkg -l
  ```

- **Check system uptime:**
  ```bash
  uptime
  ```

- **Get current date and time:**
  ```bash
  date
  ```

### File and Directory Management

- **List files and directories:**
  ```bash
  ls -la
  ```

- **Create a new directory:**
  ```bash
  mkdir directoryname
  ```

- **Delete a directory:**
  ```bash
  rm -rf directoryname
  ```

- **Copy files:**
  ```bash
  cp sourcefile destinationfile
  ```

- **Move files:**
  ```bash
  mv sourcefile destinationfile
  ```

- **Delete files:**
  ```bash
  rm filename
  ```

- **Search for files:**
  ```bash
  find /path/to/search -name filename
  ```

- **Find files containing specific text:**
  ```bash
  grep -r "searchtext" /path/to/search
  ```

- **Get file or directory size:**
  ```bash
  du -sh filename
  ```

- **Get the last modified date of a file:**
  ```bash
  stat filename
  ```

- **Rename a file:**
  ```bash
  mv oldname newname
  ```

### Network Commands

- **Ping a host:**
  ```bash
  ping hostname
  ```

- **Trace route to a host:**
  ```bash
  traceroute hostname
  ```

- **Test network connection to a port:**
  ```bash
  nc -zv hostname port
  ```

- **View routing table:**
  ```bash
  netstat -rn
  ```

- **Flush DNS cache:**
  ```bash
  sudo systemd-resolve --flush-caches
  ```

- **Display network interfaces:**
  ```bash
  ip a
  ```

- **Display network connections:**
  ```bash
  ss -tuln
  ```

- **List open ports:**
  ```bash
  sudo lsof -i -P -n
  ```

- **Show firewall rules (using iptables):**
  ```bash
  sudo iptables -L
  ```

- **Show firewall rules (using ufw):**
  ```bash
  sudo ufw status verbose
  ```

- **Configure a static IP address (for systems using netplan):**
  ```bash
  sudo nano /etc/netplan/01-netcfg.yaml
  ```

### User and Group Management

- **List all users:**
  ```bash
  cut -d: -f1 /etc/passwd
  ```

- **Add a new user:**
  ```bash
  sudo adduser username
  ```

- **Delete a user:**
  ```bash
  sudo deluser username
  ```

- **Add a user to a group:**
  ```bash
  sudo usermod -aG groupname username
  ```

- **Remove a user from a group:**
  ```bash
  sudo deluser username groupname
  ```

- **List all groups:**
  ```bash
  cut -d: -f1 /etc/group
  ```

### Security and Permissions

- **Check file permissions:**
  ```bash
  ls -l filename
  ```

- **Change file permissions:**
  ```bash
  chmod 755 filename
  ```

- **Change file ownership:**
  ```bash
  chown user:group filename
  ```

- **Check process usage:**
  ```bash
  top
  ```

- **Stop a process by PID:**
  ```bash
  sudo kill <PID>
  ```

- **Start a process:**
  ```bash
  ./processname
  ```

### System and Application Logs

- **View system logs:**
  ```bash
  sudo journalctl
  ```

- **View specific log entries:**
  ```bash
  sudo journalctl -u servicename
  ```

- **Clear logs:**
  ```bash
  sudo journalctl --vacuum-time=1d
  ```

- **View authentication logs:**
  ```bash
  sudo cat /var/log/auth.log
  ```

### Package Management

- **Update package list:**
  ```bash
  sudo apt update
  ```

- **Upgrade all packages:**
  ```bash
  sudo apt upgrade
  ```

- **Install a new package:**
  ```bash
  sudo apt install packagename
  ```

- **Remove a package:**
  ```bash
  sudo apt remove packagename
  ```

- **Search for a package:**
  ```bash
  apt search packagename
  ```

- **Show package details:**
  ```bash
  apt show packagename
  ```

- **Clean up package cache:**
  ```bash
  sudo apt clean
  ```

### Penetration Testing and Security Tools

- **Nmap (Network scanner):**
  ```bash
  nmap -A target
  ```

- **Netcat (Network utility):**
  ```bash
  nc -l -p port
  ```

- **Metasploit Framework (Exploit framework):**
  ```bash
  msfconsole
  ```

- **Burp Suite (Web vulnerability scanner):**
  ```bash
  burpsuite
  ```

- **Wireshark (Network protocol analyzer):**
  ```bash
  wireshark
  ```

- **Aircrack-ng (Wireless network security):**
  ```bash
  airodump-ng wlan0
  ```

- **John the Ripper (Password cracking):**
  ```bash
  john --wordlist=/path/to/wordlist.txt /path/to/passwordfile
  ```

- **Hydra (Password cracking):**
  ```bash
  hydra -l username -P /path/to/passwordfile target service
  ```

- **SQLmap (SQL injection):**
  ```bash
  sqlmap -u "http://target/vulnerable.php?id=1" --dbs
  ```

- **Nikto (Web server scanner):**
  ```bash
  nikto -h http://target
  ```

- **Gobuster (Directory brute-forcing):**
  ```bash
  gobuster dir -u http://target -w /path/to/wordlist
  ```

- **WhatWeb (Web fingerprinting):**
  ```bash
  whatweb http://target
  ```

- **Wpscan (WordPress vulnerability scanner):**
  ```bash
  wpscan --url http://target
  ```

- **Nessus (Vulnerability scanner):**
  ```bash
  nessuscli update
  ```

### System Maintenance

- **Run a file system check:**
  ```bash
  sudo fsck /dev/sdX
  ```

- **Update the system:**
  ```bash
  sudo apt update && sudo apt upgrade
  ```

- **Reboot the system:**
  ```bash
  sudo reboot
  ```

- **Shutdown the system:**
  ```bash
  sudo shutdown now
  ```

### Power Management

- **Check battery status:**
  ```bash
  upower -i /org/freedesktop/UPower/devices/battery_BAT0
  ```

- **Manage power settings:**
  ```bash
  sudo pm-powersave
  ```

### System Monitoring

- **Monitor system resources:**
  ```bash
  htop
  ```

- **Check CPU usage:**
  ```bash
  mpstat
  ```

- **Monitor network traffic:**
  ```bash
  iftop
  ```

- **View disk usage:**
  ```bash
  df -h
  ```

- **Monitor disk I/O:**
  ```bash
  iostat
  ```

### File Editing

- **Edit files with nano:**
  ```bash
  nano filename
  ```

- **Edit files with vim:**
  ```bash
  vim filename
  ```

- **Edit files with emacs:**
  ```bash
  emacs filename
  ```

### WSL Integration with Windows

- **Launch a WSL distribution from Windows Terminal:**
  ```bash
  wt wsl -d <DistributionName>
  ```

- **Open a WSL distribution in a new Windows Terminal tab:**
  ```bash
  wt new-tab wsl -d <DistributionName>
  ```

- **Access a Windows directory from WSL:**
  ```bash
  cd /mnt/c/Users/YourUsername/PathToDirectory
  ```

- **Access a WSL directory from Windows Explorer:**
  ```bash
  explorer.exe \\wsl$\<DistributionName>\home\<Username>
  ```

- **Create a symbolic link to a Windows directory in WSL:**
  ```bash
  ln -s /mnt/c/Path/To/Windows/Directory /path/to/symlink
  ```

### Automation and Scripting

- **Run a shell script:**
  ```bash
  ./scriptname.sh
  ```

- **Make a script executable:**
  ```bash
  chmod +x scriptname.sh
  ```

- **Schedule tasks using cron:**
  ```bash
  crontab -e
  ```

- **List cron jobs:**
  ```bash
  crontab -l
  ```

- **Remove a cron job:**
  ```bash
  crontab -r
  ```

### Environmental Variables and Configuration

- **Set an environment variable temporarily:**
  ```bash
  export VAR_NAME=value
  ```

- **Set an environment variable permanently:**
  ```bash
  echo 'export VAR_NAME=value' >> ~/.bashrc
  source ~/.bashrc
  ```

- **Check current environment variables:**
  ```bash
  printenv
  ```

## Troubleshooting WSL Issues

- **Check for WSL updates:**
  ```bash
  wsl --update
  ```

- **Reset WSL networking:**
  ```bash
  wsl --shutdown
  ```

- **Check WSL logs:**
  ```bash
  wsl --log
  ```

- **Check for known issues:**
  ```bash
  wsl --status
  ```

This list provides a broad range of WSL-specific and general Linux commands useful for various tasks and system management within the WSL environment.
