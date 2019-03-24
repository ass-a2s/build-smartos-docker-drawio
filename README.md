
Requirement
===========

* SmartOS > 20180315T080815Z
* https://github.com/joyent/smartos-live/commit/afe9efb0f462523c6f3b74405b17831c715df8d7

external Nextcloud Service
==========================

* https://github.com/ass-a2s/build-lx-debian-nextcloud

Usage
=====

```
1. (log on to the smartos machine via ssh)

2. imgadm import assa2s/draw.io

3. imgadm list --docker | grep "assa2s/draw.io"

4. (uuid in the template file adapt)

5. vmadm create -f smartos-docker-drawio.json
```

