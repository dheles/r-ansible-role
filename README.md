Ansible Role: R
=========

Installs the R programming environment

Requirements
------------

none

Role Variables
--------------

    r_debugging:            "{{ debugging | default(false) }}"
    r_version_major:        3
    r_version_minor:        4
    r_version_patch:        1
    r_version:              "{{ r_version_major }}.{{ r_version_minor }}.{{ r_version_patch }}"
    r_dir:                  "R-{{ r_version }}"
    r_download_file:        "{{ r_dir }}.tar.gz"
    r_url:                  "https://cran.r-project.org/src/base/R-{{ r_version_major }}/{{ r_download_file }}"
    r_checksum_algorithm:   "sha256"
    # NOTE: will set this from a stored list, unless a value is passed in
    r_checksum:             ""
    r_user:                 "{{ ansible_user_id }}"
    r_download_dir:         "{{ ansible_user_dir }}"
    r_install_dir:          "/usr/local"
    r_path:                 "{{ r_install_dir }}/bin"
    r_home:                 "{{ r_install_dir }}/lib/R"
    r_configure_args:       "--with-tcltk --enable-R-shlib"

Dependencies
------------

none

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: R }

License
-------

CC0

Author Information
------------------

Drew Heles
