# Opendata.ch Ansible Playbook

## Usage

Most changes can be made in the file `vars.yml`. Commit and push your changes 
to [GitHub](https://github.com/OpendataCH/playbook) 
and [GitHub Actions](https://github.com/OpendataCH/playbook/actions) will execute the 
following command which applies the changes to the server:

```
ansible-playbook site.yml
```

## Vault

To access the Vault a file with the name `vault_password.txt` needs to exist in 
the root directory of the project. Ask me for the file.

```
ansible-vault edit vault.yml
```

## Installation

Only needed if you want to run Ansible locally to debug something.

```
pip install ansible
```
