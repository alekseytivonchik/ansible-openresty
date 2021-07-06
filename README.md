# Ansible Roles: OpenResty & Filebeat

## Recommends
```yaml
ansible: 2.9.14
```
## Usage
### Openresty
---
Run role "openresty-repo":
```bash
ansible-playbook play.yaml -i inventory/hosts.ini --tags openresty-repo
```
After successfull install packages, check OpenResty release on destenation server(s):
```bash
ssh [user]@[host] openresty -V
```
```bash
nginx version: openresty/1.19.3.2
```
Befor add custom modules, make shure that installed version on host equail the variable value *nginx_version*. OpenResty variables could be change in *inventory/host_vars/main.yaml*:

```yaml
nginx_version: openresty-1.19.3.2
```
```yaml
nginx_version: openresty-x.x.x.x
```

List of modules available in *play.yaml*:
```yaml
nginx_custom_modules: "-j2 ..."
```

Run add modules roles:
```bash
ansible-playbook play.yaml -i inventory/hosts.ini --tags openresty-modules
```

### Filebeat
---
Run role "filebeat":
```bash
ansible-playbook play.yaml -i inventory/hosts.ini --tags filebeat
```
#### Customize:

Filebeat's variables in *roles/filebeat/defaults/main.yml.*

Filebeat's configs in *roles/filebeat/templates/filebeat.yml.j2*