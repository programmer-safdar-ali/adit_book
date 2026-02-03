# Chapter 3: Server Administration - Windows & Linux

## Introduction

Server administration is a critical skill for IT professionals, particularly for Assistant Directors IT who must oversee and manage server infrastructure. This chapter covers both Windows and Linux server administration, focusing on essential concepts, tools, and best practices for effective server management.

## Windows Server Administration

### Active Directory: Users, Groups, OUs, GPOs

Active Directory (AD) is Microsoft's directory service for Windows domain networks.

#### Users
- **Purpose**: Represent individual people or services in the domain
- **Attributes**: Username, password, contact info, permissions
- **Creation**: Through GUI (Active Directory Users and Computers) or PowerShell
- **Best Practices**:
  - Follow naming conventions
  - Implement strong password policies
  - Regular account reviews
  - Account disablement/deletion for departed employees

#### Groups
- **Types**:
  - Security Groups: Assign permissions and rights
  - Distribution Groups: Email distribution only
- **Scope**:
  - Domain Local: Access resources in same domain
  - Global: Contain users from same domain
  - Universal: Contain users/groups from any domain in forest
- **Group Nesting**: Following AGUDLP model (Account, Global, Universal, Domain Local, Permissions)

#### Organizational Units (OUs)
- **Purpose**: Administrative boundaries for delegation and policy application
- **Benefits**: Group Policy application, administrative delegation
- **Design**: Reflect organizational structure or administrative needs
- **Best Practices**: Plan OU structure before implementation

#### Group Policy Objects (GPOs)
- **Purpose**: Centrally manage and configure operating systems, applications, and user settings
- **Components**:
  - Computer Configuration: System-wide settings
  - User Configuration: User-specific settings
- **Processing Order**: Local, Site, Domain, OU ( LSDOU )
- **Linking**: Link GPOs to sites, domains, or OUs
- **Enforcement**: Override inheritance with "Enforced" option
- **Filtering**: Security filtering and WMI filtering

### DNS and DHCP Configuration

#### DNS (Domain Name System)
- **Purpose**: Resolves hostnames to IP addresses
- **Record Types**:
  - A: IPv4 address mapping
  - AAAA: IPv6 address mapping
  - CNAME: Canonical name alias
  - MX: Mail exchange server
  - NS: Name server
  - PTR: Reverse lookup (IP to hostname)
  - SRV: Service location
- **Zones**:
  - Primary: Read-write copy of zone data
  - Secondary: Read-only copy (zone transfer)
  - Stub: Contains only authoritative servers
- **Forwarders**: Delegate queries to other DNS servers
- **Root Hints**: IP addresses of root DNS servers

#### DHCP (Dynamic Host Configuration Protocol)
- **Purpose**: Automatically assign IP addresses and network configuration
- **Lease Process**: Discover, Offer, Request, Acknowledge (DORA)
- **Scope**: Range of IP addresses to distribute
- **Options**: DNS servers, default gateway, WINS servers
- **Reservations**: Permanent IP assignment to specific MAC addresses
- **Super Scope**: Group multiple scopes for single subnet
- **Failover**: High availability for DHCP services

### File and Print Services

#### File Services
- **File Servers**: Store and share files across network
- **Shares**: Shared folders accessible over network
- **Permissions**: NTFS (file system) and Share (network) permissions
- **DFS (Distributed File System)**: Logical view of distributed shares
- **Shadow Copies**: Point-in-time file recovery
- **Quotas**: Limit disk space usage per user/share

#### Print Services
- **Print Server**: Manages printers and print jobs
- **Printer Pooling**: Multiple identical printers as one queue
- **Priority Levels**: Assign priority to different printer queues
- **Security**: Control who can print and manage printers
- **Driver Management**: Install and maintain printer drivers

### IIS Web Server Management

#### IIS (Internet Information Services)
- **Role**: Web server for hosting websites and applications
- **Features**: HTTP/HTTPS, FTP, SMTP, NNTP
- **Architecture**: Worker processes, application pools, sites
- **Application Pools**: Isolate applications for security and stability
- **Sites**: Bindings, virtual directories, authentication methods

#### Management Tools
- **IIS Manager**: GUI for managing IIS
- **PowerShell**: Automated management and configuration
- **Web Deploy**: Deploy applications to IIS

