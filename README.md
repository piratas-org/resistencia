Resistencia
===========

_The resistance against gag laws and unfaithful governments starts in our servers._

Use Resistencia as a quick, simple and collaborative way to set up servers using Ansible. Resistencia hardens your servers using swarm intelligence at its best.

![¡Viva la resistencia!](http://www.memegenerator.es/imagenes/memes/full/3/70/3706143.jpg)

If you want to collaborate: fork, change, pull request, repeat. All contributions will be reviewed as soon as possible. Thanks!

This is a [Confederación Pirata](http://confederacionpirata.org) project.

Features
--------

* Encrypted administration e-mails (logwatch).
* File system monitorization with rkhunter.
* /etc monitoring and managing with etckeeper.
* [Haveged](https://wiki.archlinux.org/index.php/Haveged), entropy daemon, up and running for unpredictable random number generator based upon an adaptation of the HAVEGE algorithm.
* SELinux and Linux Auditing System properly configured.
* Set up to meet requirements from Security Content Automation Protocol (SCAP, see https://fedorahosted.org/scap-security-guide/).
* SSH with sane defaults.
* Unattended updates.

Usage
-----

    # mkdir -p myserver.example.com/roles
    # cat > myserver.example.com/localhost <<EOF
    127.0.0.1 ansible_connection=local
    EOF
    # cat > myserver.example.com/site.yml <<EOF
    ---
    - hosts: all
      vars:
        - hostname: myserver.example.com
        - admin: { user: admin,
                   email: admin@thirdparty.com,
                   key: URGPGKEY,
                   internal_email: "root@{{hostname}}" }
      roles:
        - resistencia
    EOF
    # git clone https://github.com/confederacion-pirata/resistencia myserver.example.com/roles/resistencia
    # ansible-playbook -i myserver.example.com/localhost myserver.example.com/site.yml
