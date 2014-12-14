Resistencia
===========

_The resistance against gag laws and unfaithful governments starts in our servers._

Use Resistencia as a quick, simple and collaborative way to set up servers using Ansible. Resistencia hardens your servers using swarm intelligence at its best.

![¡Viva la resistencia!](http://www.memegenerator.es/imagenes/memes/full/3/70/3706143.jpg)

If you want to collaborate: fork, change, pull request, repeat. All contributions will be reviewed as soon as possible. Thanks!

This is a [Confederación Pirata](http://confederacionpirata.org) project.

Usage
-----

    # mkdir -p myserver.example.com/roles
    # cat > myserver.example.com/site.yml <<EOF
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