#### Security Considerations
- **Authentication**: Anonymous, Basic, Digest, Windows, Certificate
- **Authorization**: Control access to resources
- **SSL/TLS**: Encrypt communications
- **Request Filtering**: Block malicious requests

### Remote Desktop Services

#### Components
- **RDS Connection Broker**: Load balance and reconnect sessions
- **RDS Gateway**: Secure remote access through firewall
- **RDS Licensing**: Manage RDS CALs
- **RD Web Access**: Web portal for remote access

#### Session Hosts
- **RemoteApp**: Publish individual applications
- **Session Desktops**: Full desktop experience
- **Licensing**: Per-device or per-user licensing

### Windows Server Roles and Features

#### Common Roles
- **Domain Controller**: Directory services
- **File Server**: File sharing and storage
- **DHCP Server**: IP address assignment
- **DNS Server**: Name resolution
- **Hyper-V**: Virtualization platform
- **Web Server (IIS)**: Web hosting
- **Print and Document Services**: Printing services
- **Active Directory Certificate Services**: PKI services

#### Role Installation
- **Server Manager**: GUI-based installation
- **PowerShell**: Automated installation with Add-WindowsFeature
- **DISM**: Offline image modification

### PowerShell Scripting for Automation

#### PowerShell Basics
- **Cmdlets**: Verb-Noun command structure (Get-Service, Set-Item)
- **Pipeline**: Pass objects between cmdlets
- **Providers**: Access data stores (Registry, Certificates, etc.)

#### Scripting Concepts
- **Variables**: Store values ($variable = "value")
- **Loops**: For, foreach, while
- **Conditionals**: If, elseif, else
- **Functions**: Reusable code blocks
- **Parameters**: Input to functions

#### Common Administrative Tasks
```powershell
# Get system information
Get-ComputerInfo

# Manage services
Get-Service | Where-Object {$_.Status -eq "Running"}
Start-Service -Name "ServiceName"

# User management
New-LocalUser -Name "username" -Password $password
Add-LocalGroupMember -Group "Administrators" -Member "username"

# Registry management
Get-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion"
Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion" -Name "ValueName" -Value "NewValue"
```

### Windows Registry Management

#### Registry Structure
- **HKEY_CLASSES_ROOT**: File associations and COM classes
- **HKEY_CURRENT_USER**: User-specific settings
- **HKEY_LOCAL_MACHINE**: System-wide settings
- **HKEY_USERS**: All user profiles
- **HKEY_CURRENT_CONFIG**: Current hardware profile

#### Management Tools
- **regedit.exe**: GUI registry editor
- **reg.exe**: Command-line registry tool
- **PowerShell**: Get-ItemProperty, Set-ItemProperty, Remove-ItemProperty

#### Best Practices
- **Backup**: Export registry before making changes
- **Testing**: Test changes in non-production environment
- **Documentation**: Document all changes
- **Minimize Changes**: Only change when necessary

## Linux Server Administration

### Linux Distributions: RedHat, Ubuntu, CentOS, Debian

#### Red Hat Enterprise Linux (RHEL)
- **Target**: Enterprise environments
- **Support**: Commercial support available
- **Package Manager**: RPM/YUM/DNF
- **Licensing**: Subscription-based

#### Ubuntu Server
- **Target**: Both enterprise and personal use
- **Package Manager**: APT/DEB
- **Release Cycle**: Regular (every 6 months) and LTS (every 2 years)
- **Community**: Large community support

#### CentOS/Rocky Linux/AlmaLinux
- **Target**: RHEL-compatible free alternative
- **Package Manager**: RPM/YUM/DNF
- **Focus**: Stability and compatibility with RHEL

#### Debian
- **Target**: Stable server platform
- **Package Manager**: APT/DEB
- **Focus**: Stability over cutting-edge features
- **Derivatives**: Ubuntu, Mint, Kali

### Command Line Operations and Bash Scripting

