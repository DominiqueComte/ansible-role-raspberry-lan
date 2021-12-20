Raspberry LAN Role
=========

A role to set up a Raspberry Pi for some LAN services.

Requirements
------------

A Raspberry Pi
A rSyslog server

Role Variables
--------------

For the apt task:
The 2 URLs are for 2 Nexus 3 APT mirror repositories.
* apt_main_mirror_url: changeme
  * APT mirror settings:
    * distribution: buster
    * remote storage: http://raspbian.raspberrypi.org/raspbian/ (from the APT original settings)
* apt_archive_mirror_url: changeme
    * distribution: buster
    * remote storage: http://archive.raspberrypi.org/debian/ (from the APT original settings)

For the rsyslog task:
* rsyslog_service: rsyslog
  * the rsyslog service name
* rsyslog_server_hostname: changeme
  * the hostname of the rsyslog service. leave it to "changeme" to skip the task.
* rsyslog_forward_rule_name: 00central_log_server.conf
  * the name of the rule file to create in /etc/rsyslog.d

For the unattended upgrades:
* unattended_upgrades_email_address: changeme@mailserver.local
  * leave the default value to skip setting up email notifications
* unattended_upgrades_auto_reboot: false
  * reboot automatically when necessary, or not.


Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - ansible-role-raspberry-lan

License
-------

Unlicensed
