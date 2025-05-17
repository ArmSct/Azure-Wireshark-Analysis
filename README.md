
<img width="285" alt="307529604-e1b63531-1bbe-4d75-9f4f-320f98df52b4" src="https://github.com/user-attachments/assets/23110e1b-389f-4841-989d-5929a67692ed" />

# Azure Wireshark Analysis
In this project I create two Virtual Machines (Windows 10 and Ubuntu Linux) in Azure and observing network traffic types like ICMP, DHCP, and DNS using Wireshark. The project also includes configuring firewall rules and cleaning up the resources.


## Technology Utilized
- Microsoft Azure (deploying virtual machines)
- RDP (Remote Desktop Protocol)
- Wireshark (packet analyzer)
- Windows 10 (21H2)
- Ubuntu Server 20.04

## Actions and Observations

### Azure Portal
Get logged into the Azure via the Azure Portal.
![firefox_Vl6XNuGjJR](https://github.com/user-attachments/assets/a95f9d14-832a-47f0-8f74-20868d9e1995)


### Resource Group
Create a resource group named "RG-Network".
![Photos_l2lVu2mNPH](https://github.com/user-attachments/assets/6b0a5f09-bffd-456b-b1a7-315a5c93f6f5)


### Virtual Machines
Create two VMs, a Windows 10 VM and an Ubuntu VM, within the same Virtual Network.
![Photos_1FRbaZqDHg](https://github.com/user-attachments/assets/176f7fd6-9523-486f-b85d-a1e598aa4407)


### RDP
Using Remote Desktop Protocol (RDP) connect to the Windows 10 VM.
![mstsc_UzNAIW9UwH](https://github.com/user-attachments/assets/238b9f55-60ee-44b8-b332-ba2bd26d6872)


### Wireshark 
On the Windows 10 VM download and install Wireshark.
![mstsc_lFY71YZHJI](https://github.com/user-attachments/assets/bfd7ae4c-1aa8-4512-877a-6f9a74a98c52)


### Monitoring IMCP traffic
Launch Wireshark and begin capturing packets, then apply a filter to display only ICMP traffic. Get the private IP address of the Ubuntu VM (Linux-VM) from Azure and ping it from within the Windows 10 VM.
![mstsc_0jswT3p1OY](https://github.com/user-attachments/assets/41858bed-7d2c-400d-9143-203d10a51f9c)

### Firewall and blocking IMCP traffic
Initiate a continuous ping between the Windows VM and Ubuntu VM.
![mstsc_xjr0FVozfh](https://github.com/user-attachments/assets/a4e9ad2b-0f43-4204-b4ee-70238ea00149)

From Azure, add an inbound rule in the Network Security Group that blocks all IMCP traffic.
![firefox_QQ6gH1r4lm](https://github.com/user-attachments/assets/6401ac9c-2bc0-45cb-8a60-7eded92c6879)

Observe how the continuous traffic between the VMs times out.
![mstsc_nsQwt84j3T](https://github.com/user-attachments/assets/f9d543b5-cdc8-47e3-b950-8a9571e8ae0b)

Remove the rule blocking all ICMP traffic, and observe the resumption of traffic.
![mstsc_n6DFOELm20](https://github.com/user-attachments/assets/25a3d52c-b657-47ab-bbb4-6414870919cd)

### Monitoring SSH traffic
Initiate an SSH session from the Windows VM to the Ubuntu VM and monitor the SSH traffic. From Wireshark begin capturing packets, then apply a filter to display only SSH traffic. Type commands into the and monitor the requests.
![mstsc_49qYGB3KUg](https://github.com/user-attachments/assets/d6b6dec3-d27d-43b2-ae60-7ae73a3f4510)

### Monitoring DHCP traffic
From the command line issue the Windows 10 VM a new IP address from the command line, "ipconfig /renew". The obsereve the DHCP traffic in Wireshark.
![mstsc_UnpyiVp6tQ](https://github.com/user-attachments/assets/91e334de-4e51-4752-b41e-3f80d2963305)

### Monitoring DNS traffic
Apply a DNS traffic filter in Wireshark. From the command line on your Windows 10 VM, use the nslookup command to find the IP addresse disney.com. Monitor the resulting DNS traffic in Wireshark.
![mstsc_Y9PEfLwOxX](https://github.com/user-attachments/assets/40494ad0-e36d-482e-bb91-3e1b879a7d6f)

### 1Monitoring RDP traffic
Apply a RDP (Remote Desktop Protocol) traffic filter in Wireshark. Observe RDP protocol consistently providing a real-time feed between the two computers.
![mstsc_cdsPsCRuQx](https://github.com/user-attachments/assets/7257c52a-feff-4405-b4e2-a8cf9d058e4b)


