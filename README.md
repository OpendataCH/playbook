# Opendata.ch Ansible Playbook

## Usage

Most changes can be made in the file `vars.yml`. Commit and push your changes 
to [GitHub](https://github.com/OpendataCH/playbook) 
and [GitHub Actions](https://github.com/OpendataCH/playbook/actions) will execute the 
following command which applies the changes to the server:

```
ansible-playbook site.yml
```

### Deleting a DNS record

Note that DNS records are only added or updated with the playbook. If you want 
to delete a DNS record, you have to manually do so. This also applies when 
changing the type of a DNS record as that's basically a delete and create.

You can find the `CLOUDFLARE_API_TOKEN` in the Vault.

Fetch records:

```
curl "https://api.cloudflare.com/client/v4/zones/c70c67baa5ba6666d60303664a926522/dns_records?per_page=100" \
     -H 'X-Auth-Email: hannes@opendata.ch' \
     -H 'X-Auth-Key: CLOUDFLARE_API_TOKEN' \
```

Delete record:

```
curl -X "DELETE" "https://api.cloudflare.com/client/v4/zones/c70c67baa5ba6666d60303664a926522/dns_records/DNS_RECORD_ID" \
     -H 'X-Auth-Email: hannes@opendata.ch' \
     -H 'X-Auth-Key: CLOUDFLARE_API_TOKEN' \
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
