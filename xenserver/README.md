XenServer Facts Module For Ansible
==================================

WARNING: Not well tested.

Installation Steps
------------------

* Copy the facts to ansible/library

```
$ ansible -i hosts -m xenserver_facts vxen2-1.local
vxen2-1.local | success >> {
    "ansible_facts": {
        "ansible_xen_host_uuid": "5cf1856d-bdc4-4b45-8014-e253b64af0d3", 
        "ansible_xen_hostname": "vxen2-1.local", 
        "ansible_xen_hotfixes": {
            "XS62E001": true, 
            "XS62E002": true, 
            "XS62E004": true, 
            "XS62E005": true
        }, 
        "ansible_xen_master_uuid": "5cf1856d-bdc4-4b45-8014-e253b64af0d3"
    }
}
```
