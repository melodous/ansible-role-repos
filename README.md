=== Common Repos Module ===

Role to add yum repos to the systems.

You can configure var yum_common_repos on a common var file and yum_repos for each layer var file, example configuration  for nginx layer:


content group_vars/all file

```
yum_common_repos:
  - name: rhel6
    baseurl: 'http://repos.hi.inet/redhat/rhel6.5s-x86_64/RPMS.os'
    desc: 'RHEL6 Repository'
  - name: rhel6-updates
    baseurl: 'http://repos.hi.inet/redhat/rhel6s-x86_64/RPMS.updates'
    desc: 'RHEL6 Updates Repository'
```


content group_vars/nginx file

```
yum_repos:
  - name: Nginx
    baseurl: 'http://artifactory.hi.inet/artifactory/yum-nginx/6/x86_64/'
    desc: 'Nginx Repository'
```
# ansible-role-repos
