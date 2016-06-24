# Opendata.ch Ansible Playbook

## Installation

```
pip install ansible
```

You also need a file with the name `vault_password.txt` in the root directory 
of the project. Ask me for the file.

## Usage

```
ansible-playbook site.yml
```

## Migration

```
ansible-playbook migrate-opendata-ch.yml
ansible-playbook migrate-transport.yml
```

## Vault

To access the Vault a file with the name `vault_password.txt` needs to exist in 
the root directory of the project. Ask me for the file.

```
ansible-vault edit group_vars/webservers/vault.yml
```
