# Azure Resources & Generated fields naming convention

- Project Name: `<project-name>`

### Global

- **Sendgrid**  
  `<project-name>`-sendgrid  
- **Key Vault (Standard)**  
  `<project-name>`-kv-std  
- **Key Vault (Premium)**  
  `<project-name>`-kv-prem  

## Resource Group: `<project-name>`-dev

### Virtual Machine Setup: 1
- **Virtual Machine:** `<project-name>`-ebml3
- **Network Interface:** `<project-name>`-ebml3-nic
- **Public IP:** `<project-name>`-ebml3-ip
- **Network Security Group:** `<project-name>`-ebml3-nsg
- **OS Disk:** `<project-name>`-ebml3-osdisk
- **Data Disk (optional):** `<project-name>`-ebml3-datadisk-01
- **Key pair name:** `<project-name>`-ebml3_key`

### Virtual Machine Setup: 2
- **Virtual Machine:** `<project-name>`-w9q2a
- **Network Interface:** `<project-name>`-w9q2a-nic
- **Public IP:** `<project-name>`-w9q2a-ip
- **Network Security Group:** `<project-name>`-w9q2a-nsg
- **OS Disk:** `<project-name>`-w9q2a-osdisk
- **Data Disk (optional):** `<project-name>`-w9q2a-datadisk-01
- **Key pair name:** `<project-name>`-w9q2a_key`

### Shared resources
- **Virtual Network:** `<project-name>`-dev-vnet
- **Subnet:** `<project-name>`-dev-subnet
- **Diagnostics Storage (optional):** `<project-name>`-dev-diag
- **Storage Account:** `<project-name>`devst

### Application Gateway
- **Application Gateway Name:** `<project-name>`-dev-appgw
- **Application Gateway Subnet:** `<project-name>`-dev-appgw-subnet
- **Application Gateway Public IP:** `<project-name>`-dev-appgw-ip

#### Application Gateway Backend Pool
- `<project-name>`-dev-appgw-backendpool

#### Application Gateway Backend Settings
- Backend settings name: `sub.domain.com-besetting`
- HTTPS validation settings: Complete validation & Public CA
- Override with new host name: Yes
- Override with specific domain name: sub.domain.com

#### Application Gateway Listeners
- Listener name: `sub.domain.com-listener`
- Listener type: Multi site & Single & `sub.domain.com-listener`

#### Application Gateway Rules
- Rule name: `sub.domain.com-rule`

### Front Door

- **Front Door Profile (Standard):** `<project-name>`-dev-fd-std  
- **Front Door Profile (Premium):** `<project-name>`-dev-fd-prem  
- **Endpoint Name:** `<project-name>`-dev

#### Routes
- **Route Name:** `api-domain-com-route`  
  - **Origin Group:** `api-domain-com-origgrp`  
  - **Health probes:** /__health & https & GET & 100  
  - **Origin Host Name (1):** `<project-name>`-ebml3 (VM name)  
  - **Origin Host Name (2):** `<project-name>`-w9q2a (VM name)  

- **Route Name:** `portal-domain-com-route`  
  - **Origin Group:** `portal-domain-com-origgrp`  
  - **Health probes:** /__health & https & GET & 100  
  - **Origin Host Name (1):** `<project-name>`-ebml3 (VM name)  
  - **Origin Host Name (2):** `<project-name>`-w9q2a (VM name)  

---

## Resource Group: `<project-name>`-test

### Virtual Machine Setup: 1
- **Virtual Machine:** `<project-name>`-t3y6n
- **Network Interface:** `<project-name>`-t3y6n-nic
- **Public IP:** `<project-name>`-t3y6n-ip
- **Network Security Group:** `<project-name>`-t3y6n-nsg
- **OS Disk:** `<project-name>`-t3y6n-osdisk
- **Data Disk (optional):** `<project-name>`-t3y6n-datadisk-01
- **Key pair name:** `<project-name>`-t3y6n_key`

### Virtual Machine Setup: 2
- **Virtual Machine:** `<project-name>`-c8p2x
- **Network Interface:** `<project-name>`-c8p2x-nic
- **Public IP:** `<project-name>`-c8p2x-ip
- **Network Security Group:** `<project-name>`-c8p2x-nsg
- **OS Disk:** `<project-name>`-c8p2x-osdisk
- **Data Disk (optional):** `<project-name>`-c8p2x-datadisk-01
- **Key pair name:** `<project-name>`-c8p2x_key`

