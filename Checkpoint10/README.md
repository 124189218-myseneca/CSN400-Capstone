# Checkpoint10 Submission

- **COURSE INFORMATION: CSN400NDD**
- **STUDENT’S NAME: Ashwin Dhingra**
- **STUDENT'S NUMBER: 124189218**
- **GITHUB USER ID: 124189218-myseneca**
- **TEACHER’S NAME: Atoosa Nasiri**


### Table of Contents

1. [Part A – Route Table Updates](#Part-A-–-Route-Table-Updates)
2. [Part B – Port Forwarding Basic Connectivity](#Part-B-–-Port-Forwarding-Basic-Connectivity)
3. [Part C – Logging & Isolating Masqueraded Packets](#Part-C-–-Logging-&-Isolating-Masqueraded-Packets)
4. [Part D - Azure Cost Analysis Charts](#Part-D---Azure-Cost-Analysis-Charts)



## Part A - Route Table Updates

### Lists all your Route Tables, Routes, and Associated Subnets

```

az network route-table list --output table
DisableBgpRoutePropagation    Location       Name       ProvisioningState    ResourceGroup      ResourceGuid
----------------------------  -------------  ---------  -------------------  -----------------  ------------------------------------
False                         canadacentral  RT-106     Succeeded            Student-RG-954430  a2379932-c813-4255-98bd-f09c07f63788
False                         canadacentral  RT-EX-106  Succeeded            Student-RG-954430  98360a5d-8e11-4a13-becd-7d0214b35fd2


----


az network route-table route list --resource-group Student-RG-954430 --route-table-name RT-106 --output table
AddressPrefix      HasBgpOverride    Name              NextHopIpAddress    NextHopType       ProvisioningState    ResourceGroup
-----------------  ----------------  ----------------  ------------------  ----------------  -------------------  -----------------
172.17.106.32/27   False             Route-to-Server   192.168.106.36      VirtualAppliance  Succeeded            Student-RG-954430
10.31.124.0/24     False             Route-to-Desktop  192.168.106.36      VirtualAppliance  Succeeded            Student-RG-954430
192.168.130.32/27  False             External-router   192.168.106.36      VirtualAppliance  Succeeded            Student-RG-954430


-----


az network route-table route list --resource-group Student-RG-954430 --route-table-name RT-EX-106 --output table
AddressPrefix      HasBgpOverride    Name          NextHopIpAddress    NextHopType       ProvisioningState    ResourceGroup
-----------------  ----------------  ------------  ------------------  ----------------  -------------------  -----------------
192.168.130.32/27  False             Route-to-Hub  192.168.99.36       VirtualAppliance  Succeeded            Student-RG-954430

```


## Part B - Port Forwarding Basic Connectivity

### nat_basic-connectivity.sh

```
# to flush NAT tables
iptables -t nat -F

# to allow other students to access APACHE server 
iptables -t nat -A PREROUTING -p tcp --dport 18106 -j DNAT --to-destination 172.17.106.37:80

# to allow other students to access MySQL server 
iptables -t nat -A PREROUTING -p tcp --dport 16106 -j DNAT --to-destination 172.17.106.37:3306

# to allow other students to access Linux server - SSH 
iptables -t nat -A PREROUTING -p tcp --dport 12106 -j DNAT --to-destination 172.17.106.37:22

# to allow other students to access IIS server 
iptables -t nat -A PREROUTING -p tcp --dport 19106 -j DNAT --to-destination 172.17.106.36:80

# to allow other students to access Windows server - RDP 
iptables -t nat -A PREROUTING -p tcp --dport 13106 -j DNAT --to-destination 172.17.106.36:3389


```

### firewalls-cp10.sh

```
# allow custom port for partner Apache Server
iptables -A FORWARD -p tcp -s 10.31.124.0/24 -d 192.168.130.36 --dport 18130 -j ACCEPT
iptables -A FORWARD -p tcp -s 192.168.130.36 -d 10.31.124.0/24 --sport 18130 -j ACCEPT

# allow custom port for partner MySQL Server
iptables -A FORWARD -p tcp -s 10.31.124.0/24 -d 192.168.130.36 --dport 16130 -j ACCEPT
iptables -A FORWARD -p tcp -s 192.168.130.36 -d 10.31.124.0/24 --sport 16130 -j ACCEPT

# allow custom port for partner IIS Server
iptables -A FORWARD -p tcp -s 10.31.124.0/24 -d 192.168.130.36 --dport 19130 -j ACCEPT
iptables -A FORWARD -p tcp -s 192.168.130.36 -d 10.31.124.0/24 --sport 19130 -j ACCEPT

# allow custom port for partner Windows Server RDP
iptables -A FORWARD -p tcp -s 10.31.124.0/24 -d 192.168.130.36 --dport 13130 -j ACCEPT
iptables -A FORWARD -p tcp -s 192.168.130.36 -d 10.31.124.0/24 --sport 13130 -j ACCEPT

# allow custom port88130 for partner Linux Server SSH
iptables -A FORWARD -p tcp -s 10.31.124.0/24 -d 192.168.130.36 --dport 12130 -j ACCEPT
iptables -A FORWARD -p tcp -s 192.168.130.36 -d 10.31.124.0/24 --sport 12130 -j ACCEPT

# allow partner traffic after NAT mapping
#HTTP
iptables -A FORWARD -p tcp -s 192.168.130.36 --dport 80 -j ACCEPT
iptables -A FORWARD -p tcp -d 192.168.130.36 --sport 80 -j ACCEPT
# SSH
iptables -A FORWARD -p tcp -s 192.168.130.36 --dport 22 -j ACCEPT
iptables -A FORWARD -p tcp -d 192.168.130.36 --sport 22 -j ACCEPT
# RDP
iptables -A FORWARD -p tcp -s 192.168.130.36 --dport 3389 -j ACCEPT
iptables -A FORWARD -p tcp -d 192.168.130.36 --sport 3389 -j ACCEPT
#MySQL
iptables -A FORWARD -p tcp -s 192.168.130.36 --dport 3306 -j ACCEPT
iptables -A FORWARD -p tcp -d 192.168.130.36 --sport 3306 -j ACCEPT

# to DROP all traffic which is not explicitly allowed by firewall rules
iptables -A FORWARD -j DROP

# list the updated iptables
iptables -nvL --line


```


## Part C - Logging & Isolating Masqueraded Packets



## Part D - Azure Cost Analysis Charts


| No. | Scope | Chart Type | VIEW Type |  Date Range | Group By | Granularity| Example |
|-|-|-|-|-|-|-|-|
|1|Student-RG-954430| Column (Stacked) | DailyCosts | Last 7 Days | Resource | Daily | <img src="images/PARTD/Screenshot-1.png" alt="dashbooard" title="image" alt="Daily Cost Barchart" style="float: left; margin-right: 10px;" /> |
|2|Student-RG-954430| Column (Stacked) | DailyCosts | Last 7 Days | Service | Daily | <img src="images/PARTD/Screenshot-2.png" alt="Daily Cost Service-Barchart.jpg" style="float: left; margin-right: 10px;" /> |
|3|Student-RG-954430| Area| AccumulatedCosts | Last 7 Days | Resource | Accumulated | <img src="images/PARTD/Screenshot-3.png" alt="Accumulated Resource Barchart" style="float: left; margin-right: 10px;" /> |
|4|Student-RG-954430| Pie Chart | NA | Last Month | Service Name | NA | <img src="images/PARTD/Screenshot-4.png" alt="Service Name Piechart" style="float: left; margin-right: 10px;" /> |
|5|Student-RG-954430| Pie Chart | NA | Last Month | Service Family | NA | <img src="images/PARTD/Screenshot-5.png" alt="Service Family Piechart" style="float: left; margin-right: 10px;" /> |
|6|Student-RG-954430| Pie Chart | NA | Last Month | Product | NA | <img src="images/PARTD/Screenshot-6.png" alt="Product Piechart" style="float: left; margin-right: 10px;" /> |
