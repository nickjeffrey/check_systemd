# check_systemd
nagios check for Linux systemd unit status  (services, mounts, etc)

# Requirements
perl, ssh key pair auth

# Configuration
Add a section similar to the following to the services.cfg file on the nagios server.
```
define service{
        use                             generic-service
        host_name                       linux01.example.com
        service_description             systemd dhcpd.service
        check_command                   check_by_ssh!"/usr/local/nagios/libexec/check_systemd --unit=dhcpd.service"
        }
```

# Output
You will see output similar to the following:
```
systemd dhcpd.service OK - systemd unit dhcpd.service (DHCP Server Daemon) status is active
```
