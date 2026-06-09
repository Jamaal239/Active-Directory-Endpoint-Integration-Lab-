# Enterprise Infrastructure Sandbox: Active Directory & Endpoint Deployment

## Project Overview
This project demonstrates the end-to-end provisioning, engineering, and configuration of an isolated enterprise lab environment using Oracle VirtualBox. The infrastructure features a Windows Server Domain Controller managing a Windows 11 Enterprise client workstation over a secure, non-routable internal network.

## Key Skills Demonstrated
* **Active Directory & Identity Management:** Built a localized Active Directory forest (`sandbox.local`) with complete user session control.
* **Core Networking:** Configured standard static IPv4 schemas, localized DNS routing, and resilient multi-adapter network interface loops.
* **Systems Administration:** Managed virtualization layers, endpoint naming standardizations, and automated domain authentication workflows.

---

## 📜 Technical Deployment Log

### Phase 1: Domain Controller Provisioning & Core Networking

#### Step 1: Base Virtual Network Configuration
Configuring the virtualization network parameters for the primary server node, binding the virtual switch to an isolated local network segment.
![Base Virtual Network Configuration](screenshots/screenshot_1.png)

#### Step 2: Active Directory Domain Services (AD DS) Initialization
Installing and configuring the AD DS and DNS roles via Server Manager to prepare the environment for forest promotion.
![Active Directory Domain Services Initialization](screenshots/screenshot_2.png)

---

### Phase 2: Client Workstation Staging

#### Step 3: Virtual Hardware & Storage Allocation
Provisioning virtual storage limits and hardware resource pools within VirtualBox to isolate the client node profile.
![Virtual Hardware Allocation](screenshots/screenshot_3.png)

#### Step 4: Network Interface Configuration
Assigning the workstation's virtual network interface card (NIC) to the isolated internal switch, pulling it away from default public pools.
![Network Interface Configuration](screenshots/screenshot_4.png)

#### Step 5: Disk Partitioning & OS Installation
Partitioning unallocated disk storage blocks during the Windows 11 installation setup to create local root directories.
![Disk Partitioning & OS Installation](screenshots/screenshot_5.png)

#### Step 6: Local Administrator Account Creation
Provisioning the initial local administrator account profile (`sandboxadmin`) during the Windows Out-of-Box Experience (OOBE) setup phase.
![Local Administrator Account Creation](screenshots/screenshot_6.png)

#### Step 7: VirtualBox Guest Additions Deployment
Compiling and updating the hypervisor guest utility drivers to enable dynamic resolution scaling and shared clipboard utilities.
![VirtualBox Guest Additions Deployment](screenshots/screenshot_7.png)

---

### Phase 3: Network Optimization & Diagnostics

#### Step 8: Hostname Standardization
Enforcing corporate asset tagging rules by renaming the generic Windows machine to a structured asset ID (`W11-CLIENT-01`).
![Hostname Standardization](screenshots/screenshot_8.png)

#### Step 9: Static IPv4 Schema & DNS Mapping
Configuring a static IP address (`172.16.0.10/24`) on the workstation, setting its primary DNS gateway to point directly to the Domain Controller (`172.16.0.5`).
![Static IPv4 Schema & DNS Mapping](screenshots/screenshot_9.png)

#### Step 10: Connectivity Verification & Routing Fix
Troubleshooting steps disconnected legacy NAT adapters to resolve an interface routing loop, establishing clean Layer 3 ping connectivity over the virtual switch with 0% packet loss.
![Connectivity Verification & Routing Fix](screenshots/screenshot_10.png)

---

### Phase 4: Active Directory Forest Integration

#### Step 11: Executing the Domain Join Action
Opening the Computer Name/Domain Changes window on the workstation and entering domain credentials to initiate the directory handshake.
![Executing the Domain Join Action](screenshots/screenshot_11.png)

#### Step 12: Verifying Successful Domain Admission
Confirming the successful connection via the system confirmation dialog box welcoming the client machine to the `sandbox.local` domain.
![Verifying Successful Domain Admission](screenshots/screenshot_12.png)

#### Step 13: Centralized Identity Session Initiation
Logging into the newly connected workstation for the first time using the enterprise network account domain credentials (`sandbox.local\sandboxadmin`).
![Centralized Identity Session Initiation](screenshots/screenshot_13.png)

#### Step 14: Environment & Security Context Verification
Running system environment diagnostics (`whoami /groups`) via the command line to verify that the workstation successfully recognizes the active network security context and administrator privileges.
![Environment & Security Context Verification](screenshots/screenshot_14.png)
