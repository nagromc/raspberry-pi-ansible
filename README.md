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

### Secrets file

- Create a file containing the required secrets changing the desired values:

    ```shell
    echo 'smb_user: the_user\nsmb_password: the_password' > secrets
    ```

- Create a file containting the encryption key:

    ```shell
    echo 'superSecretVaultPassword' > vault-password
    ```

- Encrypt the file:

    ```shell
    ansible-vault encrypt --vault-password-file vault-password secrets
    ```

### Deployment

```shell
ansible-playbook --inventory inventory/prod --extra-vars @secrets --vault-password-file vault-password playbook.yaml
```
