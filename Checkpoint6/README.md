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
4. [Part D - Creating Virtual Machines](#Part-D---Creating-Virtual-Machines)


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

2. In the context of Hybrid Cloud architecture. How on-prem computers can access resources inside Azure virtual network?

3. What are the most important benefits of Azure Virtual Networks? Elaborate in your own words. Do not copy/paste from Azure Documentation. Itemized list of just benefit without proper elaboration will not receive any marks

4. What is the difference between Network Security Group (NSG) and Route-Tables?

5. What is the difference between NSG and Firewalls?

6. What is a hob-and-spoc network topology and how be deployed in Azure Cloud?

7. In working with Azure VNETs, do you need o to define gateways for Azure to route traffic between subnets?
When do you need to configure and use Virtual Network Gateways?

```

## Part D - Creating Virtual Machines using Azure CLI