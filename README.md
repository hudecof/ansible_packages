# Packages

Basic setup of the distribution specific package repositories.

## Requirements

- ansible: 2.1


## Role Variables

Role variables are **global** for any distribution or **distribution based**. See the default values in `defaults/main.yml`

### Global variables

- `packages_proxy`: proxy server for getting packages
- `packages_proxy_username`: proxy server username for getting packages
- `packages_proxy_password`: proxy server password for getting packages

### Debian variables
The `/etc/apt/sources.list` file is removed and the `/etc/apt/sources.list.d/debian.list` is created. Debian packages are served from

- deb.debian.org
- archive.debian.org

The file is generated based on these variables:

- `packages_debian_security`: enable debian secutity updates
- `packages_debian_backports`: enable debian backports
- `packages_debian_updates`: enable debian proposal updates


### Ubuntu variables
The `/etc/apt/sources.list` file is removed and the `/etc/apt/sources.list.d/ubuntu.list` is created. Ubuntu packages are served from

Ubuntu packages are serverd from

- archive.ubuntu.com

The file is generated based on these variables:

- `packages_ubuntu_multiverse`: enable ubuntu multiverse
- `packages_ubuntu_universe`: enable ubuntu universe
- `packages_ubuntu_backports`: enable ubuntu backports for main, restricted, multiverse, multiverse
- `packages_ubuntu_security`:enable secutiry updates for main, restricted, multiverse, multiverse
- `packages_ubuntu_updates` enable ubuntu updates for main, restricted, multiverse, multiverse
- `packages_ubuntu_proposed`: enable ubuntu proposal updates for main, restricted, multiverse, multiverse

### CentOS variables
For CentOS it role do not change the repositories, so the **mirrorlist** should be used.

- `packages_centos_epel`: enable epel repository


## Dependencies

There are no external dependencies on any other role.

Example Playbook
-------------------------


    - hosts: all
      roles:
        - role: hudecof.packages

License
-------

BSD

Author Information
------------------

Peter Hudec
CNC, a.s.
Slovakia
