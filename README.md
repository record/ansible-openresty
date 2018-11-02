OpenResty
=========

Role which installs OpenResty for you.

Requirements
------------

Ansible 1.9.

Role Variables
--------------

| Name | Effect | Default | Example |
|---|---|---|---|
| openresty_version | Expected version | `1.13.6.2` ||
| openresty_install_prefix | Install prefix | `/usr/local/openresty` ||
| openresty_build_wipe_first | Wipe build dir or not | `false` ||
| openresty_system_packages | Required System Packages | `['build-essential', 'libpcre3-dev', 'libssl-dev']` ||
| openresty_extra_modules | Extra required modules | `[]` | `['http_stub_status_module', 'ipv6']` |
| openresty_conf_main | Main Config | `{{ role_path }}/templates/nginx.conf.j2` | `{{ playbook_dir }}/templates/nginx.conf.j2` |
| openresty_confs | Site Configs | [] | `[{src: 'tests/test.conf.j2', dest: 'test.conf'}]` |
| openresty_user | Service Account | `www-data` ||
| openresty_pid_file | PID File Location | `/var/run/openresty.pid` ||
| openresty_systemd_unit_file | Systemd Unit File | `{{ role_path }}/templates/openresty.service.j2` ||
