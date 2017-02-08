
ansible-role-r
=========

An Ansible role to install and manage R installations.


Requirements
------------

* **The apt_repository** Ansible module **filename** option requires Ansible 2.1 or greater. See [ apt_repository module]( http://docs.ansible.com/ansible/apt_repository_module.html#examples ).

Role Variables
--------------

### roles/r/defaults/main.yml

Currently **r_state** is the only variable used. Others may be used when requested.

```yaml
---
# file: roles/r/defaults/main.yml
#
#

# r installation state
#
r_state         : present     # absent, present

# Ubuntu r packages
#
# (var not used at this time)
r_ubuntu_16.04_packages:

  - r-cran-boot
  - r-cran-class
  - r-cran-cluster
  - r-cran-codetools
  - r-cran-foreign
  - r-cran-kernsmooth
  - r-cran-lattice
  - r-cran-mass
  - r-cran-matrix
  - r-cran-mgcv
  - r-cran-nlme
  - r-cran-nnet
  - r-cran-rpart
  - r-cran-spatial
  - r-cran-survival

# apt key info
#
#r_keyserver_url    : hkp://keyserver.ubuntu.com:80
#r_key_id           : E084DAB9
#r_cran_mirror      : 'http://cran.utstat.utoronto.ca/'  # University of Toronto
#r_ubuntu_backports : 'deb http://ubuntu.mirror.iweb.ca/ xenial-backports main restricted universe'

# References
#
## Canadian cran mirrors
#
# http://cran.stat.sfu.ca/ 	Simon Fraser University, Burnaby
# https://muug.ca/mirror/cran/ 	Manitoba Unix User Group
# http://muug.ca/mirror/cran/ 	Manitoba Unix User Group
# http://mirror.its.dal.ca/cran/ 	Dalhousie University, Halifax
# http://cran.utstat.utoronto.ca/ 	University of Toronto 

## Backports
#
# Installation and compilation of R or some of its packages may require Ubuntu packages from the "backports" repositories. Therefore, it is suggested to activate the backports repositories with an entry like 

#    deb https://<my.favorite.ubuntu.mirror>/ trusty-backports main restricted universe
#
#    deb http://ubuntu.mirror.iweb.ca/ xenial-backports main restricted universe
#    deb-src http://ubuntu.mirror.iweb.ca/ xenial-backports main restricted universe
```

Dependencies
------------

None.

Example Playbook
----------------

### project/r.yml

An example can be copied from the `roles/r/files/r.yml` file:

```shell
cp roles/r/files/r.yml .
```

### Content example

    ---
    - hosts: r
      become: true
      gather_facts: false
      roles:
        - r

## ansible-playbook command example

```shell
ansible-playbook -i inventory/dev systems.yml
```



License
-------

2017 MIT 


Author Information
------------------

Christopher dot Steel AT McGill dot ca
