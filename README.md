# Ansible Role: ForgeRock Amster

[![Build Status](https://travis-ci.com/darkedges/ansible-role-forgerock-amster.svg?branch=master)](https://travis-ci.com/darkedges/ansible-role-forgerock-amster)

This Ansible Role helps with the installation of ForgeRock Amster.

## Configuration

The following values are used as part of the configuration

### Common

| Variable                        | Default Value                                            | Type     | Possible Values | Description |
| ------------------------------- | -------------------------------------------------------- | -------- | --------------- | ----------- |
| `amster_install_path`           | `/opt/ois`                                               | `string` |                 |             |
| `staging_dir`                   | `/tmp/staging`                                           | `string` |                 |             |
| `fr_user`                       | `forgerock`                                              | `string` |                 |             |
| `fr_group`                      | `forgerock`                                              | `string` |                 |             |
| `amster_version`                | `6.5.0`                                                  | `string` |                 |             |
| `amster_install_file`           | `Amster-{{ amster_version }}.zip`                        | `string` |                 |             |
| `amster_install_directory_name` | `amster`                                                 | `string` |                 |             |
| `amster_install_directory_base` | `{{ install_root }}/{{ amster_install_directory_name }}` | `string` |                 |             |

## Examples

**Note:** There is an assumption in these examples that a JDK has been deployed suitable for the product.

For example

```bash
- hosts: frds
  roles:
    - role: geerlingguy.java
      java_packages:
        - java-1.8.0-openjdk-headless
```

### Default Amster

This use default values

| installation path | user        | group       |
| ----------------- | ----------- | ----------- |
| `/opt/ois/amster` | `forgerock` | `forgerock` |

```bash
- hosts: frds
  roles:
    - role: forgerock.user
    - role: forgerock.amster
```

### Default Amster

This use default values

| installation path       | user        | group       |
| ----------------------- | ----------- | ----------- |
| `/opt/forgerock/amster` | `forgerock` | `forgerock` |

```bash
- hosts: frds
  roles:
    - role: forgerock.user
    - role: forgerock.amster
      amster_install_path: "/opt/forgerock"
```

## License

Copyright © 2019 [DarkEdges](https://bitbucket.org/darkedges).
This project is [Apache License Version 2.0](https://github.com/darkedges/ansible-role-forgerock-amster/blob/master/LICENSE) licensed.
