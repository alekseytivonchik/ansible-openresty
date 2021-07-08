# Install OpenResty & Filebeat via Ansible
## Installation
### OpenResty
```bash
ansible-playbook resty-source.yaml -i hosts.ini --ask-become-pass
```
### Filebeat
```bash
ansible-playbook fb.yaml -i hosts.ini --ask-become-pass
```
### All
```bash
ansible-playbook play.yaml -i hosts.ini --ask-become-pass
```
## Configuration
### OpenResty
All variables could be customize in *proxy-bootstrap\ansible\roles\openresty-source\defaults\main.yaml*
### Filebeat
All variables could be customize in *proxy-bootstrap\ansible\roles\filebeat\defaults\main.yml*

Config file *proxy-bootstrap\ansible\roles\filebeat\templates\filebeat.yml* isn't template and don't include variables from *defaults\main.yml*