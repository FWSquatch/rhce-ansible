# RHCE Ansible Practice 1

1. Use `vagrant up` to fire up the lab environment.
2. Use `vagrant ssh control` to remote into the control node.
3. Username is `vagrant` with a password of `vagrant`
4. Create an `automation` directory in the vagrant home folder on the control host.

5. Create an inventory file that groups the 3 nodes in the following way:
    - `node1` and `node2` are in the `webservers` group.
    - `node3` is in the `db` group.

6. Create a file named `ansible.cfg` and do the following:
    - set the default inventory to your newly created file.
    - set the default user to `devops`
    - set up privilege escalation to become `root` using `sudo`.
    - set privilege escalation to default to not becoming root.
    - set privilege escalation to never ask for a password.

7. Use an adhoc command to create the user `devops` with a UID of 5000 and add it to the `wheel` group.

8. Create a `playbooks` folder and in it, create a playbook called `hostnames.yml`. 
    - Create a play that adds the following lines to each `/etc/hosts` file:
        ```
        192.168.88.2 control.rhce.lab control
        192.168.88.101 node1.rhce.lab node1
        192.168.88.102 node2.rhce.lab node2
        192.168.88.103 node3.rhce.lab node3
        ```
    - In the same playbook, create another play that adds those same lines to the `/etc/hosts` file on the control node.

9. Create another playbook named `setup.yml` that:
    - Ensures that the following packages are installed on the `webserver` nodes.: httpd, firewalld, fail2ban.
    - Ensures that firewalld and apache are enabled and running. 
    - Copies an `index.html` file to the `/var/www/html/` folder on the webservers. The file should contain the following text: 'This is an Apache test page.\n'
    - allows the web traffic through the firewall of each webserver
    - tests each webserver from the localhost to make sure it is accessible.
