## Virtual Private Cloud (VPC)  
- [**Shared VPC**](https://cloud.google.com/vpc/docs/shared-vpc)
    - Allows an organization to connection resources from multiple projects to a common VPC network, so that they can communicate with other securely and effciently using internal IPs from that network.
- **[VPC Network Peering](https://cloud.google.com/vpc/docs/vpc-peering)**
    - Allows connectivity between two VPC networks regardless if they are in different projects or organizations.
- **[Load Balancers](https://cloud.google.com/load-balancing/docs/choosing-load-balancer)**
    - A load balancer distributes users traffic across multiple instances of your applications. By spreading the load, load balacing reduces the risk that your applications experience performance issues.
- **Cloud VPN vs. Cloud Interconnect**
    - Cloud Interconnect offers [low-latency and high availability to transfer data between on-premise and VPC networks](https://cloud.google.com/network-connectivity/docs/interconnect/concepts/overview).
        - *Dedicated Interconnect* provides a direct physical connection between your on-premises network and Google's network.
        - *Partner Interconnect* provides connectivity between your on-premises and VPC networks through a supported service provider.
    - Consider using Cloud VPN if you [don’t require low-latency and high availability](https://cloud.google.com/network-connectivity/docs/interconnect/concepts/overview#cloud-vpn-considerations) to set up IPSec VPN tunnels between your networks. IPSec VPN tunnels encrypts data.
        - A Cloud VPN tunnel doesn't require the overhead or costs associated with a direct, private connection. Cloud VPN only requires a VPN device in your on-premises network.

### Shared VPC
Shared VPC allows projects to share a common VPC network. VPNs are used to link VPCs to on premises networks.   
Shared VPCs can be created at the organization or folder level of the resource hierarchy.  


### Command to create VPC  

```bash
gcloud compute networks create
```

Flow Log option of the `create vpc` command determines wheter logs are sent to Cloud Logging.


### Creating VPN  
When you create VPN, you need to create forwarding rules, tunnels and gateways with use of:
- `gcloud compute forwarding-rule`    
- `gcloud compute target-vpn-gateways`  
- `gcloud compute vpn-tunnels`  


### Creating firewall  
Example of `gcloud` command:  
```bash
gcloud compute firewall-rules create ace-exam-fwr2 --network ace-exam-vpc1 --allow tcp:20000-25000
```
Parameters:  

### Structure of Firewall Rules  
- Direction
- Priority
- Action
- Target
- Source/destination
- Protocol and port
- Enforcement status


### Default firewalls  
Default network is created with four network rules:  
- Incoming traffic from any VM instance on the same network
- Incoming TCP traffic on port 22 - allowing SSH
- Incoming TCP traffic on port 3389 - allowing Microsoft Remote Desktop Protocol (RDP)
- Incoming Internet Control Message Protocol (ICMP) from any source on the network  
The default rules all have priority 65534.  



### Implied rules  
All VPCs start with two implied rules:  
- Allow egress traffic from any source (IP address 0.0.0.0/0).  
- Deny all incoming traffic from any source (IP address 0.0.0.0/0).

Implied rules have priority 65535. You cannot delete and implied rule.  

### Load Balancers characteristics  
- Global vs Regional  
- External vs Internal  
- Traffic type (HTTP, TCP)  

Global load balancers are used when an application is globally distributed.  

Regional load balancers are used when an application is in a single region.  

**Global Load Balanacers**:  
- HTTP(S) (balances HTTP and HTTPS load across backend instances)
- SSL Proxy  (terminates SSL/TLS connections - non-HTTPS traffic)
- TCP Proxy (terminates TCP session at the load balancer and then forwards traffic to backend servers)

**Regional Load Balancers**:  
- Internal TCP/UDP (balances TCP/UDP traffic on private networks hosting internal VMs)
- Network TPC/UDP (balancing based on IP protocol, address and port)

### Target pools in Cloud Load Balancing
A target pool is a group of backend instances that receive incoming traffic from external passthrough Network Load Balancers. All backend instances of a target pool must reside in the same Google Cloud region. Target pools use HTTP health checks.

### URL maps in Cloud Load Balancing
URL maps specify direct requests to particular services. A URL map is a set of rules for routing incoming HTTP(S) requests to specific backend services or backend buckets. A minimal URL map matches all incoming request paths `/*`.

### Routes in Cloud Load Balancing
Routes are used to specify paths to destination IP addresses outside a subnet.

### Firewall rules in Cloud Load Balancing
Firewall rules control the flow of traffic on a network.  

### Traces in Cloud Load Balancing  
Traces are used to understand performance characteristics of services in a distributed system.  
