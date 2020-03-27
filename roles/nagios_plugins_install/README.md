# Ansible Role: NRPE Client


This role installs the NRPE client on a monitoring server. You can use this role as an addon to the `networklore/nagios`role.


# Requirements

nagios / nrpe installed


# Role Variables

The variables you can configure are listed below. For the default settings you can look in `defaults/main.yml`.

This is the directory where the downloaded files will be placed and extracted.

    dest_path: "/tmp"

# require the distributions Nagios package to be installed.

pluginstarball: nagios-plugins-2.2.1.tar.gz
pluginssrc: nagios-plugins-2.2.1

# Location of monitoring plugins

plugins_dir: /usr/local/nagios/libexec


The download url for NRPE along with the directory name which will be created when the source file is
decompressed to. I.e. with `tar -xzvf nrpe-3.2.1.tar.gz`

    plugins_dir: /usr/local/nagios/libexec

The location of where you want to place the check_nrpe file, usually where your other monitoring plugins are located.

# Dependencies
    - gcc
    - glibc
    - glibc-common
    - make
    - openssl-devel

This role doesn't have any strict dependencies

# Example Playbook

Install NRPE to your current monitoring plugin directory.

    - hosts: monitoring-servers
      vars_files:
       - vars/main.yml    
      roles:
         - { role: nagios_plugins_install }

*Contents of vars/main.yml*:

    plugins_dir: /usr/local/nagios/plugins

License
-------

BSD

Author Information
------------------

Ahmed Shamsan - EIT Linux and App Support
