---
layout: post
title: Restart NFS on Synology Diskstation DSM 6.2
---

# {{ page.title }}

I was having trouble mounting an NFS share from my Synology DS411j:

    gareth: ~
    $ showmount -e diskstation
    showmount: Cannot retrieve info from host: diskstation: RPC failed:: RPC: Unable to send; errno = Bad file descriptor

I can access the NAS, so lets have a look at what it's exporting:

    gareth@diskstation:/$ showmount -e localhost
    clnt_create: RPC: Port mapper failure - Unable to receive: errno 111 (Connection refused)

Strange. I tried `rpcinfo`:

    gareth@diskstation:/$ sudo rpcinfo
    rpcinfo: can't contact rpcbind: RPC: Remote system error - Connection refused

I'm wondering if an automatic update has borked NFS, so I'll try restarting it:

    gareth@diskstation:/$ sudo service --status-all
    sudo: service: command not found

Okay, so I can't restart using `service`. Nothing in the usual `/etc/init.d` either.

    gareth@diskstation:/$ sudo ls -al /etc/init.d/
    total 8
    drwxr-xr-x  2 root root 4096 Feb 15  2012 .
    drwxr-xr-x 48 root root 4096 Aug 20 21:24 ..

Wonder where the startup script is…

    gareth@diskstation:/$ sudo find . -name *nfsd* -type f
    # Loads of files…

`/usr/syno/etc.defaults/rc.sysv/S83nfsd.sh` looks promising; `cat`ing it confirms it looks like an init script.

    gareth@diskstation:/$ sudo ./usr/syno/etc.defaults/rc.sysv/S83nfsd.sh restart
    statd: no process found
    mountd: no process found
    idmapd: no process found
    svcgssd: no process found
    rpcbind: no process found
    :: Unloading module nfsd ... [FAILED]
    :: Unloading module exportfs ... [FAILED]
    Starting NFS server...

It worked!

    gareth@diskstation:/$ showmount -e localhost
    Export list for localhost:
    /volume2/gareth         REDACTED
