Role Name
=========

create_tower_tmp_folder - due to noexec settings on /tmp folder, create new folder and set Tower to use that instead

Requirements
------------

Should be run as part of the Tower install. If not, tower_admin_password will need to be set

Role Variables
--------------

tower_tmp_dir: the new folder for Tower to use. Default: /var/lib/awx/tmp

tower_rest_uri: the uri to the Tower API. Default: https://localhost/api/v2/settings/jobs/

tower_user: the user to log into Tower with. Default: admin

tower_admin_password: the password to log into Tower with. Default: as part of Tower install, set in group_vars/all/secrets.yaml

Dependencies
------------

No external dependencies

Example Playbook
----------------

    - hosts: servers
      tasks:
        - name: create tower tmp folder
          include_role:
            name: create_tower_tmp_folder

License
-------


Author Information
------------------

Jeremy Banks (jbanks@redhat.com)
