# ocp-nutanix-prerequisites
Ansible roles and playbooks to check prerequisites for an IPI Openshift installation on Nutanix

----

## How to use

Run the playbook on the machine that will proceed the IPI installation on your Nutanix cluster.

1. Provide your credentials and some environment variables. Use the same credentials as for the Openshift installation

```text
ansible-vault create secret.yml
--------------------------------------
nutanix_central_host: ****.example.com
nutanix_element_host: ****.example.com
nutanix_cluster: example-cluster
nutanix_username: ****
nutanix_password: ****
ocp_base_domain: ****.example.com
ocp_cluster_name: example-ocp
```

2. Run the playbook

`ansible-playbook ipi-prerequisites.yml --ask-vault-pass`

If every prerequisite is satisfied, you should see that all tasks are either `ok` or `skipped` :

```text
PLAY RECAP ***********************************************************************************************************************************************
localhost                  : ok=10   changed=0    unreachable=0    failed=0    skipped=3    rescued=0    ignored=0
```