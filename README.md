Ansible Role to Install GNS3 Server
=========

Ansible role to install GNS3 Server.

Role Variables
--------------

Variables are defined in `defaults/main.yml` and structured/encapsulated in `vars/`.

| Name              | Default Value       | Description          |
|-------------------|---------------------|----------------------|
| `autorun` | `False`  | Boolean to define if the role "autorun" (`tasks/main.yml`). Useful when you want to have dependencies solved by galaxy (`meta/main.yml`) but don't want it to run automatically.  |
| `gns3_server_user` | `gns3`  | The system account to run GNS3 Server service. |
| `gns3_server_group` | `gns3` | The group to run GNS3 Server service. |
| `gns3_server_host` | `0.0.0.0` | The address to listen for connections. |
| `gns3_server_port` | `3080` | The port to listen for connections. |
| `gns3_server_home` | `/opt/gns3` | The base path for the service (homedir) |
| `gns3_server_images_path` | `{{ gns3_server_home }}/images` | The path to store images. |
| `gns3_server_projects_path` | `{{ gns3_server_home }}/projects` | The path to store projects. |
| `gns3_server_appliances_path` | `{{ gns3_server_home }}/appliances` | The path to store appliances. |
| `gns3_server_configs_path` | `{{ gns3_server_home }}/configs` | The path to store configs. |
| `gns3_server_report_errors` | `True` | Boolean to define if service shall report errors. |
| `gns3_server_qemu_enable_kvm` | `True` | Boolean to define if kvm shall be used when running instances. |
| `gns3_server_qemu_require_kvm` | `True` | Boolean to define if kvm is required by the service. |


Examples
------------

Follow below different examples and ways to use this role.

>Playbook: Install GNS3 Server with default options.

```YAML
---
- name: "GNS3: Install GNS3"
  hosts: network_lab
  gather_facts: true
  become: true

  roles:
    - role: victorock.gns3-server
      autorun: true

```

>Playbook: Install GNS3 Server using different home.

```YAML
---
- name: "GNS3: Install GNS3"
  hosts: network_lab
  gather_facts: true
  become: true

  vars:
    gns3_server_home: "/home/gns3"

  roles:
    - role: victorock.gns3-server
      autorun: true

```


License
------------

GPLv3

Author
------------

Victor da Costa (@victorock)
