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

