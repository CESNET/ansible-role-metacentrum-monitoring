metacentrum_monitoring
======================

Role for setting up monitoring by MetaCentrum's Nagios.

Adds MetaCentrum repository, installs needed packages, modifies ssh demon to use DNS.

Requirements
------------

--

Role Variables
--------------

- check_mk_packages - list of packages to install
- check_mk_local_scripts_file - list of files to copy to /usr/lib/check_mk_agent/local/
- check_mk_local_scripts_by_template - list of templates for files in /usr/lib/check_mk_agent/local/  
- check_mk_plugins_file - list of files to copy to /usr/lib/check_mk_agent/plugins/
- check_mk_plugins_by_template - list of templates for files in /usr/lib/check_mk_agent/plugins/

Dependencies
------------

--

Example Playbook
----------------

    - hosts: all
      roles:
         - cesnet.metacentrum_monitoring

