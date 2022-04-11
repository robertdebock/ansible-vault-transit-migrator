# Ansible vault transit migrator

This code can be used to export transit keys from one HashiCorp Vault and import to another HashiCorp Vault.

## Setup

In the `playbook.yml`, two plays are listed. One to export, another to import.

Change these values for **both** plays.

```yaml
VAULT_ADDR: "http://127.0.0.1:8200"
VAULT_TOKEN: "abc123"
```

## Running

Simply run:

```shell
ansible-playbook playbook.yml
```

## Cleanup

After exporting and importing, please make sure to remove all files in `export/*` and `import/*`.
