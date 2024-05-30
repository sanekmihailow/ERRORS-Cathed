```
May 30 13:06:51 server1 sshd[1328]: Failed publickey for user1 from 10.1.168.76 port 55152 ssh2: RSA SHA256:Tni9Q2HB3R35pNiPuwLacKaasdaQal;dsa
May 30 13:06:51 server1 sshd[1328]: fatal: Access denied for user user1 by PAM account configuration [preauth]
```
1) check what user1 exist in `/etc/shadow`.  
    If not exist edit shadow and add(insert line) user
    
