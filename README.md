# Ansible Roles: OpenResty & Filebeat

## Recommends
```yaml
ansible: 2.9.14
```
## Installation
### Openresty install from source
Run *resty-source.yaml* 
```bash
ansible-playbook resty-source.yaml -i hosts.ini
```
OpenResty variables could be change in *roles/openresty-source/defaults/main.yaml*

### Openresty install from repo
Run role "openresty-repo":
```bash
ansible-playbook play.yaml -i hosts.ini --tags resty-repo-install
```
List of modules available in *roles/openresty-source/defaults/main.yaml*:
```yaml
nginx_custom_modules: "-j2 ..."
```
### Filebeat
---
Run role "filebeat":
```bash
ansible-playbook play.yaml -i inventory/hosts.ini --tags filebeat-install
```
#### Customize:
Filebeat's variables in *roles/filebeat/defaults/main.yml.*

Filebeat's config in *roles/filebeat/templates/filebeat.yml.j2*