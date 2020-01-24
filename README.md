Role Name
=========

Ansible Role for RHEL based (e.g. Red Hat Linux Fedora, and CentOS) systems patching.

Role Variables
--------------

```yaml
---
# defaults file for patch-rhel

patch_rhel_ensure_versionlock: True

# yum command settings
patch_rhel_update_cache: True
patch_rhel_security: True
patch_rhel_bugfix: True

# patch_rhel_exclude_list: kernel* # kernel*,foo*

patch_rhel_autoremove: True

patch_rhel_generate_reports: True
patch_rhel_notify_reports: True

# patch_rhel_versionlock_packages:
  #  - <package_name>

patch_rhel_notify_slack: No
patch_rhel_slack_token: your_slack_token

patch_rhel_notify_email: No
patch_rhel_email_notify_host: email_server_hostname_or_ipaddress
patch_rhel_email_notify_server_port: email_server_port
patch_rhel_email_notify_server_username: user_name
patch_rhel_email_notify_server_password: password
patch_rhel_email_notify_from: reporting@email.com
patch_rhel_email_notify_to: your_email@email.com
patch_rhel_email_notify_cc: another@email.com, another@email.net
patch_rhel_email_notify_subject: "Your subject"
patch_rhel_email_notify_server_secure: always | never | starttls # never will disable this feature

patch_rhel_custom_hook: No
patch_rhel_custom_hook_url: "https://your_web_hook_url/"
patch_rhel_custom_hook_token: your_token
patch_rhel_custom_hook_method: POST
patch_rhel_custom_hook_body_format: json
patch_rhel_custom_hook_content_type: "application/json"
patch_rhel_custom_hook_expected_status_code: 200
```

Example Playbook
----------------

```yaml
- hosts:
    - all
  become: True
  gather_facts: True
  roles:
    - role: ansible-role-patch-rhel
      patch_rhel_generate_reports: True
      patch_rhel_notify_reports: True
      patch_rhel_notify_slack: Yes
      patch_rhel_slack_token: your_slack_token
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
