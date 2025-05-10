# Azure Wireshark Analysis
In this project I create two Virtual Machines (Windows 10 and Ubuntu Linux) in Azure and observing network traffic types like ICMP, DHCP, and DNS using Wireshark. The project also includes configuring firewall rules and cleaning up the resources.


## Technology Utilized
- Microsoft Azure (deploying virtual machines)
- RDP (Remote Desktop Protocol)
- Wireshark (packet analyzer)
- Windows 10 (21H2)
- Ubuntu Server 20.04

## Actions and Observations

### 1. Azure Portal
Get logged into the Azure via the Azure Portal.
![firefox_Vl6XNuGjJR](https://github.com/user-attachments/assets/a95f9d14-832a-47f0-8f74-20868d9e1995)


### 2. Resource Group
Create a resource group named "RG-Network".
![Photos_l2lVu2mNPH](https://github.com/user-attachments/assets/6b0a5f09-bffd-456b-b1a7-315a5c93f6f5)


### 3. Virtual Machines
Create two VMs, a Windows 10 VM and an Ubuntu VM, within the same Virtual Network.
![Photos_1FRbaZqDHg](https://github.com/user-attachments/assets/176f7fd6-9523-486f-b85d-a1e598aa4407)


### 4. RDP
Using Remote Desktop Protocol (RDP) connect to the Windows 10 VM.
![mstsc_UzNAIW9UwH](https://github.com/user-attachments/assets/238b9f55-60ee-44b8-b332-ba2bd26d6872)


### 5. Wireshark 
On the Windows 10 VM download and install Wireshark.
![mstsc_lFY71YZHJI](https://github.com/user-attachments/assets/bfd7ae4c-1aa8-4512-877a-6f9a74a98c52)


### 6. Monitoring IMCP Traffic
Launch Wireshark and begin capturing packets, then apply a filter to display only ICMP traffic. Get the private IP address of the Ubuntu VM (Linux-VM) from Azure and ping it from within the Windows 10 VM.
![mstsc_0jswT3p1OY](https://github.com/user-attachments/assets/41858bed-7d2c-400d-9143-203d10a51f9c)

### 7. Blocking IMCP Traffic
7a. Initiate a continuous ping between the Windows VM and Ubuntu VM.
![mstsc_xjr0FVozfh](https://github.com/user-attachments/assets/a4e9ad2b-0f43-4204-b4ee-70238ea00149)

7b. From Azure, add create a inbound rule in the Network Security Group that blocks all IMCP traffic.
![firefox_QQ6gH1r4lm](https://github.com/user-attachments/assets/6401ac9c-2bc0-45cb-8a60-7eded92c6879)

7c. Observe how the continuous traffic between the VMs times out.
![mstsc_nsQwt84j3T](https://github.com/user-attachments/assets/f9d543b5-cdc8-47e3-b950-8a9571e8ae0b)

7d. Remove the rule blocking all ICMP traffic, and observe the resumption of traffic.
![mstsc_n6DFOELm20](https://github.com/user-attachments/assets/25a3d52c-b657-47ab-bbb4-6414870919cd)



