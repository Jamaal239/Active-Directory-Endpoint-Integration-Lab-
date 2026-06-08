# Enterprise Infrastructure Sandbox: Active Directory & Endpoint Deployment

## 📋 Project Overview
This project demonstrates the end-to-end provisioning, engineering, and configuration of an isolated enterprise lab environment using Oracle VirtualBox. The infrastructure features a Windows Server Domain Controller managing a Windows 11 Enterprise client workstation over a secure, non-routable internal network. 

### 🎯 Key Skills Demonstrated
* **Active Directory & Identity Management:** Built a localized Active Directory forest (`mydomain.local`) with complete user session control.
* **Core Networking:** Configured standard static IPv4 schemas, localized DNS routing, and resolved multi-adapter network interface loops.
* **Systems Administration:** Managed virtualization layers, endpoint naming standardizations, and automated domain authentication workflows.

---

## 📸 Technical Deployment Log

### Phase 1: Domain Controller Provisioning & Core Networking

#### Step 1: Base Virtual Network Configuration
* Configured the virtualization network parameters for the primary server node, binding the virtual switch to an isolated local network segment.

#### Step 2: Active Directory Domain Services (AD DS) Initialization
* Installed and configured the AD DS and DNS roles via Server Manager to prepare the environment for forest promotion.

---

### Phase 2: Client Workstation Staging

#### Step 3: Virtual Hardware & Storage Allocation
* Provisioned virtual storage limits and hardware resource pools within VirtualBox to sustain the client node profile.

#### Step 4: Network Interface Configuration
* Assigned the workstation's virtual network interface card (NIC) to the isolated internal switch, pulling it away from default public pools.

#### Step 5: Disk Partitioning & OS Installation
* Partitioned unallocated disk storage blocks during the Windows 11 installation setup to create local root directories.

#### Step 6: Local Administrator Account Creation
* Provisioned the initial local administrator account profile (`ClientAdmin`) during the Windows Out-of-Box Experience (OOBE) setup phase.

#### Step 7: VirtualBox Guest Additions Deployment
* Compiled and updated the hypervisor guest utility drivers to enable dynamic resolution scaling and shared clipboard utilities.

---

### Phase 3: Network Optimization & Diagnostics

#### Step 8: Hostname Standardization
* Enforced corporate asset tagging rules by renaming the generic Windows machine to a structured asset ID (`W11-CLIENT-01`).

#### Step 9: Static IPv4 Schema & DNS Mapping
* Configured a static IP address (`172.16.0.100/24`) on the workstation, setting its primary DNS gateway to point directly to the Domain Controller (`172.16.0.10`).

#### Step 10: Connectivity Verification & Routing Fix
* Troubleshooting step: Disconnected legacy NAT adapters to resolve an interface routing loop, establishing clean Layer 3 ping connectivity over the virtual switch with 0% packet loss.

---

### Phase 4: Active Directory Forest Integration

#### Step 11: Domain Directory Authentication Challenge
* Triggered the endpoint domain-join wizard, allowing the client workstation to successfully resolve and locate the `mydomain.local` forest via DNS.

#### Step 12: Successful Domain Admission
* Authenticated administrative credentials to securely join the Windows 11 workstation to the active directory domain index.

#### Step 13: Centralized Identity Session Initiation
* Logged into the newly connected workstation for the first time using the enterprise network account domain credentials (`MYDOMAIN\Administrator`).

#### Step 14: Environment & Security Context Verification
* Executed system environment diagnostics (`whoami`) to verify that the workstation successfully recognizes the active network security context and administrative privileges.
