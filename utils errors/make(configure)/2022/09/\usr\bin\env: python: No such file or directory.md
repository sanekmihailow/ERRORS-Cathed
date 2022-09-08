```
$ ./configure
/usr/bin/env: ‘python’: No such file or directory
```

if exist python2 or python3, check **/usr/bin/ |grep python**
```bash
ls /usr/bin/ -la |grep python
lrwxrwxrwx   1 root root          9 Jun 24 21:02 python2 -> python2.7
-rwxr-xr-x   1 root root       8024 Jun 24 21:02 python2.7
lrwxrwxrwx   1 root root         25 Oct  7  2021 python3 -> /etc/alternatives/python3
lrwxrwxrwx   1 root root         31 Aug 25  2021 python3.6 -> /usr/libexec/platform-python3.6
lrwxrwxrwx   1 root root         32 Aug 25  2021 python3.6m -> /usr/libexec/platform-python3.6m
lrwxrwxrwx.  1 root root         24 Oct 23  2019 unversioned-python -> /etc/alternatives/python

```

- if not exist /usr/bin/python
```nginx
ln -s /etc/alternatives/python3 /usr/bin/python
#or ln -s /usr/bin/python2.7 /usr/bin/python
```