### Shared resources
- **Virtual Network:** `<project-name>`-test-vnet
- **Subnet:** `<project-name>`-test-subnet
- **Diagnostics Storage (optional):** `<project-name>`-test-diag
- **Storage Account:** `<project-name>`testst

### Application Gateway
- **Application Gateway Name:** `<project-name>`-test-appgw
- **Application Gateway Subnet:** `<project-name>`-test-appgw-subnet
- **Application Gateway Public IP:** `<project-name>`-test-appgw-ip

#### Application Gateway Backend Pool
- `<project-name>`-test-appgw-backendpool

#### Application Gateway Backend Settings
- Backend settings name: `sub.domain.com-besetting`
- HTTPS validation settings: Complete validation & Public CA
- Override with new host name: Yes
- Override with specific domain name: sub.domain.com

#### Application Gateway Listeners
- Listener name: `sub.domain.com-listener`
- Listener type: Multi site & Single & `sub.domain.com-listener`

#### Application Gateway Rules
- Rule name: `sub.domain.com-rule`

### Front Door

- **Front Door Profile (Standard):** `<project-name>`-test-fd-std  
- **Front Door Profile (Premium):** `<project-name>`-test-fd-prem  
- **Endpoint Name:** `<project-name>`-test

#### Routes
- **Route Name:** `api-domain-com-route`  
  - **Origin Group:** `api-domain-com-origgrp`  
  - **Health probes:** /__health & https & GET & 100  
  - **Origin Host Name (1):** `<project-name>`-t3y6n (VM name)  
  - **Origin Host Name (2):** `<project-name>`-c8p2x (VM name)  

- **Route Name:** `portal-domain-com-route`  
  - **Origin Group:** `portal-domain-com-origgrp`  
  - **Health probes:** /__health & https & GET & 100  
  - **Origin Host Name (1):** `<project-name>`-t3y6n (VM name)  
  - **Origin Host Name (2):** `<project-name>`-c8p2x (VM name)  

---

## Resource Group: `<project-name>`-staging

### Virtual Machine Setup: 1
- **Virtual Machine:** `<project-name>`-x8z7p
- **Network Interface:** `<project-name>`-x8z7p-nic
- **Public IP:** `<project-name>`-x8z7p-ip
- **Network Security Group:** `<project-name>`-x8z7p-nsg
- **OS Disk:** `<project-name>`-x8z7p-osdisk
- **Data Disk (optional):** `<project-name>`-x8z7p-datadisk-01
- **Key pair name:** `<project-name>`-x8z7p_key`

### Virtual Machine Setup: 2
- **Virtual Machine:** `<project-name>`-4us2m
- **Network Interface:** `<project-name>`-4us2m-nic
- **Public IP:** `<project-name>`-4us2m-ip
- **Network Security Group:** `<project-name>`-4us2m-nsg
- **OS Disk:** `<project-name>`-4us2m-osdisk
- **Data Disk (optional):** `<project-name>`-4us2m-datadisk-01
- **Key pair name:** `<project-name>`-4us2m_key`

### Shared resources
- **Virtual Network:** `<project-name>`-staging-vnet
- **Subnet:** `<project-name>`-staging-subnet
- **Diagnostics Storage (optional):** `<project-name>`-staging-diag
- **Storage Account:** `<project-name>`stagingst

### Application Gateway
- **Application Gateway Name:** `<project-name>`-staging-appgw
- **Application Gateway Subnet:** `<project-name>`-staging-appgw-subnet
- **Application Gateway Public IP:** `<project-name>`-staging-appgw-ip

#### Application Gateway Backend Pool
- `<project-name>`-staging-appgw-backendpool

#### Application Gateway Backend Settings
- Backend settings name: `sub.domain.com-besetting`
- HTTPS validation settings: Complete validation & Public CA
- Override with new host name: Yes
- Override with specific domain name: sub.domain.com

