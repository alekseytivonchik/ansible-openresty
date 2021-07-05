# Ansible playbook
### Install OpenResty from repo on Debian/Ubuntu servers, add requared modules.

## How to
Run role "install":
```bash
ansible-playbook play.yaml -i hosts.ini --tags install
```
After successfull install packages, check OpenResty release on destenation server(s):
```bash
ssh [user]@[host] openresty -V
```
```bash
nginx version: openresty/1.19.3.2
```
Befor add custom modules, make shure that installed version on host equail the variable value *nginx_version*. All variables could be change in *play.yaml*:

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
ansible-playbook play.yaml -i hosts.ini --tags download,configure
```