## `telegraf:alpine`

```console
$ docker pull telegraf@sha256:2b93bed047fec948e7880243dea73ca6675b0b47710d5645daf1a376a952274b
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `telegraf:alpine` - linux; amd64

```console
$ docker pull telegraf@sha256:99ad33dd9279d0cd0a2959ee7991c7dae8d22da61113aed2c860dcdb50fbe9b5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **15.8 MB (15833690 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fbc5b10f2e8362ca7a0c55f0ecbbba85f7af2f8868bd23a2adc7466f33c09431`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:25 GMT
ADD file:eceadb32d029164d23db918d14c88df7186b6ee9645fa2f0c0a7e3e046a6a129 in / 
# Fri, 06 Jul 2018 14:13:25 GMT
CMD ["/bin/sh"]
# Thu, 30 Aug 2018 22:02:41 GMT
RUN echo 'hosts: files dns' >> /etc/nsswitch.conf
# Fri, 31 Aug 2018 18:20:37 GMT
RUN apk add --no-cache iputils ca-certificates net-snmp-tools procps lm_sensors &&     update-ca-certificates
# Fri, 31 Aug 2018 18:21:08 GMT
ENV TELEGRAF_VERSION=1.7.4
# Fri, 31 Aug 2018 18:21:15 GMT
RUN set -ex &&     apk add --no-cache --virtual .build-deps wget gnupg tar &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done &&     wget --no-verbose https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc &&     wget --no-verbose https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src /etc/telegraf &&     tar -C /usr/src -xzf telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mv /usr/src/telegraf*/telegraf.conf /etc/telegraf/ &&     chmod +x /usr/src/telegraf*/* &&     cp -a /usr/src/telegraf*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Fri, 31 Aug 2018 18:21:15 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Fri, 31 Aug 2018 18:21:16 GMT
COPY file:43e6828e001b57ab465cff8dfd3d30830289afe7ca5944b61641956bfe38cd1c in /entrypoint.sh 
# Fri, 31 Aug 2018 18:21:16 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Fri, 31 Aug 2018 18:21:16 GMT
CMD ["telegraf"]
```

-	Layers:
	-	`sha256:a073c86ecf9e0f29180e80e9638d4c741970695851ea48247276c32c57e40282`  
		Last Modified: Fri, 06 Jul 2018 14:16:26 GMT  
		Size: 2.0 MB (2014658 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a72645f13036d032a355da86f6dbd210460b976b408bd03617c93bf67107a4b0`  
		Last Modified: Thu, 30 Aug 2018 22:05:03 GMT  
		Size: 155.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33ddf12af64a8b8a015b9774eee480fb87cbfe1bbdbc7296d24333a1f27703c6`  
		Last Modified: Fri, 31 Aug 2018 18:21:34 GMT  
		Size: 3.4 MB (3354125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71e384f882c4f2ec60fdc0a1dfed4c93475e815adf1c83298d596276ba22c246`  
		Last Modified: Fri, 31 Aug 2018 18:22:15 GMT  
		Size: 10.5 MB (10464569 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d7688d4c8f66801ec27d435ad417fe5aa16fb6b901b47e8f2a9b1263d5af8de`  
		Last Modified: Fri, 31 Aug 2018 18:22:13 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
