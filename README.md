Information
===========



PPTP
----

Build Docker Image from Dockerfile

```
$ docker build -t alpine/pptp .
```

Delete Docker Image

```
$ docker rmi alpine/pptp
```

Debug Docker Container

```
$ docker run --rm -ti alpine/pptp /bin/sh
$ docker run --rm -ti alpine/pptp ls /etc/ppp/
$ docker run --rm -ti alpine/pptp cat /etc/ppp/options.pptp
```

OS
--

Settings on OS for firewalld

```
$ firewall-cmd --permanent --direct --add-rule ipv4 filter INPUT 0 -i eth0 -p tcp --dport 1723 -j ACCEPT
$ firewall-cmd --permanent --direct --add-rule ipv4 filter INPUT 0 -p gre -j ACCEPT
$ firewall-cmd --permanent --direct --add-rule ipv4 filter POSTROUTING 0 -t nat -o eth0 -j MASQUERADE
$ firewall-cmd --permanent --direct --add-rule ipv4 filter FORWARD 0 -i ppp+ -o eth0 -j ACCEPT
$ firewall-cmd --permanent --direct --add-rule ipv4 filter FORWARD 0 -i eth0 -o ppp+ -j ACCEPT
$ firewall-cmd --reload
```

Settings on OS for sysctl.conf

```
$ vim /etc/sysctl.conf

...
net.ipv4.ip_forward = 1
...

$ sysctl -p
```
