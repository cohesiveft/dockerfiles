varnish-ssh
===========

See the [Using Docker.io for content caching](http://blog.cohesiveft.com/2014/02/using-dockerio-for-content-caching.html) blog post for more details on usage.

SSH Key file
------------

authorized_keys should also be replaced to use your own keys

To generate a keypair:

    ssh-keygen -t rsa
    
Then copy the public key to authorized_keys

    cp id_rsa.pub authorized_keys

Config files
------------

custom.vcl can be modified to work with different server IPs etc.
supervisord.conf may be used to run varnishlog (or varnishncsa)
