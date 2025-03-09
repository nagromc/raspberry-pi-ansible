## Prerequisite

- Ansible
- Vagrant
- VirtualBox
- sshpass
  - `brew install hudochenkov/sshpass/sshpass` on macOS

## Development

### Initializing a minimal environment

1. Add `raspi-vbox.local` to your `/etc/ansible/hosts` file.
2. Run `vagrant up`

### Deploying a playbook

First playbook deployment:

```
$ ansible-playbook --inventory dev-inventory --extra-vars "@vars-init.json" playbook-init.yaml
```

Following playbook deployments:

```
$ ansible-playbook --inventory dev-inventory --ask-become-pass playbook.yaml
```


## Production

### Initializing a minimal environment

Create an empty `ssh` file

```
$ touch /Volumes/boot/ssh
```


### Deploying a playbook

First playbook deployment:

```
$ ansible-playbook --inventory prod-inventory --extra-vars "@vars-init.json" playbook-init.yaml
```

Following playbook deployments:

```
$ ansible-playbook --inventory prod-inventory --ask-become-pass playbook.yaml
```
