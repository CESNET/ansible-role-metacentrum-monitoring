metacentrum_monitoring
======================

Role for setting up monitoring by MetaCentrum's Nagios.

Adds MetaCentrum repository, installs needed packages, modifies ssh demon to use DNS.


Requirements
------------

--

Role Variables
--------------

- monitoring_check_mk_packages - list of packages to install
- monitoring_check_mk_dirs - list of directories which will be created under /usr/lib/check_mk_agent/
  - Example value: `- {path: "", owner: "", group: "", mode: ""}` where:
    - path - required
    - owner - optional; Default value: root
    - group - optional; Default value: root
    - mode - optional; Default value: 0755
- monitoring_check_mk_files - list of files to copy to /usr/lib/check_mk_agent/
  - Example value: `- {src: "", dest: "", owner: "", group: "", mode: ""}` where:
    - src - required
    - dest - optional; Default value: same as src
    - owner - optional; Default value: root
    - group - optional; Default value: root
    - mode - optional; Default value: 0711
    
- monitoring_check_mk_templates - list of templates for files in /usr/lib/check_mk_agent/ (File name without .j2)
  - Example value: `- {src: "", dest: "", user: "", group: "", mode: ""}` where:
    - src - required
    - dest - optional; Default value: same as src
    - owner - optional; Default value: root
    - group - optional; Default value: root
    - mode - optional; Default value: 0711
- monitoring_check_mk_config - path to directory with config files (*.cfg) for 
  check_mk to be copied to /etc/check_mk/. Skipped if empty.


Dependencies
------------

--

Example Playbook
----------------

    - hosts: all
      roles:
         - cesnet.metacentrum_monitoring
