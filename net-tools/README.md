net-tools
=========

A selection of network diagnostic tools including:

'netstat' 'iostat' 'vmstat' 'iptraf' 'sar' 'sysstat' 'iftop' 'tcpdump' 'hping3' 'nethogs'

SSH Key file
------------

authorized_keys should be replaced to use your own keys

To generate a keypair:

    ssh-keygen -t rsa
    
Then copy the public key to authorized_keys

    cp id_rsa.pub authorized_keys
