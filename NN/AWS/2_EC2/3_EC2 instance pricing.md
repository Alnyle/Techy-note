
#### EC2 Dedicated Instance

**EC2 Dedicated Hosts** are a type of Amazon EC2 offering where a physical server is allocated entirely to a single customer. This means that the physical hardware, including all of its EC2 instance capacity, is not shared with other customers, unlike in the typical EC2 instance offerings where resources are shared.

Here’s how it works:

### Key Features of EC2 Dedicated Hosts:

1. **Dedicated Hardware:**
    
    - You are the only customer using the physical server (host). This provides isolation at the hardware level, making it suitable for workloads with strict security or compliance requirements.
2. **Compliance Requirements:**
    
    - Some organizations have strict compliance standards (e.g., government or financial institutions) that require them to use hardware that isn't shared with other customers. EC2 Dedicated Hosts help address these regulations.
3. **Bring Your Own Licenses (BYOL):**
    
    - You can bring and use your **existing server-bound software licenses** (such as those licensed per-core, per-socket, or per-virtual machine) on EC2 Dedicated Hosts. This is particularly useful for software like Windows Server, SQL Server, Oracle, or others that require licensing tied to specific hardware.
4. **Visibility and Control:**
    
    - With EC2 Dedicated Hosts, you gain better visibility into the physical hardware, including the number of sockets, physical cores, and instance placement. This helps you manage your software licensing, optimize costs, and track the usage of your resources more effectively.
5. **Cost Management:**
    
    - If you're using software licensed per socket or per core (e.g., Oracle Database, Windows Server), a Dedicated Host can help manage costs by allowing you to control how the physical resources are allocated.
6. **Persistent Placement:**
    
    - Instances on Dedicated Hosts can have a more persistent placement. This can be important for applications requiring stable instance placement across different lifecycle events (e.g., stopping/starting the instance).

### Benefits:

- **Full Hardware Control**: You can control how instances are placed on the host and manage the host’s resources.
- **Compliance-Friendly**: Helps meet security and regulatory compliance standards by offering hardware isolation.
- **Cost Savings**: Allows you to bring and reuse existing software licenses, reducing the cost of new licenses.