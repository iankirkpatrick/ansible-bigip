# ansible-bigip
This is ansible playbook which will configure an F5 BIGIP LTM appliance

The playbook requires that the following dependencies have been met before first run:

1. F5 is connected to network
2. MGMT IP assigned
3. F5 has been licensed and initial configuration has been completed
4. Ansible role installed using ansible-galaxy

ansible-galaxy role install mkouhei.include_csv

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

The variables are read from formatted csv files, the playbook is supplied with sample csv files, you should replace the data in the csv files with your own.
The playbook indicates which files should be adjusted for each configuration task.  

The playbook currently configures the following:

Partitions<br>
Route-domains<br>
VLANs<br>
Associate VLANs with Route-domains<br>
Self IP's (both local and floating)<br>
ICMP monitors<br>
Nodes<br>
Basic Pools<br>
Basic Virtual-servers fastL4 without SSL offloading or SNAT<br>
TCP half open monitors<br>

To be added in the future:

Additional monitors (UDP, HTTP and HTTPS)<br>
Pools using priority groups and other lb_methods than round-robin<br>
Virtual-Servers with SSL offloading and or Source NAT<br>
Source-NAT pools<br>
iRules<br>

# Tested with the following software versions

BIGIP 14.1.2.3<br>
Ansible 2.9<br>




