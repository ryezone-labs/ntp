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

  When `true`, configures role to overwrite default configuration of NTP daemon
  and client with managed configuration.

- `ntp_daemon_log_options` (string)

  Space delimited list of options to configure in NTP daemon configuration
  settings.

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

- `ntp_daemon_servers` (list of string)

  Selects the ntp servers daemon should listen to for ntp updates.

- `ntp_servers` (list of string)

  Selects the ntp servers the ntp client should listen to for ntp updates.

- `ntp_fallback_servers` (list of string)

  Selects the fallback ntp servers the ntp client should listen to in the event
  the servers in `ntp_servers` cannot be reached.

Example Playbook
----------------

Example ntp client configuration

```yaml
- hosts: 127.0.0.1
  connection: local
  vars:
    - ntp_enabled: True
    - ntp_timezone: Etc/UTC
    - ntp_servers:
      - ntp.domain.local
  roles:
    - ryezone_labs.ntp
```

Example ntp daemon configuration

```yaml
- hosts: 127.0.0.1
  connection: local
  vars:
    - ntp_enabled: True
    - ntpd_enabled: True
    - ntp_timezone: Etc/UTC
    - ntp_area: us
    - ntp_servers:
      - 127.0.0.1
  roles:
    - ryezone_labs.ntp
```

License
-------

BSD
