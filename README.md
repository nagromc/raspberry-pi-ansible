## Prerequisite

- Ansible
- Vagrant
- VirtualBox
- sshpass
  - `brew install hudochenkov/sshpass/sshpass` on macOS

## Development

### Initializing a minimal environment

```shell
$ vagrant up
```

### Deploying a playbook

First playbook deployment:

```
$ ansible-playbook --inventory inventory/dev --extra-vars "@vars-init.json" playbook-init.yaml
```

Following playbook deployments:

```
$ ansible-playbook --inventory inventory/dev --ask-become-pass playbook.yaml
```


## Production

### Initializing a minimal environment

Copy the content of the `bootfs/` directory to the Raspberry Pi's first partition named `bootfs`:

```
$ cp bootfs/* /Volumes/boot/
```


### Deploying a playbook

First playbook deployment:

```
$ ansible-playbook --inventory inventory/prod --extra-vars "@vars-init.json" playbook-init.yaml
```

Following playbook deployments:

```
$ ansible-playbook --inventory inventory/prod --ask-become-pass playbook.yaml
```
