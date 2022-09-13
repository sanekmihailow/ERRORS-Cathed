```
Dependencies Resolved

=================================================================================================================================================================================
 Package                                               Arch                             Version                                Repository                                   Size
=================================================================================================================================================================================
Installing:
 mysql-community-libs                                  x86_64                           5.7.39-1.el7                           mysql57-community                           2.6 M
     replacing  mariadb-libs.x86_64 1:5.5.68-1.el7
 mysql-community-libs-compat                           x86_64                           5.7.39-1.el7                           mysql57-community                           1.2 M
     replacing  mariadb-libs.x86_64 1:5.5.68-1.el7
 mysql-community-server                                x86_64                           5.7.39-1.el7                           mysql57-community                           178 M
Installing for dependencies:
 mysql-community-client                                x86_64                           5.7.39-1.el7                           mysql57-community                            28 M
 mysql-community-common                                x86_64                           5.7.39-1.el7                           mysql57-community                           311 k

Transaction Summary
=================================================================================================================================================================================
Install  3 Packages (+2 Dependent packages)

Total size: 210 M
Is this ok [y/d/N]: y
Downloading packages:
warning: /var/cache/yum/x86_64/7/mysql57-community/packages/mysql-community-client-5.7.39-1.el7.x86_64.rpm: Header V4 RSA/SHA256 Signature, key ID 3a79bd29: NOKEY
Retrieving key from file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql


The GPG keys listed for the "MySQL 5.7 Community Server" repository are already installed but they are not correct for this package.
Check that the correct key URLs are configured for this repository.


 Failing package is: mysql-community-client-5.7.39-1.el7.x86_64
 GPG Keys are configured as: file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
```

- in 2022 add gpg keys 2022 it resolve this problem

```nginx
rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2022
```
