# Preinstall

1. Check `vm.swappiness` on all your nodes
    * Set the value to `1` if necessary
```
[root@ip-172-31-29-97 ~]# sysctl vm.swappiness
vm.swappiness = 1
```

2. Show the mount attributes of your volume(s)
```
xvdc    ext4         889a4b89-458d-4243-8459-0ab23d35b540 /data/disk1 xvdc     80G root  disk  brw-rw----
[root@ip-172-31-29-97 ~]# mount | grep xvd
/dev/xvda2 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
/dev/xvdb on /data/disk0 type ext4 (rw,nosuid,nodev,noexec,noatime,seclabel,data=ordered)
/dev/xvdc on /data/disk1 type ext4 (rw,nosuid,nodev,noexec,noatime,seclabel,data=ordered)

[root@ip-172-31-29-97 ~]# lsblk -fm
NAME    FSTYPE LABEL UUID                                 MOUNTPOINT  NAME    SIZE OWNER GROUP MODE
xvda                                                                  xvda     50G root  disk  brw-rw----
├─xvda1                                                               ├─xvda1   1M root  disk  brw-rw----
└─xvda2 xfs          de4def96-ff72-4eb9-ad5e-0847257d1866 /           └─xvda2  50G root  disk  brw-rw----
xvdb    ext4         140c7a68-715f-47e4-8c03-f5f1463150c0 /data/disk0 xvdb     80G root  disk  brw-rw----
xvdc    ext4         889a4b89-458d-4243-8459-0ab23d35b540 /data/disk1 xvdc     80G root  disk  brw-rw----

[root@ip-172-31-29-97 ~]# ls -la /opt /var/log
lrwxrwxrwx. 1 root root 15 Nov 27 15:06 /opt -> /data/disk0/opt
lrwxrwxrwx. 1 root root 15 Nov 27 14:53 /var/log -> /data/disk1/log
```
3. If you have `ext`-based volumes, list the reserve space setting
    * XFS volumes do not support reserve space
```
[root@ip-172-31-29-97 ~]# tune2fs -l /dev/xvdb | grep "Reserved block count"; tune2fs -l /dev/xvdc | grep "Reserved block count"
Reserved block count:     0
Reserved block count:     0
```
4. Disable transparent hugepage support
```
[root@ip-172-31-29-97 ~]# cat /sys/kernel/mm/transparent_hugepage/enabled
always madvise [never]

[root@ip-172-31-29-97 ~]# cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]

[root@ip-172-31-29-97 ~]# cat /proc/meminfo  | grep -i huge
AnonHugePages:      8192 kB
HugePages_Total:       0
HugePages_Free:        0
HugePages_Rsvd:        0
HugePages_Surp:        0
Hugepagesize:       2048 kB
```
5. List your network interface configuration
```
[root@ip-172-31-29-97 ~]# ifconfig eth0
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1440
        inet 172.31.29.97  netmask 255.255.240.0  broadcast 172.31.31.255
        ether 0a:6c:1f:cf:e3:b2  txqueuelen 10000  (Ethernet)
        RX packets 138299  bytes 196509206 (187.4 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 15923  bytes 2392282 (2.2 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

[root@ip-172-31-29-97 ~]# ip addr show dev eth0
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1440 qdisc mq state UP qlen 10000
    link/ether 0a:6c:1f:cf:e3:b2 brd ff:ff:ff:ff:ff:ff
    inet 172.31.29.97/20 brd 172.31.31.255 scope global dynamic eth0
       valid_lft 2240sec preferred_lft 2240sec
```
5. Show that forward and reverse host lookups are correctly resolved
  * For `/etc/hosts`, use `getent`
  * For DNS, use `nslookup`
