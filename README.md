# Ansible netconfig role

This is an [Ansible](http://www.ansible.com) role to setup /etc/netconfig file.

The file defines a list of "transport names" describing their semantics and protocol.

This file is only used by the RPC library code.

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

## Usage

This is an example playbook:

```yaml
---

- hosts: all
  roles:
    - role: amtega.netconfig
      vars:
        netconfig_settings:
          - network_id: "udp"
            semantics: "tpi_clts"
            flags: "v"
            protofamily: "inet"
            protoname: "udp"
            device: "-"
            libraries: "-"
          - network_id: "tcp"
            semantics: "tpi_cots_ord"
            flags: "v"
            protofamily: "inet"
            protoname: "tcp"
            device: "-"
            libraries: "-"  
```

## Testing

Tests are based on docker containers. You can setup docker engine quickly using the playbook `files/setup.yml` available in the role [amtega.docker_engine](https://galaxy.ansible.com/amtega/docker_engine).

Once you have docker, you can run the tests with the following commands:

```shell
$ cd amtega.netconfig/tests
$ ansible-playbook main.yml
```

## License

Copyright (C) 2019 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- José Enrique Mourón Regueira
