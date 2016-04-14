ansible-vyos
=============

Installs VyOS configuration.

Tested on VyOS 1.1.7, patches are welcome.

## Installation

Clone this repo to your Ansible roles directory

    git clone git://github.com/gregfaust/ansible-vyos.git vyos

## Usage

Here's an example how to use this role.

    ---
    - hosts: servers
      become: root
      roles:
        - { role: vyos,
            vyos_configuration: "vyos_configurations/vyos_configuration_{{ ansible_hostname }}.j2"
          }
      tasks:
        - name: install OpenVPN Key
          copy: src="vyos_configurations/{{ ansible_hostname }}.key" dest="/config/auth/{{ ansible_hostname }}.key" owner=root group=vyattacfg mode=0775

The user must have root permissions in order to copy keys and set permissions.

## License

Licensed under the GPLv3 License. See the LICENSE file for details.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
