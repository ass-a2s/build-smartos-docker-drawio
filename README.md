
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

SmartOS Docker (example)
========================

```
{
  "brand": "lx",
  "kernel_version": "3.16.0",
  "image_uuid": "d9a1e024-1c5c-dfd8-cf26-a6e0bbe4c77d",
  "autoboot": true,
  "alias": "root2-haproxy1-docker-drawio2",
  "hostname": "root2-haproxy1-docker-drawio2",
  "delegate_dataset": true,
  "dns_domain": "test.local",
  "resolvers": [
     "9.9.9.9",
     "149.112.112.112"
  ],
  "max_physical_memory": 4096,
  "max_swap": 4096,
  "tmpfs": 4096,
  "quota": 50,
  "cpu_cap": 200,
  "cpu_shares": 100,
  "max_lwps": 2000,
  "nics": [
     {
        "nic_tag": "haproxy1",
        "ip": "10.0.73.5",
        "ips": ["10.0.73.5/22", "addrconf"],
        "netmask": "255.255.252.0",
        "gateway": "10.0.72.100",
        "primary": true
     }
  ],
  "docker": "true",
  "internal_metadata": {
     "docker:cmd": "[\"catalina.sh\", \"run\"]",
     "docker:env": "[\"PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin\", \"LANG=C.UTF-8\", \"JAVA_HOME=/docker-java-home\", \"JAVA_VERSION=10.0.2+13\",  \"JAVA_DEBIAN_VERSION=10.0.2+13-1\", \"CATALINA_HOME=/usr/local/tomcat\", \"TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib\", \"LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib\", \"OPENSSL_VERSION=1.1.0f-3+deb9u2\", \"GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 9BA44C2621385CB966EBA586F72C284D731FABEE A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23\", \"TOMCAT_MAJOR=9\", \"TOMCAT_VERSION=9.0.10\", \"TOMCAT_SHA512=ecdee920fcb75bf30cd87c350e0732e8fa566911cd16cf2759689edd324ebac911c0d154e79ffc67e948b29eacc49c88dadc5954383d3c4af2fdb952f3d1c371\", \"TOMCAT_TGZ_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.10/bin/apache-tomcat-9.0.10.tar.gz \thttps://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.10/bin/apache-tomcat-9.0.10.tar.gz \thttps://www.apache.org/dist/tomcat/tomcat-9/v9.0.10/bin/apache-tomcat-9.0.10.tar.gz \thttps://archive.apache.org/dist/tomcat/tomcat-9/v9.0.10/bin/apache-tomcat-9.0.10.tar.gz\", \"TOMCAT_ASC_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.10/bin/apache-tomcat-9.0.10.tar.gz.asc \thttps://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.10/bin/apache-tomcat-9.0.10.tar.gz.asc \thttps://www.apache.org/dist/tomcat/tomcat-9/v9.0.10/bin/apache-tomcat-9.0.10.tar.gz.asc \thttps://archive.apache.org/dist/tomcat/tomcat-9/v9.0.10/bin/apache-tomcat-9.0.10.tar.gz.asc\"]",
     "docker:workingdir": "/usr/local/tomcat",
     "docker:workdir": "/data",
     "docker:tty": true,
     "docker:attach_stdin": true,
     "docker:attach_stdout": true,
     "docker:attach_stderr": true,
     "docker:open_stdin": true
  }
}
```

