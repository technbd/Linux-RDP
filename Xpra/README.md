
## Xpra | Remote Desktop 

`xpra` is known as "screen for X" : its seamless mode allows you to run X11 programs, usually on a remote host, direct their display to your local machine, and then to disconnect from these programs and reconnect from the same or another machine(s), without losing any state. Effectively giving you remote access to individual graphical applications.



### Installation: Method-1: 

_For Centos:_
```
wget -O /etc/yum.repos.d/xpra.repo https://raw.githubusercontent.com/Xpra-org/xpra/master/packaging/repos/Fedora/xpra.repo
```


_For Rocky:_
```
wget -O /etc/yum.repos.d/xpra.repo https://raw.githubusercontent.com/Xpra-org/xpra/master/packaging/repos/rockylinux/xpra.repo
```



```
cat /etc/yum.repos.d/xpra.repo


[xpra]
name=Xpra $releasever - $basearch
enabled=1
metadata_expire=1d
gpgcheck=1
gpgkey=https://xpra.org/xpra.asc
#baseurl=https://xpra.org/dists/Fedora/$releasever/$basearch/
baseurl=https://xpra.org/dists/CentOS/$releasever/$basearch/
keepcache = 0
```



```
yum install xpra -y 
```



#### Start Xpra on the Remote Server:

- Here, `:100` specifies the display number, and `xterm` is an example application to launch.
- `xterm` must be installed on the HOST.


_Run on Server:_

```
xpra start :100 --start=xterm
```


Or,

```
xpra start ssh://USER@HOST/ --start=xterm
```


#### Attach from the Client:

_Attach from the Client:_

```
xpra attach ssh://USERNAME@HOST/100
```


```
xpra attach ssh://rcms@192.168.10.191/100
```





### Installation: Method-2: 

```
git clone https://github.com/Xpra-org/xpra
cd xpra
./setup.py install-repo
```





### Links:
- [Xpra | Github](https://github.com/Xpra-org/xpra/)
- [Download Xpra](https://github.com/Xpra-org/xpra/wiki/Download#-for-rpm-distributions)
- [Stable dists](https://xpra.org/dists/)
- [Command line usage Examples](https://github.com/Xpra-org/xpra/blob/master/docs/Usage/README.md)

