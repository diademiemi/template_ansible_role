Ansible Role Template
=========

This is a template for Ansible roles in my style.  

Some more information.  


Requirements
------------
These platforms are supported:
- Ubuntu 20.04
- Ubuntu 22.04
- Debian 10
- Debian 11
- CentOS Stream/RHEL 8
- CentOS Stream/RHEL 9

<!-- 
- List hardware requirements here  
-->

Role Variables
--------------

Variable | Default | Description
--- | --- | ---
<!--
`variable` | `default` | Variable example
`long_variable` | See [defaults/main.yml](./defaults/main.yml) | Variable referring to defaults
`distro_specific_variable` | See [vars/debian.yml](./vars/debian.yml) | Variable referring to distro-specific variables
-->

Dependencies
------------

None

Example Playbook
----------------

```yaml
- name: Use template role
  hosts: "{{ target | default('template') }}"
  roles:
    - diademiemi.template
```

Role Structure
--------------

Roles have an entrypoint `main.yml` which includes other files.  
It searches for files in `vars/`, `tasks/assert/` and `tasks/setup` for files named like the host platform. If no file is found, it falls back to `default.yml`.  

This is an easy way to provide distro-specific variables, assertions and tasks and allows me to keep the role structure clean.  


Role Testing
------------

This repository comes with Molecule tests for Docker on the supported platforms.
Install Molecule by running
```bash
pip3 install -r requirements.txt
```

Run the tests with
```bash
molecule test
```

License
-------

MIT

Author Information
------------------

- diademiemi (@diademiemi)