#### Essential Commands
```bash
# File operations
ls -la                    # List files with details
cd /path/to/directory     # Change directory
pwd                       # Print working directory
cp source dest            # Copy files
mv source dest            # Move/rename files
rm file                   # Remove files
mkdir directory           # Create directory
rmdir directory           # Remove empty directory
touch file                # Create/update timestamp

# System information
uname -a                  # System information
df -h                     # Disk usage
free -h                   # Memory usage
top/htop                  # Process monitoring
ps aux                    # Process list
whoami                    # Current user
hostname                  # System hostname

# Text processing
cat file                  # Display file contents
less file                 # View file with scrolling
grep "pattern" file       # Search for pattern
find /path -name "*.txt"  # Find files by name
wc file                   # Count lines, words, chars
sort file                 # Sort lines
uniq file                 # Remove duplicate lines
```

#### Bash Scripting
```bash
#!/bin/bash
# Shebang line to specify interpreter

# Variables
MY_VAR="Hello World"
USER_NAME=$(whoami)

# Conditionals
if [ "$MY_VAR" == "Hello World" ]; then
    echo "Match found!"
elif [ "$MY_VAR" == "Goodbye" ]; then
    echo "Goodbye found!"
else
    echo "No match"
fi

# Loops
for i in {1..5}; do
    echo "Number: $i"
done

while [ $counter -lt 5 ]; do
    echo "Counter: $counter"
    ((counter++))
done

# Functions
my_function() {
    echo "This is a function"
    return 0
}

# Calling function
my_function
```

### File Permissions: chmod, chown, umask

#### Permission Types
- **Read (r)**: 4 - View file contents
- **Write (w)**: 2 - Modify file contents
- **Execute (x)**: 1 - Run file as program

#### Permission Categories
- **Owner (u)**: User who owns the file
- **Group (g)**: Group associated with the file
- **Others (o)**: Everyone else

#### chmod Command
```bash
# Numeric method
chmod 755 file          # rwx for owner, rx for group/others
chmod 644 file          # rw for owner, r for group/others
chmod 600 file          # rw for owner only

# Symbolic method
chmod u+x file          # Add execute to owner
chmod g-w file          # Remove write from group
chmod o-rwx file        # Remove all permissions from others
```

#### chown Command
```bash
chown user file         # Change owner
chown user:group file   # Change owner and group
chown :group file       # Change group only
```

#### umask Command
- **Purpose**: Sets default permissions for new files
- **Default**: Usually 022 (creates 644 for files, 755 for directories)
- **Calculation**: Subtract from 666 (files) or 777 (directories)

### User and Group Management

#### User Management
```bash
# Create user
sudo useradd username
sudo useradd -m -s /bin/bash username  # Create home directory and set shell

# Set password
sudo passwd username

# Modify user
sudo usermod -aG groupname username    # Add user to group
sudo usermod -d /new/home username     # Change home directory

# Delete user
sudo userdel username
sudo userdel -r username               # Delete user and home directory
```

#### Group Management
```bash
# Create group
sudo groupadd groupname

# Modify group
sudo groupmod -n newname oldname       # Rename group
sudo gpasswd -a username groupname     # Add user to group
sudo gpasswd -d username groupname     # Remove user from group

# Delete group
sudo groupdel groupname
```

#### Useful Files
- **/etc/passwd**: User account information
- **/etc/shadow**: Encrypted passwords
- **/etc/group**: Group information
- **/etc/gshadow**: Group passwords

### Package Management: apt, yum, dnf

#### APT (Debian/Ubuntu)
```bash
# Update package list
sudo apt update

# Upgrade packages
sudo apt upgrade
sudo apt full-upgrade    # Also handles dependencies

# Install packages
sudo apt install packagename
sudo apt install package1 package2

# Remove packages
sudo apt remove packagename
sudo apt purge packagename   # Remove config files too

# Search packages
apt search keyword
apt show packagename

# Clean up
sudo apt autoremove        # Remove unused packages
sudo apt autoclean         # Clean package cache
```

#### YUM/DNF (Red Hat/CentOS)
```bash
# Update packages
sudo yum update
sudo dnf update

# Install packages
sudo yum install packagename
sudo dnf install packagename

# Remove packages
sudo yum remove packagename
sudo dnf remove packagename

# Search packages
yum search keyword
dnf search keyword

# List installed packages
rpm -qa
dnf list installed
```

### Service Management: systemd, init

#### systemd (Modern Systems)
```bash
# Service management
sudo systemctl start servicename
sudo systemctl stop servicename
sudo systemctl restart servicename
sudo systemctl reload servicename    # Reload config without restart

# Service status
systemctl status servicename
systemctl is-active servicename
systemctl is-enabled servicename

# Enable/disable services
sudo systemctl enable servicename    # Start at boot
sudo systemctl disable servicename   # Don't start at boot

# List services
systemctl list-units --type=service
systemctl list-unit-files --type=service
```

