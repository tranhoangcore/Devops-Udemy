# Azure from zero to here

### 1. **Introduction to the Cloud**

#### **1. Introduction to the Cloud**

   Why you need cloud? What is this in the past?

#### **2. What is the Cloud?**

   Compute, Networking, Storage and other services managed by someone else.

#### **3. CapEx vs OpEx**

|                 Capital Expense                 | Operating Expense |
| :---------------------------------------------: | :---------------: |
| Making upfront investment for future use/profit |   Pay as you go   |

#### **4. IaaS, PaaS, SaaS**

   ![img](https://miro.medium.com/max/1179/1*qD4iN1yAojNQLQx3_hHcQg.png)
   ![img](https://miro.medium.com/max/2382/0*41Hh9XgGbfvB5JQG.png)

#### **5. Types of Clouds**

|                            Public                            |                           Private                            |                            Hybrid                            |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| The cloud resources (like servers and storage) are owned and operated by a third-party cloud service provider and delivered over the internet. With a public cloud, all hardware, software, and other supporting infrastructure are owned and managed by the cloud provider. Microsoft Azure is an example of a public cloud | A private cloud consists of cloud computing resources used exclusively by one business or organization. The private cloud can be physically located at your organization’s on-site datacenter, or it can be hosted by a third-party service provider. But in a private cloud, the services and infrastructure are always maintained on a private network and the hardware and software are dedicated solely to your organization. | Combines on-premises infrastructure—or a private cloud—with a public cloud. Hybrid clouds allow data and apps to move between the two environments. |
|             AWZ, Azure, Google Cloud, IBM Cloud              |             VMWare Cloud, OpenShift, Azure Stack             |                   Azure Arc, AWS Outposts                    |

#### 6. Main Cloud Providers

![top cloud service provider](https://csharpcorner-mindcrackerinc.netdna-ssl.com/article/top-10-cloud-service-providers/Images/Top%20cloud%20providers.jpg)￼

### 2. **Introduction to Azure**

#### 1.  Introduction

- Microsoft

- Announced 2008

- Released 20120

#### 2. Regions and Zones

- Region: a set of datacenters

- Zone: a datacenter

#### 3. Azure Services

   Everything that can be done  in the cloud is called Cloud Services

#### 4.  Creating Account

   https://azure.microsoft.com/en-us/

### 3. **First Look at Azure**



***The Five Disciplines of Cloud Governance***

![img](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/_images/operational-transformation-govern-large.png#lightbox)

#### 1. The Azure Portal

> The Azure portal is a web-based, unified console that provides an alternative to command-line tools.

#### 2. Account and Subscription

| Subscription (Logical Container) |        Account (Identity)         |
| :------------------------------: | :-------------------------------: |
|  Contains the various resources  | Identity with access to resources |

#### 3. Resources

- Creating resource

- Removing a resouce

#### 4. Azure CLI & PowerShell

### 4. **Azure Basic Concepts**

#### 1. Regions

  How to choose region:

- Location

- Service available

- Price

#### 2. Resource Groups

![](https://images2.imgbox.com/ea/c3/E2Zx92p8_o.png)

  Prefix: 

```
admin-rg
```

#### 3. Storage Accounts

  An Azure storage account contains all of your Azure Storage data objects:

- Blobs

- File shares

- Queues

- Tables

- Disk

#### 4. SLA

- Service-level agreements
- Uptime % cloud service
- https://uptime.is/

#### 5. Cost

   Pricing Model:

- Per resource (VM)

- Per consumption (Function App)

- Reservations

### 5. **Introducing Our App**

ReadIt!

- Book catalog

- Shopping Cart

- Inventory Management

- Order Engine

### 6. **Azure Compute**

#### 1. Introduction

![Decision tree for Azure compute services](https://docs.microsoft.com/en-us/azure/architecture/guide/technology-choices/images/compute-choices.png)

In this course:

- Virtual Machines

- App Services

- AKS

- Azure Functions

#### 2. Virtual Machines

  *Unmanaged Service*

<img src="https://images2.imgbox.com/32/81/iF4fatGC_o.png" style="zoom:50%;" />



##### **Steps for creating VM in Azure**

- Selection Location
- Image (OS + pre-installed software)
- Size

##### Cost of VM

- VM
- Disk
- IP
- Storage

##### Azure Resource Manager Template (ARM Template)

![Resource Manager request model](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/media/overview/consistent-management-layer.png)

![img](https://miro.medium.com/max/1442/1*SiZ0VADTxZlbVHucXXojuA.png)



##### Virtual Machine Scale Set

###### Why

- Easy to create and manage multiple VMs

- Provides high availability and application resiliency

- Allows your application to automatically scale as resource demand changes

- Works at large-scale (support 1,000 VM instances)

###### Differences between virtual machines and scale sets

| Scenario                           | Manual group of VMs                                          | Virtual machine scale set                                    |
| ---------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Add additional VM instances        | Manual process to create, configure, and ensure compliance   | Automatically create from central configuration              |
| Traffic balancing and distribution | Manual process to create and configure Azure load balancer or Application Gateway | Can automatically create and integrate with Azure load balancer or Application Gateway |
| High availability and redundancy   | Manually create Availability Set or distribute and track VMs across Availability Zones | Automatic distribution of VM instances across Availability Zones or Availability Sets |
| Scaling of VMs                     | Manual monitoring and Azure Automation                       | Autoscale based on host metrics, in-guest metrics, Application Insights, or schedule |

##### Virtual Machines Tips and Tricks

- If your VM needs more disks, in addition to the default one provided by Azure, then go to the Disks page for that, and add whatever disk you need. Don't forget that disks have costs, and check it in the calculator beforehand.
- Want to backup your VM so that it can be restored in a case of failure? Check the Backup page, where you can define the frequency of the backup and the retention period.
- You can define DNS name for the VM, so that it will be accessible not just using its IP. This can be done by clicking the DNS Name: Configure link in the Overview page.

#### 3. App Services

<img src="https://miro.medium.com/max/2812/1*jSUzukmOtd8jdzOus9h3Gw.png" alt="Image showing the services available as part of Azure App Service" style="zoom:50%;" />

   *Azure App Service* is an HTTP-based service for hosting web applications, REST APIs, and mobile back ends.

##### App Services Tips and Tricks

- By default, App Services can be accessed using *http* and *https*. You can make it *https* only in the TLS/SSL settings in the App Service menu.
- App service can run also batch processes, or continuous jobs, and not only web apps with the request / response paradigm. This can be done using the WebJobs menu item, where you can upload exe file that will run always, or on scheduled times.
- Want to know the IP address of the App Service? Take a look at the Properties of the page. You can find there the Virtual IP address of the App Service, and also - the Outbound IP addresses. Note the plural - App Service can have more than one outbound IP address.
- Want to know how much storage did you use, and what are the current usage statistics? Go to Quotas for this data.

#### 4. **Azure** Kubernetes Service (AKS)

>    Azure Kubernetes Service (AKS) simplifies deploying a managed Kubernetes cluster in Azure by offloading the operational overhead to Azure. 

##### Containers

> Standardized, portable packaging for your applications

![img](https://azurecomcdn.azureedge.net/cvt-afa119cf5cfa972a993a0804f2d106cd1b8dc417f448ccee8a6d2720813d1a65/images/page/overview/what-is-a-container/valprop1.svg)

![img](https://azurecomcdn.azureedge.net/cvt-afa119cf5cfa972a993a0804f2d106cd1b8dc417f448ccee8a6d2720813d1a65/images/page/overview/what-is-a-container/valprop2.svg)

##### Introduction to Docker

>    Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications. By taking advantage of Docker’s methodologies for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.

![Docker Architecture Diagram](https://docs.docker.com/engine/images/architecture.svg)

##### Containers Management

- Deployment

- Scalability

- Monitoring

- Routing

- High-Availability

#####  Introduction to Kubernetes

> Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

<img src="https://miro.medium.com/max/3032/1*t5TbINIv1vbTYCTraPy16g.png" alt="Các thành phần Kubernetes." style="zoom:50%;" />

#### 5. Azure Functions

> Azure Functions is a serverless solution that allows you to write less code, maintain less infrastructure, and save on costs. Instead of worrying about deploying and maintaining servers, the cloud infrastructure provides all the up-to-date resources needed to keep your applications running.

<img src="https://www.jiadongchen.com/2021/03/azure-functions-best-practice-reuse-client-instances-in-two-different-ways/featured.png" alt="img" style="zoom:33%;" />

##### Triggers and Bindings

| Triggers                             | Bindings                                  |
| ------------------------------------ | ----------------------------------------- |
| The event that made the function run | Declarative connection to the resource(s) |
| Quite a few                          | Input, Output or both                     |
| Deeply integrated into other Azure   | Provided as parameter to the function     |
| Technically not mandatory            | Makes connecting to other resource easy   |
|                                      | Not mandatory                             |

##### Durable Functions

![A diagram of the function chaining pattern](https://docs.microsoft.com/en-us/azure/azure-functions/durable/media/durable-functions-concepts/function-chaining.png)

> *Durable Functions* is an extension of [Azure Functions](https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview) that lets you write stateful functions in a serverless compute environment. The extension lets you define stateful workflows by writing [*orchestrator functions*](https://docs.microsoft.com/en-us/azure/azure-functions/durable/durable-functions-orchestrations) and stateful entities by writing [*entity functions*](https://docs.microsoft.com/en-us/azure/azure-functions/durable/durable-functions-entities) using the Azure Functions programming model. Behind the scenes, the extension manages state, checkpoints, and restarts for you, allowing you to focus on your business logic.

##### 

### 7. **Azure Networking**

#### 1. Networking in Azure

![img](https://s3-us-west-2.amazonaws.com/media.forumbee.com/i/47d9d677-75bd-4328-ae40-f9d9aa3ffd87/547.png)

Talked about:

- VNets

- SubNets

- Load Balancer

- Application Gateway

##### 2. Virtual Networks

Azure Virtual Network (VNet) is the fundamental building block for your private network in Azure. VNet enables many types of Azure resources, such as Azure Virtual Machines (VM), to securely communicate with each other, the internet, and on-premises networks. VNet is similar to a traditional network that you'd operate in your own data center, but brings with it additional benefits of Azure's infrastructure such as scale, availability, and isolation.

- VNets are free

- Limit 50 in region

###### Classless Inter-Domain Routing (CIDR Notation)

> Size = 2^(32-Range)
>
> So, for example, in this case:
>
> 109.186.149.240/24
> This is what we get:
>
> Size = 2^(32-24) = 2^8 = 256

##### 3. Subnets

> A subnet is a range of IP addresses in the VNet. You can divide a VNet into multiple subnets for organization and security. Each NIC in a VM is connected to one subnet in one VNet. NICs connected to subnets (same or different) within a VNet can communicate with each other without any extra configuration.

- Free
- Limit 3000 subnet per VNet


![Virtual networks - Azure Virtual Machines | Microsoft Docs](https://docs.microsoft.com/en-us/azure/virtual-machines/media/virtual-machines-common-network-overview/vnetoverview.png)

######  Network Security Groups

> filter network traffic to and from Azure resources in an Azure virtual network. A network security group contains security rules that allow or deny inbound network traffic to, or outbound network traffic from, several types of Azure resources. For each rule, you can specify source and destination, port, and protocol.



- Source or Destination
- Port range
- Protocol

######  Network Peering

> Virtual network peering enables you to seamlessly connect two or more Virtual Networks in Azure. The virtual networks appear as one for connectivity purposes. The traffic between virtual machines in peered virtual networks uses the Microsoft backbone infrastructure. Like traffic between virtual machines in the same network, traffic is routed through Microsoft's private network only

- Use private IP


##### 4. Secure VM Access

###### JIT Access

> Just in Time Access

   Open the port and auto close.


###### VPN

##### Jump Box

> Put another VM in VNet

##### Bastion

> Web-based connection to the VM



Azure Private Links vs Azure Service Endpoints 

###### Azure Private Links

>  Azure Private Link (Private Endpoint) allows you to access Azure PaaS services over Private IP address within the VNet. It gets a new private IP on your VNet. When you send traffic to PaaS resource, it will always ensure traffic stays within your VNet.

###### Azure Services Endpoints

> Azure Service Endpoint provides secure and direct connectivity to Azure PaaS services over an optimized route over the Azure backbone network. Traffic still left your VNet and hit the public endpoint of PaaS service.

Azure PaaS Services: SQL Databases, Storage, Key Vault, ServicesBus, App Services, Cosmos DB, Event Hubs, SQL Data Warehouse etc.
Key Points
Access
Service endpoint — It remains a publicly routable IP address.
Private endpoint — It is a private IP in the address space of the virtual network where the private endpoint is configured.
Both are design to allow you to restrict who connects to your service. Traffic between your virtual network and the service travels the Microsoft backbone network without going over the internet.
Data Exfiltration protection
Service Endpoint — Traffic need to be passed through an NVA/Firewall for exfiltration protection.
Private Link — It has an inbuilt data protection.
On-Premise Connectivity
Service Endpoints — it is not easily restrict on-premise traffic. They can only be secured to Azure VNet.
Private Links — Easily extensible for On-premises network traffic via ExpressRoute or VPN tunnels.
Complexity
Service Endpoint — It’s much simpler to implement and significantly reduce complexity of your architecture design.
Private Link — Need to manage another resource.
Cost
Service Endpoint — There is no additional cost for using VNet service endpoints.
Private Link — It costs can quickly grow depending on total ingress and egress traffic and runtime of the link.
Availability
Both services are not available for all resources/services. See the complete list for Service Endpoints and Private Link.
Summary
Use a private endpoint, if you want to be able to block all internet traffic to a target resource.
Private Link is superior to Service Endpoint in Security.

##### Load Balancer

> *Load balancing* refers to evenly distributing load (incoming network traffic) across a group of backend resources or servers.



##### Application Gateway

> a web traffic load balancer that enables you to manage traffic to your web applications. Traditional load balancers operate at the transport layer (OSI layer 4 - TCP and UDP) and route traffic based on source IP address and port, to a destination IP address and port.



### 8. **Data in Azure**

### 9. **Messaging in Azure**

<img src="https://www.serverless360.com/wp-content/uploads/2018/07/Segmentation-of-the-Azure-Messaging-Services.png" alt="Microsoft Azure Messaging Service" style="zoom:150%;" />

### 10. **Azure AD**

### 11. **Monitoring in Azure**

![Azure Monitor overview](https://docs.microsoft.com/en-us/azure/azure-monitor/media/overview/overview.png)

- **Metrics** are numerical values that describe some aspect of a system at a particular point in time. They are lightweight and capable of supporting near real-time scenarios. 

- **Logs** contain different kinds of data organized into records with different sets of properties for each type. Telemetry such as events and traces are stored as logs in addition to performance data so that it can all be combined for analysis.

#### 1. Insights

> Insights provide a customized monitoring experience for particular Azure services. They require minimal configuration and increase your visibility into the operation of critical resources.

### 2. Alerts

> Alerts in Azure Monitor proactively notify you of critical conditions and potentially attempt to take corrective action. Alert rules based on metrics provide near real time alerts based on numeric values. Rules based on logs allow for complex logic across data from multiple sources.
