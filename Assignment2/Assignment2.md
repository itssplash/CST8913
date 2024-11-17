# VMware to Azure Migration Lab Documentation

## Table of Contents
1. [Introduction](#introduction)  
2. [Environment Setup](#environment-setup)  
3. [OS Installation](#os-installation)  
4. [Application Deployment](#application-deployment)  
5. [Migration Assessment](#migration-assessment)  
6. [VM Migration Execution](#vm-migration-execution)  
7. [Validation and Failover Testing](#validation-and-failover-testing)  
8. [Reflection](#reflection)  

---

## Introduction
This document summarizes the steps, findings, and outcomes of the VMware to Azure migration lab. The objective was to migrate a Windows Server-based virtual machine (VM) running a “Hello World” web application to Azure using Azure Migrate tools.

---

## Environment Setup
### Task: Install VMware Workstation and create a new VM  
**Objective:** Prepare a VM environment on the local system.  
**Steps Taken:**  
1. Downloaded and installed VMware Workstation.  
2. Created a new virtual machine with allocated resources (e.g., 2 CPUs, 4GB RAM, 60GB HDD).  

**Outcome:**  
The VMware Workstation was successfully set up, and a new VM instance was launched.

---

## OS Installation
### Task: Install Windows Server OS on the VM  
**Objective:** Set up a Windows Server instance as the primary VM environment.  
**Steps Taken:**  
1. Installed Windows Server 2019 from the Azure subscription’s software portal under Education resources.  
2. Performed initial configurations, including:  
   - Setting up an administrator account.  
   - Enabling Remote Desktop and necessary firewall rules.  

**Outcome:**  
The Windows Server OS was successfully installed and configured.

---

## Application Deployment
### Task: Deploy a “Hello World” web application on the Windows Server  
**Objective:** Test basic server and network functionality.  
**Steps Taken:**  
1. Installed .NET on the Windows Server.  
2. Deployed a basic "Hello World" application by using basic CMD commands.  
3. Verified access to the application at `http://localhost/5022` within the VM network.  

**Outcome:**  
The application was accessible at `http://localhost/5022` within the VM network.

---

## Migration Assessment
### Task: Use Azure Migrate to perform an assessment of the VM for migration readiness  
**Objective:** Evaluate the VM’s compatibility with Azure and note any necessary adjustments.  
**Steps Taken:**  
1. Created a migration project named "HelloWorldMigration".  
2. Installed the Azure Installer on the VM.  
3. Used PowerShell to run the three scripts required for Azure Migrate on the VM.  

**Challenges Encountered:**  
- **Error 2147942405: Access Denied** while setting up prerequisites for Azure Migrate.  
  - **Resolution:** Resolved the issue by following instructions from [this guide](https://learn.microsoft.com/en-us/answers/questions/514610/azure-migrate-discovery-and-assessment-error-21479). Logged in with my College ID, then proceeded with the migration steps.  
4. Completed the discovery and assessment phases.  
5. Built the business case and assessment report. I have the Excel file for both the business case and the assessment report.

**Outcome:**  
A migration readiness assessment report was successfully generated, and the migration project was prepared.

---

## VM Migration Execution
### Task: Migrate the VM to Azure using Azure Migrate tools  
**Objective:** Complete the VM migration to Azure.  
**Steps Taken:**  
1. Created another VM for the replication server.  
2. Installed the Mobility Agent on the VM (faced challenges initially). Resolved the issue by researching StackOverflow and online resources.  
3. Used Azure Migrate tools to replicate the VM to Azure (replication took about 2 hours).  
4. Created a VNet and Network Security Group (NSG) for the replicated server.  
5. Replicated the server to Azure.  

**Outcome:**  
The VM instance was successfully migrated to Azure. The server was replicated and operational in the cloud.

---

## Validation and Failover Testing
### Task: Validate the migrated VM's functionality and conduct a failover test  
**Objective:** Ensure the application runs as expected post-migration and test failover mechanisms.  
**Steps Taken:**  
1. Accessed the “Hello World” application on the Azure VM via a web browser.  
2. Simulated a failover by shutting down the primary VM and testing availability.  

**Outcome:**  
The application was functional in Azure, and failover mechanisms were validated successfully.

---

## Reflection
### Challenges Encountered:
- **Firewall Configuration:** Initial issues with accessing the application externally due to firewall settings on Azure.  
   - **Resolution:** Updated Azure Network Security Group (NSG) rules to allow HTTP traffic.  
- **Mobility Agent Installation:** Faced challenges during the Mobility Agent installation on the VM.  
   - **Resolution:** Resolved by consulting online resources such as StackOverflow.
- **Performance Optimization:** The VM required resizing after migration to improve performance.  

### Insights Gained:
- Azure Migrate simplifies the migration process significantly, but thorough pre-migration assessment is crucial for a smooth transition.  
- Post-migration validation is essential to ensure operational continuity.

---
