## Prerequisite

- Ansible
- Vagrant
- VirtualBox

## Development

### Initializing a minimal environment

```shell
vagrant up
```

### Deploying a playbook

Run the following command:

```shell
ansible-playbook --inventory inventory/dev --ask-become-pass playbook.yaml
```


## Production

Following playbook deployments:

```shell
ansible-playbook --inventory inventory/prod --ask-become-pass playbook.yaml
```
