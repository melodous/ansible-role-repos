Welcome to repos Ansible Role’s documentation!
==============================================

REPOS
-----

Role to add yum repos to the systems. It also can configure the epel
repository on the system.

You can configure var yum\_common\_repos on a common var file and
yum\_repos for each layer var file

### Requirements

N/A

### Dependencies

N/A

### Example Playbook

    - hosts: servers
      roles:
        - { role: repos }

yum repos ansible role default variables
----------------------------------------

#### Sections

-   yum repos management
-   epel repo management

### yum repos management

`yum_common_repos`

> Yum common repos dict, add yum repositories to the system normally
> this var is defined as global for every layer for example on file
> group\_vars/all.

    yum_common_repos: false


     Example:

    yum_common_repos:
      - name: rhel7
        baseurl: 'http://repos/redhat/rhel6.5s-x86_64/RPMS.os'
        desc: 'RedHat7 Repository'

`yum_repos`

> yum repos dict, add yum repositories to the system normally this var
> is defined per layer to add repos that aren’t need by all the project
> components.

    yum_repos: false


     Example:

    yum_repos:
      - name: MyApp
        baseurl: 'http://repos/redhat/rhel6.5s-x86_64/myApp'
        desc: 'MyApp Repository'

### epel repo management

`repo_epel`

> Enable or disable epel yum repo on the system (bool)

    repo_epel: true

`epel_repo_url`

> Epel yum repository url
>
>     epel_repo_url: "https://dl.fedoraproject.org/pub/epel/epel-release-latest-{{ ansible_distribution_major_version }}.noarch.rpm"

`epel_repo_gpg_key_url`

> Gpg key url for epel repository
>
>     epel_repo_gpg_key_url: "/etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-{{ ansible_distribution_major_version }}"

`epel_repofile_path`

> Epel repository configuration file
>
>     epel_repofile_path: "/etc/yum.repos.d/epel.repo"

Changelog
---------

**repos**

This project adheres to Semantic Versioning and human-readable
changelog.

### repos master - unreleased

##### Added

-   First addition

##### Changed

-   First change

### repos v0.0.1 - 2017/07/12

##### Added

-   Added initial version
-   Added documentation
-   Added tests

Copyright
---------

repos

Copyright (C) 2017/07/12 Raul Melo
&lt;<raul.melo@opensolutions.cloud>&gt;

LICENSE
