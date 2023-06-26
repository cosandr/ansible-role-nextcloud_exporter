# ansible-role-nextcloud_exporter

![GitHub](https://img.shields.io/github/license/cosandr/ansible-role-nextcloud_exporter) ![GitHub last commit](https://img.shields.io/github/last-commit/cosandr/ansible-role-nextcloud_exporter) ![GitHub issues](https://img.shields.io/github/issues-raw/cosandr/ansible-role-nextcloud_exporter)

**Ansible role for setting up nextcloud_exporter.**

## Supported Platforms

| OS Family | Distribution  | Latest | Supported Version(s) | Comment |
|-----------|---------------|--------|----------------------|---------|
| RedHat    | RHEL          | :heavy_check_mark: | 9 | |
|           | RockyLinux    | :heavy_check_mark: | 8, 9 | |
|           | AlmaLinux     | :heavy_check_mark: | 8, 9 | |
|           | Fedora        | :heavy_check_mark: | 36, 37, 38 | |

Probably works fine on Debian based distros.

## Requirements

Ansible 2.12 or higher, `bzip2` on Ansible controller.

## Variables

See [upstream docs](https://github.com/xperimental/nextcloud-exporter#configuration-file).

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `nextcloud_exporter_version` | latest | Can be set to a specific tag |
| `nextcloud_exporter_server` |  | Required, URL of nextcloud instance |
| `nextcloud_exporter_auth_token` |  | Required if not using user/pass, takes precedence over them |
| `nextcloud_exporter_username` |  | Required if token is missing |
| `nextcloud_exporter_password` |  | Required if token is missing |
| `nextcloud_exporter_listen_address` | :9205 | Listen address and port |
| `nextcloud_exporter_timeout` | 5s |  |
| `nextcloud_exporter_tls_skip_verify` | false | Don't verify server certificates |


## Dependencies

None.

## Example Playbook

```yaml
---

- hosts: all
  become: true
  gather_facts: true
  roles:
    - role: ansible-role-nextcloud_exporter
```

## Author

[Andrei Costescu](https://github.com/cosandr/)