#### init (Legacy Systems)
```bash
# Service management
sudo service servicename start
sudo service servicename stop
sudo service servicename restart

# Check status
sudo service servicename status

# Enable/disable at boot
sudo chkconfig servicename on/off    # RHEL/CentOS
sudo update-rc.d servicename enable  # Debian/Ubuntu
```

### SSH Configuration and Management

#### SSH Server Configuration
- **Main file**: /etc/ssh/sshd_config
- **Key settings**:
  - Port: SSH port (default 22)
  - PermitRootLogin: Whether root can log in directly
  - PasswordAuthentication: Allow password authentication
  - PubkeyAuthentication: Allow key-based authentication
  - AllowUsers/AllowGroups: Specify allowed users/groups

#### SSH Client Usage
```bash
# Basic connection
ssh username@hostname
ssh -p port_number username@hostname

# Key-based authentication
ssh-keygen -t rsa -b 4096
ssh-copy-id username@hostname

# SSH tunneling
ssh -L local_port:target_host:target_port username@ssh_server
ssh -R remote_port:target_host:target_port username@ssh_server
```

#### SSH Security Best Practices
- Change default port
- Disable root login
- Use key-based authentication
- Implement fail2ban for brute force protection
- Regular updates of SSH software

### Linux File System Hierarchy

#### Root Directory Structure
- **/**: Root directory
- **/bin**: Essential command binaries
- **/boot**: Boot loader files
- **/dev**: Device files
- **/etc**: Configuration files
- **/home**: User home directories
- **/lib**: System libraries
- **/media**: Mount points for removable media
- **/mnt**: Temporary mount points
- **/opt**: Add-on application software
- **/proc**: Process information pseudo-filesystem
- **/root**: Home directory for root user
- **/sbin**: System binaries
- **/srv**: Service data
- **/tmp**: Temporary files
- **/usr**: Secondary hierarchy for user data
- **/var**: Variable files (logs, spool, etc.)

## Common Server Administration Tasks (Windows & Linux)

### Server Hardening and Patch Management

#### General Hardening Steps
- **Disable unnecessary services**
- **Configure firewall rules**
- **Apply security updates regularly**
- **Implement strong authentication**
- **Monitor system logs**
- **Remove default accounts**
- **Configure secure remote access**

#### Patch Management
- **Windows**: Windows Update, WSUS (Windows Server Update Services)
- **Linux**: Package managers (apt, yum, dnf), unattended-upgrades
- **Schedule**: Regular patching cycles
- **Testing**: Test patches in non-production before deployment
- **Rollback**: Have rollback plans for failed updates

### Backup and Recovery Strategies

#### Backup Types
- **Full Backup**: Complete copy of all data
- **Incremental**: Changes since last backup
- **Differential**: Changes since last full backup
- **Mirror**: Exact copy of source

#### 3-2-1 Backup Rule
- 3 copies of data
- 2 different media types
- 1 offsite copy

#### Recovery Strategies
- **RTO (Recovery Time Objective)**: Maximum acceptable downtime
- **RTO (Recovery Point Objective)**: Maximum acceptable data loss
- **Disaster Recovery Plans**: Procedures for different scenarios
- **Testing**: Regular testing of backup restoration

### Virtualization: VMware vSphere, Hyper-V, KVM, Proxmox

#### VMware vSphere
- **ESXi**: Hypervisor
- **vCenter**: Management platform
- **vMotion**: Live migration of VMs
- **DRS**: Distributed Resource Scheduler
- **HA**: High Availability

#### Microsoft Hyper-V
- **Host**: Physical server running Hyper-V
- **VMs**: Virtual machines
- **Integration Services**: Guest additions
- **Live Migration**: Move VMs between hosts
- **Replica**: VM replication for DR

#### KVM (Kernel-based Virtual Machine)
- **Hypervisor**: Runs in kernel space
- **Management**: libvirt, virt-manager, virsh
- **Storage**: Various backends (local, NFS, iSCSI)
- **Networking**: Bridged, NAT, isolated networks

