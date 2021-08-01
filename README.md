Ansible role for Request Tracker v5+
================================

This Ansible role installs Best Practical's Request Tracker (RT). It optionally installs certain RT extensions.

https://bestpractical.com/  
https://github.com/bestpractical/rt

Requirements
------------

RT depends on many Perl modules, Apache with either mod_perl or mod_fcgid, and PostgreSQL or MySQL.

RT prefers mod_fcgid and MySQL.

This role assumes Enterprise Linux 8 with SELinux **enabled.**

Role Variables
--------------

Check [defaults/main.yml](defaults/main.yml).

- Use `rt_version` to select the RT version to install. See [vars/rt_versions.yml](vars/rt_versions.yml) for supported versions.
- Use `cpanm_notest` to enable or disable running tests after building Perl modules.

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: bcduggan.rt
           rt_version: rt-4.2.12
           rt_hostname: <domain or server IP>
           selinux: true
           cpanm_notest: false
           perlbrew_notest: false
           mysql_root_password: root

License
-------

GPLv3


Author Information
------------------

Neil Hanlon
Brian Duggan
