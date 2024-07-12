<br>

<p align="center">
<img width="500" src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5795419a-3012-4a57-b4b0-155c2dd93fc7" alt="Microsoft Active Directory Logo"/>
<br>
<br>
<br>



<h1>Configure an Application Security Group</h1>
<br>

<h2>Understanding the Scenario</h2>

<br>

You are a Security Engineer with an organization that needs to **Create an Azure Virtual Machine** that uses an **Application Security Group**.

1. First, you will **Create a Virtual Network**. 

2. Next, you will **Create an Application Security Group**.

3. Then you will **Create a Network Security Group**.

4. Finally, you will **Create an Azure Virtual Machine** to be used as a **Web Server**, and then you will **Test the Security Configuration**.

<br>

<br>

<p align="center">
<img src="https://github.com/user-attachments/assets/570b8877-b28c-4558-9e91-037632da4a3e" height="40%" width="40%" alt="9"/><br />
<br>

<br>

<br>

<h2>1️⃣ Create a Virtual Network</h2>
<br>

In the Azure portal, select Create a resource to display the Azure Marketplace.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5b9a2405-7215-4592-95f3-363c871949ef" height="100%" width="100%" alt="9"/><br />
<br>

In Search services and marketplace, search for and select Virtual Network, and then select Create.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5b9a2405-7215-4592-95f3-363c871949ef" height="100%" width="100%" alt="9"/><br />
<br>

On the Create virtual network blade, on the Basics page, in Resource group, select corp-datalod42364539, in Virtual network name, enter webVNET, and then on the command bar, select IP Addresses.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5b9a2405-7215-4592-95f3-363c871949ef" height="100%" width="100%" alt="9"/><br />
<br>

On the IP Addresses page, in IPv4 address space, select the existing address space 10.0.0.0/16, enter 10.10.0.0/16 to overwrite the value.
<br>

On the IP Addresses page, in Subnets, select the Trash icon to delete the existing default subnet.
<br>

Select Add a subnet to open the Add a subnet blade.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5b9a2405-7215-4592-95f3-363c871949ef" height="100%" width="100%" alt="9"/><br />
<br>

On the Add a subnet blade, in Name, enter web, in Starting address, enter 10.10.0.0/25, and then select Add.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5b9a2405-7215-4592-95f3-363c871949ef" height="100%" width="100%" alt="9"/><br />
<br>

On the Create virtual network blade, select Review + create, and then select Create to create the virtual network.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5b9a2405-7215-4592-95f3-363c871949ef" height="100%" width="100%" alt="9"/><br />
<br>

<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5b9a2405-7215-4592-95f3-363c871949ef" height="100%" width="100%" alt="9"/><br />
<br>

✅ You will use this **Virtual Network** for the **Web Tier**.

<br>

<br>

  <details close> 
  
**<summary> 💡 Note</summary>**

You can use an Azure virtual network to create a network address space in the cloud that you will use to host resources, for example:

- virtual machines
- load balancers
- and application gateways

➔ for secure access from on-premises networks and other virtual networks.

  </details>


<br>
<br>

<h2>2️⃣ Create an Application Security Group and an associated Network Security Group</h2>
<br>

### Step ❶ ➔ Create an Application Security Group

<br>

On the Azure portal menu, select Create a resource to display the Azure Marketplace.
<br>
  
In Search services and marketplace, search for and select Application security group, and then select Create.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>
  
On the Create an application security group blade, in Resource group, select corp-datalod42364539, and then in Name, enter webASG.
<br>

Select Review + create, and then select Create to create the application security group.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>


<br>
<h2></h2>
<br>

### Step ❷ ➔ Create a Network Security Group

<br>

On the Azure portal menu, select Create a resource to display the Azure Marketplace.
<br>

In Search services and marketplace, search for and select Network security group, and then select Create.createnetworksecuritygroups.jpg
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the Create an network security group blade, in Resource group, select corp-datalod42364539, and then in Name, enter webNSG.
<br>

Select Review + create, and then select Create to create the network security group.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>


<br>
<h2></h2>
<br>

### Step ❸ ➔ Add an Inbound Security Rule to *webNSG* to allow HTTP and HTTPS Traffic 

<br>

On the Azure portal menu, select All services, in Categories, select Networking, and then select Network security groups.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the Network security groups page, select webNSG.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the webNSG resource menu, in Settings, select Inbound security rules, and then on the command bar, select Add.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the Add inbound security rule blade, in Destination, select Application security group, and then in Destination application security groups, select webASG.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

In Destination port ranges, enter 80,443, in Name, enter AllowAllweb, and then select Add to add the inbound security rule.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

⚠️ Wait for the new inbound security rule to be created ➔ This will take approximately 1–2 minutes.
<br>


<br>
<h2></h2>
<br>

