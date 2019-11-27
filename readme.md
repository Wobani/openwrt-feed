# OpenWRT dist
Build with GitHub Workflow daily.

This project is only for OpenWRT routers. Currently it's based on 1907.

[You may want original project here.](http://openwrt-dist.sourceforge.net)

## Usage
First, Add the public dist key.
``` 
wget https://github.com/simonsmh/openwrt-dist/raw/master/simonsmh-dist.pub
opkg-key add simonsmh-dist.pub
```

You can use the following command to get architecture.
```
opkg print-architecture | awk '{print $2}'
```

Then, check your architecture in all branches and add the following line to `/etc/opkg.conf`.
```
src/gz simonsmh https://github.com/simonsmh/openwrt-dist/raw/{architecture}/packages/{architecture}/base
```

Then install what you want.
```
opkg update
opkg install ChinaDNS
opkg install luci-app-chinadns
opkg install dns-forwarder
opkg install luci-app-dns-forwarder
opkg install shadowsocks-libev
opkg install luci-app-shadowsocks
opkg install v2ray-plugin
opkg install luci-app-pdnsd
opkg install luci-app-nfs
opkg install v2ray-core
opkg install luci-app-v2ray
opkg install luci-app-vlmcsd
```
For more detail please check the `base` directory.

You can also search and install them in LuCI or SCP/FTP upload these downloaded files to your router, then login to your router and use opkg to install these .ipk file.

## Build it yourself
[Check here](https://github.com/simonsmh/openwrt-dist/blob/master/.github/workflows/main.yml)

## License
GPLv3

## Credit
Copyright © 2017-2019 simonsmh
