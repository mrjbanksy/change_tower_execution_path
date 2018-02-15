Role Name
=========

change_tower_execution_path - due to noexec settings on /tmp folder or other reasons, create new folder and set Tower to use that instead for its execution folder

Requirements
------------

Ansible Tower should already be installed by the time this role is called. This role can be included at the end of the Tower install playbook.

Set tower_user_password. I recommend setting it in a Vault encrypted file and then referencing it within 'defaults/main.yml', for example:

'tower_user_password: "{{ vaulted_tower_user_password }}"'

Role Variables
--------------

tower_tmp_dir: the new folder for Tower to use. Default: /var/lib/awx/tmp

tower_rest_url: the url to the Tower API. Default: https://localhost/api/v2/settings/jobs/

tower_user: the user to log into Tower with. Default: admin

tower_user_password: the password to log into Tower with. Default: not defined

Dependencies
------------

No external dependencies

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: change_tower_execution_path

License
-------

GPLv3


Author Information
------------------

Jeremy Banks (jbanks@redhat.com)
