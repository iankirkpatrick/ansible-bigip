# ansible-bigip
This is ansible playbook which will configure an F5 BIGIP LTM appliance

The playbook requires that the following dependencies have been met before first run:

1. F5 is connected to network
2. MGMT IP assigned
3. F5 has been licensed and initial configuration has been completed

This playbook relies on the following variables being defined in the inventory file.
An example would be as follows:

[f5-devices]<br>
bigip1

[f5-devices:vars]<br>
F5_USER=admin<br>
F5_PASSWORD=<password><br>
F5_SERVER_PORT=443<br>
F5_VALIDATE_CERTS=NO<br>

It is recommended that the inventory file is encrypted using ansible-vault to protect the account details. 

The variables are currently defined in the playbook, you should adjust the playbook with your own network details. 

The playbook currently configures the following:

Partitions<br>
Route-domains<br>
VLANs<br>
Associate VLANs with Route-domains<br>
Self IP's (both local and floating)<br>
ICMP monitors<br>
Nodes<br>

To be added in the future:

Additional monitors (TCP, UDP, HTTP and HTTPS)<br>
Pools<br>
Virtual-Servers<br>
Source-NAT<br>


# Tested with the software versions

BIGIP 11.6.1<br>
Ansible 2.4<br>




