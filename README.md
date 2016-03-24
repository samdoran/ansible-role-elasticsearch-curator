Elasticsearch Curator
=========

Elasticsearch Curator is a tool for mananging indices stored in Elasticsearch. It can close, delete, snapshot, and optimize indices. See the [official documentanion](https://www.elastic.co/guide/en/elasticsearch/client/curator/3.5/index.html) for details.

Requirements
------------

Access to the Elasticsearch database that Curator will manage.

Role Variables
--------------

| Name              | Default Value       | Description          |
|-------------------|---------------------|----------------------|
| `curator_version` | `3` | Major version of `curator` to install. |
| `curator_repo_dir` | `[OS dependent]` | Path where repository file is created. See `vars/(RedHat|Debian).yml` |
| `curator_repo_file` | `[OS dependent` | Name of repository file. See `vars/(RedHat|Debian).yml` |
| `curator_package_list` | `[OS dependent]` | List of packages to install when installing `curator`. See `vars/(RedHat|Debian).yml` |

Dependencies
------------

EPEL repo is needed for RHEL 6 in order to install `python-unittest2`. 

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: elasticsearch
      roles:
         - { role: curator, when: ansible_hostname == groups['es'][0] }

License
-------

MIT
