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

7. Use an adhoc command to create the user `devops` with a UID of 5000 and add him to the `wheel` group.

8. Create a `playbooks` folder and in it, create a playbook called `hostnames.yml`. Create plays that:
    - add the following lines to each `/etc/hosts` file:
        ```
        192.168.88.2 control.centos8.test control
        192.168.88.101 node1.centos8.test node1
        192.168.88.102 node2.centos8.test node2
        192.168.88.103 node3.centos8.test node3
        ```
    - adds those same lines to the `/etc/hosts` file on `localhost`.
    - installs and enables Apache webserver on the `webserver` nodes.
    - Copies an `index.html` file to the `/var/www/html/` folder on the webservers. The file should contain the following text: 'This is an Apache test page.\n'
    - allows the web traffic through the firewall of each webserver
    - tests each webserver from the localhost to make sure it is accessible.