# Section 1: On-Premises Solution Design

1. Web Application: A monolithic application hosted on physical servers.
2. SQL Database: Backend data stored in an SQL server.
3. File Storage: A local file system for file storage.
4. Networking: Managed with company-owned routers and firewalls.
5. Email Services: For customer notifications, running on local servers.

### Diagram: On-Premises


![onpremises-architecture](https://github.com/user-attachments/assets/df7066a4-f7ac-4199-9ca3-cc8cb5d980f5)




### Key Components to be Migrated

#### Web Application
- **Migration Target**: Azure App Service.
- **Service Type**: PaaS (Platform as a Service).
- **Explanation**: This PaaS architecture requires very little knowledge of servers as well as permits vertical scaling of web apps easily. Though it has its own complications; it reduces overhead on operations quite a lot.

#### SQL Database
- **Migration Target**: Azure SQL Database.
- **Service Type**: PaaS.
- **Explanation**: Fully managed SQL service that requires less maintenance as backups, scaling, patches are done automatically which will guarantee availability.

#### File Storage
- **Migration Target**: Azure Blob Storage.
- **Service Type**: PaaS.
- **Explanation**: Gives access to very rich and secure file cloud service which is not meant for archiving but serves as a repository of files and other media.

#### Networking
- **Migration Target**: Azure Blob Storage.
- **Service Type**: PaaS.
- **Explanation**: Gives access to very rich and secure file cloud service which is not meant for archiving but serves as a repository of files and other media.

#### Email Services
- **Migration Target**: Office 365.
- **Service Type**: SaaS.
- **Explanation**: Services such as Office 365 which are managed email services make email infrastructures less complex.

---

# Section 2: Migration Strategies

### 1. Web Application Migration
- **Migration Target**: Azure App Service PaaS or Azure Virtual Machine IaaS.
- **Explanation**: Employing PaaS specifically Azure App Service spares the user the headache of worrying about infrastructure as it is automatically managed with regards to scaling, upgrades and security. Traditionally, based on the level of control you desire over your environment an IaaS solution Azure Virtual Machine can be implemented use but this involves controlling the patches, scaling, and even backups often.
- **Recommendation**: PaaS (Azure App Service) is for people who want to reduce the complexity of maintaining multiple components that have the same functionality.

### 2. SQL Database Migration
- **Migration Target**: Azure SQL Database PaaS or Azure Virtual Machine IaaS.
- **Explanation**: Warring against the rotating schedule of patches by resolving to use PaaS like the Azure SQL Database offers you a fully managed service as all users tasks are automated and made place for. In case fullest control over the database is sought then a solution PaaS is employed but quite inconvenient, an IaaS approach SQL server on an Azure virtual machine is necessary.
- **Recommendation**: PaaS (Azure SQL Database) is more often the case due to managed systems specially designed for it and that are also properly scalable.

### 3. File Storage Migration
- **Migration Target**: Azure Blob Storage PaaS.
- **Explanation**: Storage Cloud offers a scalable secure and affordable storage platform with built-in security features with the additional advantage of disaster recovery. This is suitable for file and media assimilation with low levels of span control.
- **Recommendation**: Migrate to PaaS (Azure Blob Storage) for its simplicity and scalability.

### 4. Networking Migration
- **Migration Target**: Azure Virtual Network (Cloud-native).
- **Explanation**: With the focus on cloud-based solutions, organizations like Microsoft come up with infrastructure which is flexible and offers scalability as well as security. There are features present such as internal and external communication, VPNs, and firewalls securing the traffic.
- **Recommendation**: Move to cloud-native networking (Azure Virtual Network) for better security and scalability.

### 5. Email Service Migration
- **Migration Target**: Office 365 (SaaS).
- **Explanation**: SaaS solutions like Office 365 are managed especially for clients and thus no administration of an infrastructure as a service is necessary.
- **Recommendation**: Use SaaS (Office 365) for fully managed email services.

---

# DIAGRAM – CLOUD PERMISES

![cloudmigration-architecture](https://github.com/user-attachments/assets/afdcb69c-e658-4fa1-8dd0-c1fe7925e3cf)



### Explanation of Cloud Components

- **Cloud Networking (Azure Virtual Network)**: Manages internal and external communication, offering security and flexibility.
- **PaaS Web App (Azure App Service)**: Manages the web application, scaling automatically to meet traffic demands.
- **PaaS Database (Azure SQL Database)**: A fully managed database service with automated updating, backups, and scaling.
- **PaaS File Storage (Azure Blob Storage)**: Provides secure, scalable storage for data.
- **SaaS Email Service (Office 365)**: Handles email communication without requiring any infrastructure management.

