ryezone_labs.ntp
=========

Installs and configures ntp client and daemon software.

Role Variables
--------------

- `ntpd_enabled` (bool)

  When `true`, installs and configures the NTP daemon.

- `ntp_enabled` (bool)

  When `true`, installs and configures the NTP client.

- `ntp_timezone` (string)

  Sets the timezone for the server.

- `ntp_manage_config` (bool)

  When `true`, configures role to overwrite default configuration of NTP daemon and client with managed configuration.

- `ntp_daemon_log_options` (string)

  Space delimited list of options to configure in NTP daemon configuration settings.

- `ntp_daemon_maxupdateskew` (decimal)

  Sets the threshold used by the NTP daemon for determining whether an estimate
  may be so unreliable that it should not be used.

- `ntp_daemon_logchange` (decimal)

  Sets the threshold used by the NTP daemon for amount of adjustment of the
  system clock that will generate a syslog message.

- `ntp_daemon_allow` (list of string)

  List of IP Addresses to allow communication with the NTP daemon.

- `ntp_area` (string)

  Sets the NTP area path.  See http://support.ntp.org/bin/view/Servers/NTPPoolServers

  


Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