#### Proxmox VE
- **Platform**: Open-source virtualization environment
- **Technologies**: KVM and LXC
- **Management**: Web interface
- **High Availability**: Built-in clustering

### Monitoring and Performance Tuning

#### Windows Monitoring
- **Performance Monitor**: Built-in tool for counters
- **Event Viewer**: System and application logs
- **Task Manager**: Process monitoring
- **Resource Monitor**: Detailed resource usage
- **PowerShell**: Automated monitoring scripts

#### Linux Monitoring
- **top/htop**: Process monitoring
- **iostat**: I/O statistics
- **vmstat**: Virtual memory statistics
- **sar**: System activity reporter
- **nmon**: System performance monitor
- **Log files**: /var/log/ directory

#### Performance Tuning Areas
- **CPU**: Process scheduling, affinity
- **Memory**: Swap configuration, caching
- **Disk**: I/O scheduling, partitioning
- **Network**: Buffer sizes, offloading

### Log Management and Analysis

#### Windows Logs
- **System Log**: Hardware and system events
- **Application Log**: Application events
- **Security Log**: Security-related events
- **Setup Log**: Windows installation events

#### Linux Logs
- **/var/log/messages**: General system messages
- **/var/log/syslog**: System logging (Ubuntu/Debian)
- **/var/log/auth.log**: Authentication logs (Ubuntu/Debian)
- **/var/log/secure**: Authentication logs (RHEL/CentOS)

#### Log Analysis Tools
- **Windows**: Event Viewer, PowerShell, Sysinternals tools
- **Linux**: grep, awk, sed, journalctl (systemd), logrotate
- **Centralized**: ELK Stack, Splunk, Graylog

### Clustering and High Availability

#### Clustering Concepts
- **Active/Passive**: One active, one passive node
- **Active/Active**: Both nodes active
- **Load Balancing**: Distribute load across nodes
- **Failover**: Automatic switchover on failure

#### Windows Failover Clustering
- **Requirements**: Shared storage, cluster-aware applications
- **Components**: Nodes, networks, quorum
- **Features**: Cluster-aware applications, storage spaces

#### Linux Clustering
- **Pacemaker**: Cluster resource manager
- **Corosync**: Messaging layer
- **DRBD**: Distributed Replicated Block Device

### Load Balancing Configurations

#### Types of Load Balancing
- **Round Robin**: Sequential distribution
- **Weighted Round Robin**: Based on server capacity
- **Least Connections**: Send to server with fewest connections
- **IP Hash**: Based on client IP address

#### Load Balancing Solutions
- **Hardware**: F5 BIG-IP, Citrix Netscaler
- **Software**: HAProxy, NGINX, Apache mod_proxy_balancer
- **Cloud**: AWS ELB, Azure Load Balancer, Google Cloud Load Balancer

## Summary

This chapter covered comprehensive server administration for both Windows and Linux environments. Understanding these concepts is essential for managing and overseeing server infrastructure effectively. The next chapter will focus on database management systems.

## Key Takeaways

1. Active Directory provides centralized identity and policy management in Windows environments
2. DNS and DHCP are critical services for network functionality
3. PowerShell enables automation and management of Windows servers
4. Linux offers powerful command-line tools and flexible configuration options
5. Proper user and group management is essential for security
6. Package management systems simplify software installation and updates
7. Service management differs between systemd and init systems
8. SSH provides secure remote access and should be properly configured
9. Server hardening and patch management are ongoing security requirements
10. Virtualization technologies provide flexibility and resource optimization

## Practice Questions

1. What is the difference between security groups and distribution groups in Active Directory?
2. Explain the AGUDLP model in Active Directory group nesting.
3. What are the three categories of Linux file permissions?
4. Name three Linux package managers and the distributions that use them.
5. What is the 3-2-1 backup rule?

## Answers

1. Security groups are used to assign permissions and rights, while distribution groups are used only for email distribution.
2. AGUDLP stands for Account (users), Global (groups), Universal (groups), Domain Local (groups), Permissions (assigned to DL groups). This model follows best practices for group nesting.
3. The three categories of Linux file permissions are Owner (u), Group (g), and Others (o).
4. APT (Debian/Ubuntu), YUM/DNF (Red Hat/CentOS), and Pacman (Arch Linux).
5. The 3-2-1 backup rule means keeping 3 copies of data, on 2 different media types, with 1 offsite copy.