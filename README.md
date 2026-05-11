# NAT-Overload-Lab
This project is a Cisco Packet Tracer lab that demonstrates the configuration of Dynamic PAT (NAT Overload) using a router’s outside interface IP address. The lab includes inside/outside NAT configuration, default route creation, ACL implementation, PAT overload configuration, and verification through connectivity testing and NAT translation tables.

# Network Topology
<img width="975" height="380" alt="image" src="https://github.com/user-attachments/assets/bee8d4de-3b3d-4660-8867-d443630084ee" />


### In this setup:
* R1 acts as the PAT router
* R2 simulates an outside ISP router
* PC1 and PC2 are internal hosts using private IPv4 addresses
* PAT allows multiple inside devices to share R1’s outside interface IP address simultaneously

## Step 1 – Configure NAT Inside and Outside Interfaces

The first step was configuring the interfaces on R1 and assigning NAT inside and outside roles.

<img width="959" height="500" alt="image" src="https://github.com/user-attachments/assets/0469fde4-e7ec-4724-8ea5-0d1bb9916978" />

## Step 2 – Configure Default Route and ACL

Next, a default route was configured so R1 could forward traffic toward the outside network.
A standard ACL was then created to identify which inside local addresses would be translated by NAT overload.

<img width="831" height="513" alt="image" src="https://github.com/user-attachments/assets/b9f0ce1d-4b23-473c-a120-3d5e777e13fa" />

### PAT was configured to translate all inside local addresses matching ACL 1 using the IPv4 address assigned to R1’s outside interface

## Step 3 – Configure R2
<img width="948" height="388" alt="image" src="https://github.com/user-attachments/assets/cd4dec38-5aeb-4f90-a07c-e1af095f7b1d" />

### R2 was configured with the appropriate outside network addressing to simulate an ISP router.

## Step 4 - Connectivity Tests

After configuration was completed, connectivity was tested from both internal PCs to verify successful NAT translations.

PC1 Connectivity Test
<img width="616" height="314" alt="image" src="https://github.com/user-attachments/assets/648fb9a2-7152-4db0-8819-8e0f013c06ba" />

PC2 Connectivity Test
<img width="617" height="314" alt="image" src="https://github.com/user-attachments/assets/57b9bffa-aa39-4af9-ae0e-e033d93349c0" />


Both PCs successfully reached the outside network.

## Step 5 – Verify NAT Translation Table

<img width="827" height="242" alt="image" src="https://github.com/user-attachments/assets/9bef36c3-dfb3-4e2c-aed0-769933042e9a" />

### NAT Translation Table

Notice how the inside global address remains the same for both internal hosts because PAT uses the IP address of R1’s outside interface while distinguishing sessions through unique port numbers.

## Summary & Takeaways

Through this lab, I gained hands-on experience in:

* Configuring NAT inside and outside interfaces
* Implementing Dynamic PAT (NAT Overload)
* Using standard ACLs to identify translatable inside local addresses
* Configuring default routes for outside network communication
* Allowing multiple hosts to share a single public IPv4 address
* Verifying translations using the NAT translation table
* Testing successful end-to-end connectivity

Packet Tracer file available in repository.
