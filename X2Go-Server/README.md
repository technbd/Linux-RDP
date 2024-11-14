
## X2Go Server:


### Install a Desktop Environment:
If you don’t have a desktop environment installed, you’ll need to install one. X2Go works best with lightweight environments like `XFCE` or `MATE`.


_To install XFCE:_

```
yum list installed | grep xfce
```


```
yum groupinstall "Xfce" -y
```


```
yum remove -y @xfce

yum remove -y xfce* xfdesktop* xfwm* xfce4* thunar*

yum remove -y lightdm lightdm-gtk
```


Or,


_To install MATE:_
```
yum groupinstall "MATE Desktop" -y
```





### Install the X2Go Server:

```
yum install epel-release -y
```



_Install perl-CPAN, which is the standard module installer for Perl: (Optional)_

```
yum install perl-CPAN -y


cpan -i File::BaseDir
```


Or,

_Alternative: Install Perl File::BaseDir via EPEL_

```
yum install perl-File-BaseDir -y
```



_Install the X2Go Server:_

```
yum install x2goserver x2goserver-xsession -y
```



_X2Go should automatically run with your SSH daemon. Ensure SSH is enabled and started:_

```
systemctl enable sshd
systemctl start sshd
```





### X2Go Client:



```
yum install x2goclient -y 
```


_Install (If need):_
```
yum install mesa-libGL mesa-libGLU mesa-libEGL mesa-dri-drivers -y
```



_Run on Linux CLI:_
```
x2goclient
```





### Links:
- [X2Go Server installation](https://wiki.x2go.org/doku.php/doc:installation:x2goserver)
- [X2Go Client](https://wiki.x2go.org/doku.php/doc:installation:x2goclient)
- [Install X2Go Server | Video ](https://www.youtube.com/watch?v=IYsHa260zi4)
