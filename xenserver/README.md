XenServer Facts Module For Ansible
==================================

Installation Steps
------------------

* Copy the xenserver_facts module to your local ansible/library/
folder and then run the module against your XenServer host

Using xenserver_facts with Ansible
----------------------------------

You can run it as a standalone module as below or use it in
your playbooks for applying xenserver patches, configuring
the dom0_mem limits or even setting up your network labels

Have fun.

```
ansible -m xenserver_facts xenserver_host
vxen1-1.lan | success >> {
    "ansible_facts": {
        "xenserver_facts": {
            "dom0_mem": {
                "max": "512M", 
                "min": "512M"
            }, 
            "host_uuid": "a6259d21-5f4e-4ff8-b6f1-c72da0eeaba7", 
            "hostname": "vxen1-1", 
            "hotfixes": {
                "XS62E001": {
                    "after_apply_guidance": [
                        "restartXAPI"
                    ], 
                    "applied": true, 
                    "name_description": "Public Availability: Xapi fixes", 
                    "uuid": "dedcc0dd-d8f3-4f76-90ca-92697c7a44f0"
                }, 
                "XS62E002": {
                    "after_apply_guidance": [
                        "restartHost"
                    ], 
                    "applied": true, 
                    "name_description": "Public Availability: security fixes to Xen", 
                    "uuid": "59128f15-92cd-4dd9-8fbe-a0115d1b07a2"
                }, 
                "XS62E004": {
                    "after_apply_guidance": [
                        "restartHost"
                    ], 
                    "applied": true, 
                    "name_description": "Public Availability: Fixes for Dom0 kernel issues", 
                    "uuid": "5579f1f0-ff83-11e2-b778-0800200c9a66"
                }, 
                "XS62E005": {
                    "after_apply_guidance": [
                        "restartXAPI"
                    ], 
                    "applied": true, 
                    "name_description": "Public Availability: Toolstack fixes", 
                    "uuid": "aeff92a9-2c60-43eb-b34e-14e4132b411c"
                }, 
                "XS62E009": {
                    "after_apply_guidance": [
                        "restartHost"
                    ], 
                    "applied": true, 
                    "name_description": "Public Availability: security fixes to Xen", 
                    "uuid": "d9c753b9-a15b-4a31-897b-97fdae609031"
                }, 
                "XS62E010": {
                    "after_apply_guidance": [], 
                    "applied": true, 
                    "name_description": "Public Availability: Fix for GPU pass through", 
                    "uuid": "83bca9f6-4ae5-45f9-9426-440216f73797"
                }
            }, 
            "master_uuid": "a6259d21-5f4e-4ff8-b6f1-c72da0eeaba7", 
            "networks": {
                "xapi0": {
                    "name_description": "link local network used by system vms", 
                    "name_label": "cloud_link_local_network", 
                    "uuid": "8fcf41ad-071f-1d77-dd0b-2f63340a16cc"
                }, 
                "xapi1": {
                    "name_description": "", 
                    "name_label": "VLAN-615a80b0-6241-136a-5d7f-03ea1283961f-64", 
                    "uuid": "a694ba20-65f8-45ad-31a4-4ca56e872075"
                }, 
                "xapi2": {
                    "name_description": "", 
                    "name_label": "VLAN-615a80b0-6241-136a-5d7f-03ea1283961f-65", 
                    "uuid": "62e7cd1a-d321-0e11-31db-fe6f5faebcb4"
                }, 
                "xenapi": {
                    "name_description": "Network on which guests will be assigned a private link-local IP address which can be used to talk XenAPI", 
                    "name_label": "Host internal management network", 
                    "uuid": "3de3a508-f929-210e-620d-ed32fa6e17a0"
                }, 
                "xenbr0": {
                    "name_description": "Management Network", 
                    "name_label": "MGMT", 
                    "uuid": "615a80b0-6241-136a-5d7f-03ea1283961f"
                }
            }, 
            "pifs": {
                "eth0": {
                    "gateway": "", 
                    "ip": "192.168.44.24", 
                    "netmask": "255.255.255.0", 
                    "uuid": "1ecf12a3-c542-9503-cb33-b66f9889fe30"
                }
            }
        }
    }, 
    "changed": false
}
```
