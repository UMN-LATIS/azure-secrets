Azure-Secrets
=========

This role will fetch a set of secrets from an Azure Keyvault and populate a "populatedSecrets" dictionary with those values. 



Role Variables
--------------

The "secrets" array contains the list of secrets you want to fetch from Azure Keyvault. 

```
azure_sp_client_id: "your-sp-app-id"
azure_sp_client_secret: "your-sp-password"
azure_akv_vault_url: "your-vault-url.vault.azure.net"
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
    azure_sp_client_id: "ID"
    azure_sp_client_secret: "SECRET"
    azure_akv_vault_url: "latis-camino.vault.azure.net"
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