### Step ❹ ➔ Add a second Inbound Security Rule to *webNSG* to allow RDP Traffic 

<br>

On the Add inbound security rule blade, in Destination, select **Application security group**, and then in Destination application security groups, select **webASG**.
<br>

In Destination port ranges, enter ***🆃 3389***, in Name, enter ***🆃 AllowAllRDP***, and then select **Add** to add the second inbound security rule.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

⚠️ Wait for the new inbound security rule to be created.
<br>


<br>
<h2></h2>
<br>

### Step ❺ ➔ Associate the NSG to the Web Subnet

On the webNSG resource menu, in Settings, select Subnets, and then on the command bar, select Associate.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the Associate subnet blade, in Virtual network, select webVNET, in Subnet, select web, and then select OK to associate the network security group to the selected subnet.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

⚠️ Wait for the webNSG to be associated with the web subnet ➔ This will take approximately 1–2 minutes.

<br>



<br>
<br>

<h2>3️⃣ Create an Azure Virtual Machine</h2>
<br>

### Step ❶ ➔ Create an Azure Virtual Machine

<br>

On the Azure portal menu, select Create a resource.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

In Search services and marketplace, search for and select Virtual machine, and then select Create.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the Create a virtual machine blade, on the Basics page, in Resource group, select corp-datalod42364539.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

In Virtual machine name, enter VM1.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

In Image, select Windows Server 2019 Datacenter - x64 Gen2.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

In Size, select See all sizes.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the Select a VM size page, in Search by VM size, enter B2, in VM Size, select B2s, and then select Select.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the Basics page, in Username, enter AzureAdmin, in Password and Confirm password, enter Az!42364539!, and then in Public inbound ports, select None.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the Networking page, in Virtual network, ensure that webVNET is selected, in Subnet, ensure that web (10.10.0.0/25) is selected, and then in NIC network security group, ensure that None is selected.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the Monitoring page, in Boot diagnostics, select Disable.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

Select Review + create, review the virtual machine specifications, and then select Create to deploy the virtual machine.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

⚠️ The deployment will take approximately 3–5 minutes.
<br>

<br>
<h2></h2>
<br>

### Step ❷ ➔ Associate the ASG to the Virtual Machine NIC

<br>

On the Azure portal menu, select All resources, and then select VM1.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the VM1 resource menu, in Networking, select Application security groups.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the VM1 Application security groups page, select Add application security groups.Applicationsecuritygroups.jpg
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

On the Add application security groups blade, select webASG, and then select Add.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/83d5df37-6cdb-4da2-8fa9-99a4fdb61607" height="100%" width="100%" alt="9"/><br />
<br>

⚠️ It will take approximately 1–2 minutes to save the network settings in the background.
<br>

<br>
<h2></h2>
<br>

### Step ❸ ➔ Connect to the VM through RDP

<br>

On the VM1 Overview page, in Public IP address, write down the **Public IP address**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

On the Azure portal home page, select Virtual machines, and then select VM1.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

On the VM1 Overview page, on the command bar, select Connect, in Native RDP, select Download RDP file.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

On the Connect page, in IP address, ensure that Public IP address is selected, and then select Download RDP File.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

Open the RDP file, and then in the Remote Desktop Connection window, select Connect.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

When prompted for credentials, select More choices, and then select Use a different account.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

In User name, enter AzureAdmin, in Password, enter Az!42364539!, and then select OK.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

In the Remote Desktop Connection warning message box, select Yes, and then wait for the RDP session to initialize.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

In the RDP session, if prompted to allow your PC to be discoverable by other PCs and devices on this network, select No, and then minimize Server Manager.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

<br>
<h2></h2>
<br>


### Step ❹ ➔ Install Internet Information Services (IIS) using Windows PowerShell®

<br>

In the Remote Desktop Connection window, on the Start menu, select Windows PowerShell.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

In Windows PowerShell, run the following command to install IIS on VM1:

```commandline
Install-WindowsFeature -name web-Server -IncludeManagementTools
```
<br>
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

Verify that the IIS installation was successful.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

Close the Remote Desktop Connection window, and then select OK to disconnect.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>

Open a new browser window, and then go to the public IP address of VM1 at http://<PublicIP>.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>
  
✅ You should see the default Internet Information Services (IIS) webpage ➔ This will verify that **Web Traffic has been routed correctly by using an ASG and a NSG**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/516d697e-5e68-4355-bc73-59c724b948ca" height="100%" width="100%" alt="9"/><br />
<br>


<br>

<h2>Summary</h2>

<br>

✅ Congratulations, we have completed the **Configure an Application Security Group Lab**.

<br>

We have accomplished the following:

- **Created a virtual network for a web server tier**.

- **Created an Application Security Group and associated Network Security Group**.

- **Created an Azure Virtual Machine and Tested Application Security**.

<br>
<br>
<br>
<br>