```
[root@ip-172-31-29-97 ~]# getent hosts $(hostname -a)
172.31.29.97    ip-172-31-29-97.ec2.internal ip-172-31-29-97.ec2 elephant
172.31.29.97    ip-172-31-29-97.ec2.internal ip-172-31-29-97.ec2 elephant

[root@ip-172-31-29-97 ~]# nslookup $(hostname -f)
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-29-97.ec2.internal
Address: 172.31.29.97
```
6. Show the <code>nscd</code> service is running
```
[root@ip-172-31-29-97 ~]# systemctl status nscd
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-11-27 14:16:35 CST; 53s ago
 Main PID: 7703 (nscd)
   CGroup: /system.slice/nscd.service
           └─7703 /usr/sbin/nscd

Nov 27 14:16:35 ip-172-31-29-97.ec2.internal nscd[7703]: 7703 monitoring directory `/etc` (2)
Nov 27 14:16:35 ip-172-31-29-97.ec2.internal nscd[7703]: 7703 monitoring file `/etc/resolv.conf` (5)
Nov 27 14:16:35 ip-172-31-29-97.ec2.internal nscd[7703]: 7703 monitoring directory `/etc` (2)
Nov 27 14:16:35 ip-172-31-29-97.ec2.internal nscd[7703]: 7703 monitoring file `/etc/services` (6)
Nov 27 14:16:35 ip-172-31-29-97.ec2.internal nscd[7703]: 7703 monitoring directory `/etc` (2)
Nov 27 14:16:35 ip-172-31-29-97.ec2.internal nscd[7703]: 7703 disabled inotify-based monitoring for file `/etc/netgroup': No such file or directory
Nov 27 14:16:35 ip-172-31-29-97.ec2.internal nscd[7703]: 7703 stat failed for file `/etc/netgroup'; will try again later: No such file or directory
Nov 27 14:16:35 ip-172-31-29-97.ec2.internal nscd[7703]: 7703 Access Vector Cache (AVC) started
Nov 27 14:16:35 ip-172-31-29-97.ec2.internal systemd[1]: Started Name Service Cache Daemon.
Nov 27 14:16:54 ip-172-31-29-97.ec2.internal nscd[7703]: 7703 checking for monitored file `/etc/netgroup': No such file or directory

[root@ip-172-31-29-97 ~]# nscd -g | head -n 20
nscd configuration:

              0  server debug level
         2m  4s  server runtime
              5  current number of threads
             32  maximum number of threads
              0  number of times clients had to wait
             no  paranoia mode enabled
           3600  restart internal
              5  reload count

passwd cache:

            yes  cache is enabled
            yes  cache is persistent
            yes  cache is shared
            211  suggested size
         216064  total data pool size
            160  used data pool size
            600  seconds time to live for positive entries
```
7. Show the <code>ntpd</code> service is running
```
[root@ip-172-31-29-97 ~]# systemctl status ntpd
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-11-27 14:13:48 CST; 7min ago
 Main PID: 7661 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─7661 /usr/sbin/ntpd -u ntp:ntp -g

Nov 27 14:13:48 ip-172-31-29-97.ec2.internal ntpd[7661]: ntp_io: estimated max descriptors: 1024, initial socket boundary: 16
Nov 27 14:13:48 ip-172-31-29-97.ec2.internal ntpd[7661]: Listen and drop on 0 v4wildcard 0.0.0.0 UDP 123
Nov 27 14:13:48 ip-172-31-29-97.ec2.internal ntpd[7661]: Listen and drop on 1 v6wildcard :: UDP 123
Nov 27 14:13:48 ip-172-31-29-97.ec2.internal ntpd[7661]: Listen normally on 2 lo 127.0.0.1 UDP 123
Nov 27 14:13:48 ip-172-31-29-97.ec2.internal ntpd[7661]: Listen normally on 3 eth0 172.31.29.97 UDP 123
Nov 27 14:13:48 ip-172-31-29-97.ec2.internal ntpd[7661]: Listening on routing socket on fd #20 for interface updates
Nov 27 14:13:49 ip-172-31-29-97.ec2.internal ntpd[7661]: 0.0.0.0 c016 06 restart
Nov 27 14:13:49 ip-172-31-29-97.ec2.internal ntpd[7661]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
Nov 27 14:13:49 ip-172-31-29-97.ec2.internal ntpd[7661]: 0.0.0.0 c011 01 freq_not_set
Nov 27 14:13:56 ip-172-31-29-97.ec2.internal ntpd[7661]: 0.0.0.0 c614 04 freq_mode

[root@ip-172-31-29-97 ~]# timedatectl status
Warning: Ignoring the TZ variable. Reading the system's time zone setting only.

      Local time: Mon 2017-11-27 20:21:39 UTC
  Universal time: Mon 2017-11-27 20:21:39 UTC
        RTC time: Mon 2017-11-27 20:21:39
       Time zone: UTC (UTC, +0000)
     NTP enabled: no
NTP synchronized: yes
 RTC in local TZ: no
      DST active: n/a
```
