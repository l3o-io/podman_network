podman_network
==============

Creates or deletes podman CNI networks using **podman-plugins** (dnsname).

Please note that this role installs **podman-plugins** from my [home project](https://build.opensuse.org/package/show/home:cfelder:CentOS-8/podman-plugins) on EL8 systems.

Role Variables
--------------

| Variable                        | Value                       |
| ------------------------------- | --------------------------- |
| ``podman_network_name``         | CNI network name            |
| ``podman_network_state``        | ``present`` or ``absent``   |
| ``skip_podman_plugins_install`` | ``yes`` or ``no`` (default) |

Example Playbook
----------------

The following playbook installs the dnsname plugin package (**podman-plugins**) and creates a new CNI network named ``dnsname0``:

    - name: Create new podman network
      hosts: all
      tasks:
        - include_role:
            name: podman_network
          vars:
            podman_network_name: 'dnsname0'
            podman_network_state: 'present'

License
-------

GPLv3+

Author Information
------------------

Christian Felder
