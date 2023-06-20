# Checkpoint6 Submission

- **COURSE INFORMATION: CSN400NDD**
- **STUDENT’S NAME: Ashwin Dhingra**
- **STUDENT'S NUMBER: 124189218**
- **GITHUB USER ID: 124189218-myseneca**
- **TEACHER’S NAME: Atoosa Nasiri**

### Table of Contents

1. [Part A - Creating Network Resources using Azure CLI](&Part-A---Creating-Network-Resources-using-Azure-CLI)
2. [Part B - Working in Azure CLI Bash](#Part-B---Working-in-Azure-CLI-Bash)
3. [Part C - Network Review Questions](#Part-C---Network-Review-Questions)
4. [Part D - Creating Virtual Machines using Azure CLI](#Part-D---Creating-Virtual-Machines-using-Azure-CLI)


## Part A - Creating Network Resources using Azure CLI

### Output 

### Questions/ Answers
```
1. In network_config_test.sh what does if [[ ! $(az group list -o tsv --query "[?name=='$RG_NAME']") ]] do? Explain your answer.

2. Why is it crucial to check if a resource exist before creating it? What bash syntax do you use to test this? How do you check if a vnet exits in vnet_create.sh?

3. What is the Azure CLI command to create vnet? Give the specific command as per your environment and unique ID configuration. What are the required and what are the optional parameters that you need to pass to it?

4. What is the Azure CLI command to create subnet? Give the specific command as per your environment and unique ID configuration. What are the required and what are the optional parameters that you need to pass to it?


```


## Part B - Working in Azure CLI Bash

### Question/Answers
```
1. List all VNETs using az network vnet list command and send the output in json format to vnet_list.jsonfile

2. Get the details of your default student vnet using az show command and send the output in json format to student_vnet.json file

3. List all peerings using az network vnet peering list command and send the output in table format to peerings.tblfile

4. Get the details of your Router-XX subnet SN1 using az show command in json format and query it for details of subnet and rout associations. Only submit the specific property you are asked for. You will need to embed this in your README.md as per instructions.

5. List all routes in RT-xx using az network route-table route list command and send the output in table format to route_list.tblfile

6.Get the details of route between your Router-xx SN1 and Server-xx SN using az network route-table route show and send the output in json format to route_details.json

7. (Optional) What CLI command will show you which subnet is associated to which route in route table? (Hint: maybe start with 'az network vnet subnet show`)

# Answer7 -- az network route-table route list --resource-group <resource-group-name> --route-table-name <route-table-name> --output table

```

## Part C - Network Review Questions

```

1. What is Azure Virtual Network (VNET)? Elaborate in your own words, you may use diagrams if drawn by yourself.
Answer 1 - Azure Vnet is a networking service provided by Azure which helps in creating and administration of virtual networks within cloud environment.
we can specify subnets, IP address ranges, and network security policies because it serves as a logical representation of your own network in the cloud.


2. In the context of Hybrid Cloud architecture. How on-prem computers can access resources inside Azure virtual network?
Answer 2- In hybrid architecture resources inside azure network can be accessed via site to site VPn or azure express route.
Site-to-site vpn: this can be set up by configuring a virtual network gateway in azure and connecting it with a VPN device on-premises.
Express route: It is a secure, high-bandwidth link that connects directly to the Azure cloud, giving users immediate access to its services and resources.


3. What are the most important benefits of Azure Virtual Networks? Elaborate in your own words. Do not copy/paste from Azure Documentation. Itemized list of just benefit without proper elaboration will not receive any marks
Answer 3 - There are several key benefits of azure virtual networks which include network isolation, scalability, and security. The major benefit of virtual network is network isolation, which gives the user full control on defining the boundaries of network traffic flow.


4. What is the difference between Network Security Group (NSG) and Route-Tables?
Answer 4 - A network security group works as a firewall and is used for regulating traffic for a particular resource. we can filter both inbound and outbound traffic and even restrict it from a particular address, whereas route tables are used to manage network traffic routing within a Virtual Network.


5. What is the difference between NSG and Firewalls?
answer 5 - network security group is basic firewall which mostly works on network level with the help of IPs and ports. we can establish rules for both inward and outward traffic. 
Firewall, on the other hand,  works on a wider range which can be even upto the entire network.


6. What is a hob-and-spoc network topology and how be deployed in Azure Cloud?
Answer6 - A hub and spoke network is where a 'hub' acts as a center of the network controlling the fucntions and security, and the other network connected to it are referred to as 'spokes'. VNET peering is an example of hub and spoke network.

7. In working with Azure VNETs, do you need o to define gateways for Azure to route traffic between subnets?
When do you need to configure and use Virtual Network Gateways?

answer 7 - A VNET's subnets can interact with one another by default without requiring for extra configuration or gateways so it is not necessary to define gateways for azure to route traffic between subnets.

8. When do you need to configure and use Virtual Network Gateways?
Answer 8 - Network gateways can be used to establish connection between networks or between an on-prem network and azure vnet.

```

## Part D - Creating Virtual Machines using Azure CLI

```
1. List all VMs and send the output in table format to vm_list.tbl file. What command did you use?

2. Get the details of your WC-99 using az show command and send the output in json format to WC-99-details.json file. What command did you use?

3. List all NSG using az list command and send the output in table format to nsg_list.tblfile. What command did you use?

4. List all VMs after running delete_all_vm.sh with the output in table format. What command did you use? How can you ensure all your VMs are deleted?

5.Provide screenshot of auto shutdown configuration for LS_XX. Is there any command to show this? What is the time-zone? What should be the correct time settings considering the time zone differences?

```