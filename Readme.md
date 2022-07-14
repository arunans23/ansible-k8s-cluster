## _Ansible playbook to create a 3 node K8s cluster_

#### Tested environment

* Three Ubuntu 20.04 Machines connected in the network.
* Ansible installed on a M1 mac and which should be able to connect with the above three machines.
* Versions
    - Ansible : 2.13.1
    - Ubuntu : 20.04
    - Kubelet : 1.16.0 (Installed from playbook itself)
    - Kubectl : 1.16.0 (Installed from playbook itself)
    - Kubeadm : 1.16.0 (Installed from playbook itself)

#### Steps

1. Replace <master-ip>, <worker-1-ip>, <worker-2-ip> with relevant IP addresses.
2. Run the following playbooks in order.
    ```sh
    ansible-playbook -i hosts initial.yaml
    ansible-playbook -i hosts kube-dependencies.yaml
    ansible-playbook -i hosts master.yaml
    ansible-playbook -i hosts workers.yaml
    ```
