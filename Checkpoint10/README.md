# Checkpoint8 Submission

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



## ✨ Part A - Route Table Updates

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


## ✨ Part B - Port Forwarding Basic Connectivity



## ✨ Part C - Logging & Isolating Masqueraded Packets



## ✨ Part D - Azure Cost Analysis Charts