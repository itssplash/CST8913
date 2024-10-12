**Lab Report: Rehosting a 3-Tier eCommerce Application to AWS**

* * * * *
![HLD - Lab5](https://github.com/user-attachments/assets/c6c24056-5d03-4ca4-9c9a-0435435b0a11)


# Target Cloud Architecture:

**AWS Services and Roles**

1.  **Amazon EC2**

-   **Front End :** The frontend web server is rehosted on EC2 instance , which gives it the flexibility and control over operating system, configurations and application settings.
-   **Backend:** The backend server is also rehosted on EC2 instances , and it can scale dynamically using Auto scaling group based on the incoming traffic

2.  **Amazon RDS (Relational Database Service):**

-   The SQL database is moved to Amazon RDS. The RDS controls tasks such as backups, software updates, and automatic failover backup using Multi-AZ deployments for high availability.

3.  **Application Load Balancer (ALB):**

-   The Application load balancer is used to load the balance across the frontend instances. It make sure that web applications can hangle high traffic efficiently.

4.  **Auto Scaling:**

-   The Auto scaling group takes care of the backend part, and make sures it maintains its performance.

5.  **VPC:**

- It ensures the networking part, distributing them between public and private subnets for security and isolation.

# Target Architecture: Scalability, Availability, and Disaster Recovery

**Scalability**

-   **Auto Scaling Groups**: The EC2 instances for backend are deployed in an Auto Scaling Group .This allows the application to automatically number of running instances based on traffic load, ensuring optimal performance during peak usage and cost savings during low usage.
-   **Application Load Balancer (ALB):** The ALB distributes incoming traffic to multiple front end EC2 instances, allowing the application to handle increased user requests easily.

**Availability**

- Multi-AZ Deployment: Amazon RDS is further set up with Multi-AZ deployment to ensure a highly available database layer. In the case of a failure in one Availability Zone, automatic failover to another AZ happens from an available standby instance, thus reducing chances of outage and therefore downtown.

- Multiple copies of instances of the frontend and backend are duplicated across different AZs. This redundancy means that, in the event of failure of one instance, others can serve client requests and hence ensure overall application availability.

**Disaster Recovery**

- Data Replication: The RDS instances will be set up with automatic replication of data across AZs. This ensures that in case a user loses some data, it can easily be recovered in the quickest time in case of a disaster.

- Data Backup Strategy: Backups of the RDS database can be scheduled and configured for point-in-time recovery to further protect against data loss because of human error or system failures.

  

# Migration Process Overview

**Phase 1: Pre-Migration Planning**

-   First we will have to analyze the on-premises application architecture and discover the dependencies and challenges and then design a High Level Diagram.

**Phase 2: AWS Environment Setup**

-   Set up a Virtual Private Cloud (VPC) with public and private subnets across multiple Availability Zones (AZs).
-   Provision frontend and backend EC2 instances in their respective subnets and configure security groups.
-   Create an Application Load Balancer (ALB) to manage incoming traffic to the frontend instances.
-   Launch Amazon RDS with Multi-AZ deployment for the SQL database, ensuring high availability.

**Phase 3: Data Migration**

-   Use AWS Database Migration Service to replicate the data continuously from the on-premises SQL database to Amazon RDS.
-   Organize pre-migration testing in AWS environments to make sure all components work properly.

**Phase 4: Final Cutover**

-   Select a low-traffic users time for the final migration to decrease user disruption so that downtime is not exceeding 2 hours and then also do a last sync with Database Migraton service to capture latest data.

**Phase 5: Post-Migration Activities**

-   Use AWS CloudWatch to monitor performance metrics such as CPU usage and error rates.
-   Keep the original on-premises environment on standby. If issues arises, redirect traffic back to it via DNS.

**Phase 6: Optimization**

-   Review performance metrics and adjust scaling policies, instance types, and database configurations for better performance.
