# RHCE Ansible Practice 4
## Handlers

\* Username is `vagrant` with a password of `vagrant` if you need it.

1. Create a playbooks directory with a playbook named setup.yml in it. In the playbook, do the following:
    - force_handlers
    - Install httpd
    - Change ServerTokens and OS signature in httpd.conf or security.conf?
    - Restart apache IF the file has been changed
    - Use the command module to see if firewalld is-active. Have it ignore failures. If it is not, it should run the "add http to firewall" and "restart firewalld" handlers
    - Use the shell module to grep for the user `homer` in /etc/passwd. Have it failed_when there is no result????    tasks:
  6     - name: Run a script
  7       shell:
  8         cmd: "/usr/bin/grep homer /etc/passwd"
  9       register: output
 10       changed_when: "'homer' in output.stdout"
 11       notify:
 12         - hell yeah
 13    
 14   handlers:
 15     - name: hell yeah
 16       debug:
 17         msg: 'YES YES YES'



    - Create a restart apache handler


Error handling

Do a block of 3 with a single conditional.

Block/Rescue/Always