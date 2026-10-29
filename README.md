090 # 🖥My Cybersecurity Lab Environment Setup
# 📌Project Overview:

   This project focuses on setting up a
   Virtual Cybersecurity and penetration-
   testing laboratory using VirtualBox and                
   KaliLinux

  The purpose of this lab is to create a controlled environment where Cybersecurity tools, network scanning, reconnaissance,  vulnerability assessment, and other security-testing activities can be persafely and repeatedly.

The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorised
security testing 

# 📌Objectives 

The main objectives of this project are to:

  ●Install and configure VirtualBox.
  ●Install/import Kali Linux as a virtual 
   machine.         
  ●Create a private NAT Network for the.          
   Cybersecurity lab.
  ●Configure network connectivity for Kali              
   Linux.
  ●Assign a consistent IP address to the Kali 
   vm.
  ●Verify network connectivity and DNS
   resolution.
  ●Take a clean VM snapshot for recovery.
  ●Document the complete setup process.
  ●Prepare the environment for future 
   Cybersecurity projects.

 #  🛡Purpose of the Lab

   The lab provides an isolated and controlled  
   for Cybersecurity learning and authorised 
   security testing 
   
   It can be used for activities such as:
    
   ■ Network reconnaissance 
   ■ Port scanning 
   ■ Vulnerability assessment 
   ■ Packet analysis 
   ■ Web security testing 
   ■ Exploitation practice 
   ■ Security-tool experimentation 

#  🖥Lab Configuration 

   🧩 Component	       ⚙️ Configuration
       🖥️ Host OS	       Windows 11
       🧠 Host          RAM 	8 GB
      ⚡ Processor     	Intel Core i5
       🧰 Hypervisor	   VirtualBox 7.2
     🐉 Security OS     Kali Linux 2026.2
      🧠 Kali RAM       2048 MB                         
   🔌 Virtual Network	     NAT Network
   📡 Network Address	     10.0.0.0/24
      🔑 Kali IP Address 10.0.0.2/24
   🚪 Default Gateway	   10.0.0.1
     🌍 DNS Server	       8.8.8.8
     🔮 Future VM Range	10.0.0.3–10.0.0.99
   

 #  🖥Lab set up procedure
Step 1. Install 7-Zip
7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a .7z archive.

Tool: 7-Zip

Step 2. Install VirtualBox
VirtualBox was installed as the hypervisor.

Step 3. Create the NAT Network
A dedicated NAT Network was created in VirtualBox.

Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled


A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.


Step 4. Import Kali Linux
The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:


 Adapter 1
Attached to:   NAT Network
Network:       NatNetwork
Adapter Type:  Intel PRO/1000 MT Desktop
 
The VM was allocated

RAM: 2048 MB

 A shared folder was also configured for transferring required files between the host operating system and the Kali VM.

Step 5. Configure the Kali Linux Network
The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:

IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

Step 6. Create a Clean VM Snapshot
After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:

Clean Kali - Network Setup
The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

🔎 Lab Verification
✅ Test	🧾 Command	🎯 Expected Result
🌐 Check IP address	ip a	Correct Kali IP displayed
📡 Test gateway	ping 10.0.0.1	Successful replies
🌍 Test Internet connectivity	ping 8.8.8.8	Successful replies
🔎 Test DNS resolution	nslookup networkwalks.com	Domain resolves
🧰 Verify Nmap	nmap --version	Nmap version displayed
🔄 Verify snapshot	Restore snapshot and run ip a	Baseline configuration restored
Example Results
IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8

