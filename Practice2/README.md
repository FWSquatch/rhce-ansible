# RHCE Ansible Practice 2

\* Username is `vagrant` with a password of `vagrant` if you need it.

1. Create an inventory file that groups the 2 nodes in the following way:
    - `node1` is in the `webserver` group.
    - `node2` is in the `dbserver` group.

2. Create a file named `ansible.cfg` and do the following:
    - set the default inventory to your newly created file.
    - set the default user to `vagrant`
    - set it to ignore deprecation warnings
    - set up privilege escalation to become `root` using `sudo`.
    - set privilege escalation to default to not becoming root.
    - set privilege escalation to never ask for a password.

3. Create a playbooks directory with a playbook named setup.yml in it. In the playbook, do the following:
    - Use the following variables:
        