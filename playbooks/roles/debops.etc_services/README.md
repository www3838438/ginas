## debops.etc_services

[![Platforms](http://img.shields.io/badge/platforms-debian%20|%20ubuntu-lightgrey.svg)](#)

`etc_services` role can be used to "reserve" or "register" a service port
in `/etc/services` file. Service ports configured this way can appear as
named entries in many command outputs, such as `iptables -L` or `netstat -lp`.
You can also have convenient database of reserved and free ports on
a particular host, and reference ports by their names in firewall
configuration files.

### Installation

To install `debops.etc_services` using Ansible Galaxy, run:

    ansible-galaxy install debops.etc_services




### Role variables

List of default variables available in the inventory:

    ---
    
    # Enable /etc/services.d/ support?
    etc_services: True
    
    # Name of diverted /etc/services, do not change if diversion is active!
    etc_services_diversion: '/etc/services.d/10_debian_etc_services'
    
    
    # ---- Local services ----
    
    # These lists allow you to generate entries for local services not included in
    # officially distributed /etc/services file. They will generate separate files
    # for each configured service in /etc/services.d/ which then will be assembled
    # into complete /etc/services file.
    
    # List of known parameters:
    #  - name: ''                 name of the service, required
    #  - port: ''                 port on which service is accessed, required
    #  - protocol: ''             protocol name to use, 'tcp' by default, optional
    #  - comment: ''              comment to add to the service entry, optional
    
    # These lists should be used in inventory
    etc_services_list: []
    etc_services_group_list: []
    etc_services_host_list: []
    
    # This list can be used in a dependency variables for 'etc_services' role
    etc_services_dependency_list: []
    
      # Example entry
      #- name: 'servicename'
      #  port: '12345'
      #  porotol: 'tcp'
      #  comment: 'Example service'





### Authors and license

`debops.etc_services` role was written by:

- Maciej Delmanowski - [e-mail](mailto:drybjed@gmail.com) | [Twitter](https://twitter.com/drybjed) | [GitHub](https://github.com/drybjed)


License: [GNU General Public License v3](https://tldrlegal.com/license/gnu-general-public-license-v3-(gpl-3))


***

This role is part of the [DebOps](http://debops.org/) project. README generated by [ansigenome](https://github.com/nickjj/ansigenome/).

