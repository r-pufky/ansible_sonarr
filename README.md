# Sonarr
Sonarr installation from public release tarball.

## Requirements
[supported platforms](https://github.com/r-pufky/ansible_sonarr/blob/main/meta/main.yml)

[collections/roles](https://github.com/r-pufky/ansible_sonarr/blob/main/meta/requirements.yml)

## Role Variables
[defaults](https://github.com/r-pufky/ansible_sonarr/tree/main/defaults/main)

### Ports
All ports and protocols have been defined for the role.

[defaults/ports.yml](https://github.com/r-pufky/ansible_sonarr/blob/main/defaults/main/ports.yml)

## Dependencies
Part of the [r_pufky.srv](https://github.com/r-pufky/ansible_collection_srv)
collection.

## Example Playbook
Read defaults documentation.

Install latest release of Sonarr; ensuring media files have proper permissions.
Version (and databases) will be migrated and updated on new releases. Media
permissions will be set to ensure Sonarr can read files.
``` yaml
- name: 'sonarr server'
  hosts: 'sonarr.example.com'
  become: true
  roles:
     - 'r_pufky.sonarr'
  vars:
    sonarr_service_version: 'latest'
    sonarr_config_api_key: '{{ vault_sonarr_api_key }}'
    sonarr_config_update_automatically: true
    sonarr_config_theme: 'dark'
    sonarr_media_root_folders:
      - '/data/media'
    sonarr_media_set_perms_file_enable: true
```

## Development
Configure [environment](https://github.com/r-pufky/ansible_collection_srv/blob/main/docs/dev/environment/README.md)

Run all unit tests:
``` bash
molecule test --all
```

### Issues
Create a bug and provide as much information as possible.

Associate pull requests with a submitted bug.

## License
[AGPL-3.0 License](https://www.tldrlegal.com/license/gnu-affero-general-public-license-v3-agpl-3-0)
 [(direct link)](https://github.com/r-pufky/ansible_nzbget/blob/main/LICENSE)

## Author Information
PGP Fingerprint: [466EEC2B67516C7117C85CE3A0BC35D16698BAB9](https://keys.openpgp.org/vks/v1/by-fingerprint/466EEC2B67516C7117C85CE3A0BC35D16698BAB9)
| [github gist](https://gist.github.com/r-pufky/a8df36977c55b5bb20829267c4c49d22)
