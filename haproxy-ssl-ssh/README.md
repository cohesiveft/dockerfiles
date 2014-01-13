proxy-ssl-ssh
===============

SSL Key files
-------------

ssl.key and ssl.crt should be replaced with your own key files

To generate your own private key:

    openssl genrsa -des3 -out ssl.key 1024

To remove the passphrase:

    cp ssl.key ssl.key.bak
    openssl rsa -in ssl.key.bak -out ssl.key

To generate a Certificate Signing Request (CSR):

    openssl req -new -key ssl.key -out ssl.csr

To then make a certificate:

    openssl x509 -req -days 3650 -in ssl.csr -signkey ssl.key -out ssl.crt

SSH Key file
------------

authorized_keys should also be replaced to use your own keys

To generate a keypair:

    ssh-keygen -t rsa
    
Then copy the public key to authorized_keys

    cp id_rsa.pub authorized_keys

Config files
------------

haproxy.cfg and nginx.conf can be modified to work with different server IPs etc.
