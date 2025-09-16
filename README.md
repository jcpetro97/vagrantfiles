# Repository of vagrant files for individualized testing


|Linux Distro|Version|Last Updated|
|------------|-------|------------|
|Debian|12|09/11/2025|
|Ubuntu|2204|09/11/2025|
|Ubuntu|2404|09/11/2025|
|Rocky|8|09/11/2025|
|Rocky|9|09/11/2025|


**NOTE:** For Virtualbox, Linux/MacOS hosts can only have a total of 128 HostOnly networks defined.  In Virtualbox 6.1.30, they started to enforce that limitation. By default the allowed HostOnly ranges are 192.168.56.0/21 ( 192.168.56 -> 192.168.63).  The valid networks can be changed. To change the subnets, do the following:

* create/edit the file `/etc/vbox/networks.conf`
* add the following options inside the file ( including the * )

```
* 192.168.0.0/16
```

This will add all of the entire 192.168.0 range.  You can also add multiple subnets by changing the entry to this:

```
* 192.168.0.56/21 192.168.10.0/24
```

I have changed my networks.conf file so that the HostOnly range would be (192.168.56 -> 192.168.80 )

```
* 192.168.56.0/21 192.168.64.0/20 192.168.80.0/24 192.168.10.0/24
```

**WARNING:** if you add the `/etc/vbox/networks.conf` there must be content inside, or virtualbox won't function correctly.


**NOTE:** The default subnet for the Vagrantfile.virtualbox is `192.168.56` so you may need to change that in the Vagrantfile.
