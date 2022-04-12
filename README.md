# Ansible vault transit migrator

This code can be used to export transit keys from one HashiCorp Vault and import to another HashiCorp Vault.

![Overview of this tool](/images/migrator.png)

1: The migrator will read all keys from the specified transit mount point.
2: The results are saved in the `data` directory.
3: The migrator will write all keys in `data` to the specified transit mount point.

## Limitations

- The secrets engine should exist on the target ("Vault B").
- The keys are stored locally on disk, please ensure to cleanup these files.
- Keys are made un-exportable, no matter what state they were in.
- No FQCN's are used.

## Setup

In the `export.yml` and `import.yml` two plays are listed. One to export, another to import.

Change these values for **both** plays.

```yaml
VAULT_ADDR: "http://127.0.0.1:8200"
VAULT_TOKEN: "abc123"
```

## Running

### Exporting

Simply run:

```shell
ansible-playbook export.yml
```

### Importing

Simply run:

```shell
ansible-playbook import.yml
```

## Cleanup

After exporting and importing, please make sure to remove all files in `data/*`.
