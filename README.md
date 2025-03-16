## Prerequisite

- Ansible
- Vagrant
- VirtualBox
- sshpass
  - `brew install hudochenkov/sshpass/sshpass` on macOS

## Development

### Initializing a minimal environment

```shell
vagrant up
```

### Deploying a playbook

First playbook deployment:

```shell
ansible-playbook --inventory inventory/dev --extra-vars "@init-overrides.json" playbook-init.yaml
```

Following playbook deployments:

```shell
ansible-playbook --inventory inventory/dev --ask-become-pass playbook.yaml
```


## Production

### Initializing a minimal environment

Copy the content of the `bootfs/` directory to the Raspberry Pi's first partition named `bootfs`:

```shell
cp bootfs/* /Volumes/bootfs/
```


### Deploying a playbook

First playbook deployment:

```shell
ansible-playbook --inventory inventory/prod --extra-vars "@init-overrides.json" playbook-init.yaml
```

Following playbook deployments:

```shell
ansible-playbook --inventory inventory/prod --ask-become-pass playbook.yaml
```
