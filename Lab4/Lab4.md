# High Level Diagram
![HLD - Rehosting Migration](https://github.com/user-attachments/assets/85105f55-9017-44e0-a1cd-2b642062f678)


# Target Architecture

**AWS Lambda**

-   Earlier the web application was hosted on the WebServerVM, now to
    move to serverless architecture, I have used AWS lambda in place of
    it. Lambda scales automatically on the basis of incoming traffic.
    There is no need for us to manage the servers.

-   As the Lambda automatically adjusts the instance on the basis of
    incoming traffic , which increases the scalability.

**Amazon RDS**

-   MySQL database was previously hosted on the SQLVM , now in place of
    SQLVM we will integrate the Amazon RDS with mutli-AZ replication,
    which make sure that the database will be available among various
    zones and and will provide high availability. Also , in case the
    primary database fails , we have the backup database to take over
    everything.

-   Amazon RDS with multi-AZ replication makes sures that in case there
    is a failover , we have another standy copy to take over things
    which increase high availability , fault tolerance and reduced
    downtime.

# Serverless Architecture
**Reduced Downtime:** Due to automatic failover in RDS and the
inherent fault tolerance of AWS Lambda, the application will have
minimal downtown, well within the 6-hour limit.

**Scalability:** AWS Lambda scales automatically based on incoming
requests, handling spikes in traffic easily.

**Cost Savings:** Lambda only charges for the compute resources it
consumes, which means you are not paying for a server that's just not
in use. Also, managed services inside RDS decrease the effort one
needs to invest into database management and maintenance.

**High Availability:** With the Multi-AZ replication in place, RDS
becomes highly redundant, hence one can rest assured about the
availability of their database in case of an outage in one
Availability Zone.

