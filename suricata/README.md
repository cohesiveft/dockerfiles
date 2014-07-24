Suricata
========

Dockerfile and associated config to install Suricata (release 2.1.0) and associated tools:

Oinkmaster
----------

Script to pull Emerging Threats open rules

SSH Key file
------------

authorized_keys should also be replaced to use your own keys

To generate a keypair:

    ssh-keygen -t rsa
    
Then copy the public key to authorized_keys

    cp id_rsa.pub authorized_keys
