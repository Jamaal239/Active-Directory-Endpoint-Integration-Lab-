# Enterprise Infrastructure Sandbox: Active Directory & Endpoint Deployment

## Project Overview
This project demonstrates the setup and configuration of an isolated enterprise lab environment using Oracle VirtualBox. The infrastructure features a Windows Server Domain Controller managing a Windows 11 Enterprise client workstation over a secure, non-routable internal network.

## Key Skills Demonstrated
* **Active Directory & Identity Management:** Built a localized Active Directory forest (`sandbox.local`) with complete user session control.
* **Core Networking:** Configured standard static IPv4 schemas, localized DNS routing, and resilient virtual network switches.
* **Systems Administration:** Managed virtualization layers, endpoint naming standardizations, and automated domain authentication workflows.

---

## 📜 Technical Deployment Log

### Phase 1: Domain Controller Promotion & Hypervisor Staging

#### Step 1: Active Directory Domain Services Wizard Initialization
Opening the Active Directory Domain Services configuration setup to begin the foundational process of promoting the server to a new enterprise forest.
![Active Directory Domain Services Wizard Initialization](screenshots/screenshot_1.png)

#### Step 2: Client Virtual Machine Hardware Optimization
Configuring the system memory (RAM) and core virtualization motherboard properties for the Windows 11 client workstation inside VirtualBox.
![Client Virtual Machine Hardware Optimization](screenshots/screenshot_2.png)

---

### Phase 2: Client Workstation Operating System Staging

#### Step 3: Virtual Network Isolation Configuration
Configuring the client virtual machine's network adapter inside VirtualBox, switching it to an isolated Internal Network to prevent external internet routing.
![Virtual Network Isolation Configuration](screenshots/screenshot_3.png)

#### Step 4: Storage Partitioning and OS Installation Setup
Selecting the unallocated virtual storage drive within the Windows 11 installation wizard to begin installing the base operating system files.
![Storage Partitioning and OS Installation Setup](screenshots/screenshot_4.png)

#### Step 5: Completing Operating System Installation
Monitoring the installation progress screen as the setup wizard finishes copying files, installing features, and applying configurations.
![Completing Operating System Installation](screenshots/screenshot_5.png)

#### Step 6: VirtualBox Guest Additions Deployment
Running the VirtualBox Guest Additions utility installer within the active desktop environment to enable seamless display scaling and shared clipboard features.
![VirtualBox Guest Additions Deployment](screenshots/screenshot_6.png)

#### Step 7: Local Administrator Account Creation
Provisioning the initial local administrator account profile (`sandboxadmin`) during the Windows Out-of-Box Experience (OOBE) setup phase.
![Local Administrator Account Creation](screenshots/screenshot_7.png)

---

### Phase 3: Network Optimization & Diagnostics

#### Step 8: Hostname Standardization
Enforcing corporate asset tagging rules by renaming the generic Windows desktop machine within the System Settings to a structured asset ID (`W11-CLIENT-01`).
![Hostname Standardization](screenshots/screenshot_8.png)

#### Step 9: Static IPv4 Schema & DNS Mapping
Configuring a static IP address (`172.16.0.10/24`) on the workstation and setting its primary DNS gateway to point directly to the Domain Controller's identity interface (`172.16.0.5`).
![Static IPv4 Schema & DNS Mapping](screenshots/screenshot_9.png)

#### Step 10: Connectivity Verification & Routing Fix
Troubleshooting network interfaces to resolve routing loops, establishing clean Layer 3 ping connectivity over the virtual switch with 0% packet loss.
![Connectivity Verification & Routing Fix](screenshots/screenshot_10.png)

---

### Phase 4: Active Directory Forest Integration

#### Step 11: Executing the Domain Join Action
Opening the Computer Name/Domain Changes window on the workstation and entering domain administrator credentials to initiate the directory handshake.
![Executing the Domain Join Action](screenshots/screenshot_11.png)

#### Step 12: Verifying Successful Domain Admission
Confirming the successful connection via the system confirmation dialog box welcoming the client machine to the `sandbox.local` domain.
![Verifying Successful Domain Admission](screenshots/screenshot_12.png)

#### Step 13: Environment & Security Context Verification
Running system environment diagnostics (`whoami /groups`) via the command line to verify that the workstation successfully recognizes the active network security context and administrator privileges.
![Environment & Security Context Verification](screenshots/screenshot_13.png)

#### Step 14: Final Staged Enterprise Infrastructure
Successfully booting into the fully configured domain workspace environment, validating the completion of the endpoint integration deployment.
![Final Staged Enterprise Infrastructure](screenshots/screenshot_14.png)
