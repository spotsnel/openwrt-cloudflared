OpenWRT instructions for Cloudflared
====================================


[Download](https://github.com/spotsnel/cloudflared/releases/tag/20230710) or compile a suitable binary

```
$ scp cloudflared root@[routerip]:/opt/sbin
```

```
$ ssh root@[routerip]
$ cd /opt/sbin
$ chmod +x cloudflared
$ ./cloudflared tunnel login
$ ./cloudflared tunnel create $HOSTNAME
$ ./cloudflared tunnel run $HOSTNAME
```

Copy the init script from this repo

```
$ scp cloudflared root@[routerip]:/etc/init.d
```

```
$ ssh root@[routerip]
$ chnod +x /etc/init.d/cloudflared
$ /etc/init.d/cloudflared enable
$ /etc/init.d/cloudflared start
```
