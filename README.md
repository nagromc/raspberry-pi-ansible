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
ansible-playbook --inventory inventory/dev playbook.yaml
```


## Production

Following playbook deployments:

```shell
ansible-playbook --inventory inventory/prod playbook.yaml
```
