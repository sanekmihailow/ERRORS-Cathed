```
Failed to start Docker Application Container Engine
...
failed to load listeners: no sockets found via socket activation: make sure the service was started by systemd  
```
- `vim /usr/lib/systemd/system/docker.service`
```
[Service]

```diff
- ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
+ ExecStart=/usr/bin/dockerd -H unix:// --containerd=/run/containerd/containerd.sock
```
- `systemctl daemon-reload`
- `systemctl restart docker`
