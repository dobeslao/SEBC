# kinit, autenticación

```
[dobeslao@ip-172-31-24-52 ~]$ kinit dobeslao@VINKOS.COM
Password for dobeslao@VINKOS.COM:
[dobeslao@ip-172-31-24-52 ~]$ klist -e
Ticket cache: FILE:/tmp/krb5cc_1002
Default principal: dobeslao@VINKOS.COM
```

# klist, propiedades de ticket Kerberos

```
[dobeslao@ip-172-31-24-52 ~]$ klist -e
Ticket cache: FILE:/tmp/krb5cc_1002
Default principal: dobeslao@VINKOS.COM

Valid starting       Expires              Service principal
11/29/2017 13:07:36  11/30/2017 13:07:36  krbtgt/VINKOS.COM@VINKOS.COM
        renew until 12/06/2017 13:07:36, Etype (skey, tkt): arcfour-hmac, arcfour-hmac
[dobeslao@ip-172-31-24-52 ~]$ klist -l
Principal name                 Cache name
--------------                 ----------
dobeslao@VINKOS.COM            FILE:/tmp/krb5cc_1002
```
