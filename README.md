Azure-Secrets
=========

This role will fetch a set of secrets from an Azure Keyvault and populate a "populatedSecrets" dictionary with those values. 



Role Variables
--------------

The "secrets" array contains the list of secrets you want to fetch from Azure Keyvault. 

```
client_id: "your-sp-app-id"
client_secret: "your-sp-password"
vaultURL: "your-vault-url.vault.azure.net"
secrets:
  - list
  - of
  - secrets
  - you
  - want
```


Example Playbook
----------------

```
---
- hosts: localhost
  gather_facts: no
  vars:
    client_id: "ID"
    client_secret: "SECRET"
    vaultURL: "latis-camino.vault.azure.net"
    secrets:
    - "db-dev"
  tasks:
  - name: Output the secret
    debug: 
      msg="{{ populatedSecrets['db-dev'] }}"
  roles:
    - azure-secrets
```


License
-------

BSD
