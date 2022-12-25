# SETUP mongodb on kubernetes

# setup the inventory file

Steps: 
1. first install the aws cli
2. configure credentials in the default profile
3. Use this below code as inventory file

```yaml
plugin: aws_ec2
regions:
  - us-east-1
filters:
  # All instances with their state as `running`
  instance-state-name: running
keyed_groups:
  - key: tags
    prefix: tag
hostnames:
  - ip-address
```

# Install kubernetes and mongodb in it
now run the below commands

```bash
ansible-playbook main.yaml
ansible-playbook configure.yaml
```