#### Application Gateway Listeners
- Listener name: `sub.domain.com-listener`
- Listener type: Multi site & Single & `sub.domain.com-listener`

#### Application Gateway Rules
- Rule name: `sub.domain.com-rule`

### Front Door

- **Front Door Profile (Standard):** `<project-name>`-staging-fd-std  
- **Front Door Profile (Premium):** `<project-name>`-staging-fd-prem  
- **Endpoint Name:** `<project-name>`-staging

#### Routes
- **Route Name:** `api-domain-com-route`  
  - **Origin Group:** `api-domain-com-origgrp`  
  - **Health probes:** /__health & https & GET & 100  
  - **Origin Host Name (1):** `<project-name>`-x8z7p (VM name)  
  - **Origin Host Name (2):** `<project-name>`-4us2m (VM name)  

- **Route Name:** `portal-domain-com-route`  
  - **Origin Group:** `portal-domain-com-origgrp`  
  - **Health probes:** /__health & https & GET & 100  
  - **Origin Host Name (1):** `<project-name>`-x8z7p (VM name)  
  - **Origin Host Name (2):** `<project-name>`-4us2m (VM name)  

---

## Resource Group: `<project-name>`-prod

### Virtual Machine Setup: 1
- **Virtual Machine:** `<project-name>`-h5t9k
- **Network Interface:** `<project-name>`-h5t9k-nic
- **Public IP:** `<project-name>`-h5t9k-ip
- **Network Security Group:** `<project-name>`-h5t9k-nsg
- **OS Disk:** `<project-name>`-h5t9k-osdisk
- **Data Disk (optional):** `<project-name>`-h5t9k-datadisk-01
- **Key pair name:** `<project-name>`-h5t9k_key`

### Virtual Machine Setup: 2
- **Virtual Machine:** `<project-name>`-j2q3v
- **Network Interface:** `<project-name>`-j2q3v-nic
- **Public IP:** `<project-name>`-j2q3v-ip
- **Network Security Group:** `<project-name>`-j2q3v-nsg
- **OS Disk:** `<project-name>`-j2q3v-osdisk
- **Data Disk (optional):** `<project-name>`-j2q3v-datadisk-01
- **Key pair name:** `<project-name>`-j2q3v_key`

### Shared resources
- **Virtual Network:** `<project-name>`-prod-vnet
- **Subnet:** `<project-name>`-prod-subnet
- **Diagnostics Storage (optional):** `<project-name>`-prod-diag
- **Storage Account:** `<project-name>`prodst

### Application Gateway
- **Application Gateway Name:** `<project-name>`-prod-appgw
- **Application Gateway Subnet:** `<project-name>`-prod-appgw-subnet
- **Application Gateway Public IP:** `<project-name>`-prod-appgw-ip

#### Application Gateway Backend Pool
- `<project-name>`-prod-appgw-backendpool

#### Application Gateway Backend Settings
- Backend settings name: `sub.domain.com-besetting`
- HTTPS validation settings: Complete validation & Public CA
- Override with new host name: Yes
- Override with specific domain name: sub.domain.com

#### Application Gateway Listeners
- Listener name: `sub.domain.com-listener`
- Listener type: Multi site & Single & `sub.domain.com-listener`

#### Application Gateway Rules
- Rule name: `sub.domain.com-rule`

### Front Door

- **Front Door Profile (Standard):** `<project-name>`-prod-fd-std  
- **Front Door Profile (Premium):** `<project-name>`-prod-fd-prem  
- **Endpoint Name:** `<project-name>`-prod

#### Routes
- **Route Name:** `api-domain-com-route`  
  - **Origin Group:** `api-domain-com-origgrp`  
  - **Health probes:** /__health & https & GET & 100  
  - **Origin Host Name (1):** `<project-name>`-h5t9k (VM name)  
  - **Origin Host Name (2):** `<project-name>`-j2q3v (VM name)  

- **Route Name:** `portal-domain-com-route`  
  - **Origin Group:** `portal-domain-com-origgrp`  
  - **Health probes:** /__health & https & GET & 100  
  - **Origin Host Name (1):** `<project-name>`-h5t9k (VM name)  
  - **Origin Host Name (2):** `<project-name>`-j2q3v (VM name)  
