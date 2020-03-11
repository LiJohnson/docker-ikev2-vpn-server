

# install strongswan

apt-get install -y strongswan libstrongswan-standard-plugins libcharon-extra-plugins libcharon-standard-plugins

# edit /etc/ipsec.conf


```
conn toserver  
    keyexchange=ikev2  
    ike=aes256-sha256-modp2048,3des-sha1-modp2048,aes256-sha1-modp2048!  
    esp=aes256-sha256,3des-sha1,aes256-sha1!  
    rekey=no  
    left=%any  
    leftsourceip=【10.8.0.7】
    leftsubnet=0.0.0.0/0  
    leftfirewall=yes  
    leftsendcert=never  
    leftauth=【psk】
    right=【vpn-host】
    rightid=【vpn-host】
    rightauth=【psk】
    rightsubnet=0.0.0.0/0  
    rightsendcert=always  
    dpdaction=clear  
    fragmentation=yes  
    auto=start   

```

# edit /etc/ipsec.secrets

```
: PSK 【"123qQ3SUy7*******************gRCcVrWs="】
```

ref: https://github.com/jawj/IKEv2-setup/blob/master/setup.sh
