# Ansible Role: project-sync

Sync database (postgresql or mysql) and files between environments (e.g. production, staging etc.)

## Dependencies

rsync and database packages (mysql or postgresql) of linux distribution

## Example Playbook

    - hosts: server-name
      vars:
        project_sync_instances:
          - name: prod-staging
            src_host: remote-prod.example.com
            src_dir: /srv/store/files
            target_parent_dir: /srv/store
            db_type: postgresql
            db_source_name: store
            db_target_name: store
            db_target_owner: store
      roles:
        - AlphaNodes.project-sync

if you have defined more the one instance and you only want a specific one to run, use --extra-vars "project_sync_instance_name=NAME"'

## License

GPL Version 3

## Author Information

This role was created in 2017 by [AlphaNodes](https://alphanodes.com/).
