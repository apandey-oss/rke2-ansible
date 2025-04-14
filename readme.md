# Ansible playbooks to create multinode rke2 cluster

### generate random seed and run install playbook

```
export RANDOM_KEY=$(openssl rand -hex 32)

ansible-playbook -i hosts.ini \
  -e RKE_RANCHER_BOOTSTRAP_SECRET=${RANDOM_KEY} \
  -e RKE_TOKEN=${RANDOM_KEY} \
  playbooks/install.yaml 
```