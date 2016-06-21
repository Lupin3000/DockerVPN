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
