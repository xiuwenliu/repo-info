<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `bonita`

-	[`bonita:7.6`](#bonita76)
-	[`bonita:7.6.3`](#bonita763)
-	[`bonita:7.7`](#bonita77)
-	[`bonita:7.7.3`](#bonita773)
-	[`bonita:latest`](#bonitalatest)

## `bonita:7.6`

```console
$ docker pull bonita@sha256:261aa6168642cfae76cf7de8610bbb0af1753ded3dd49a2882df94e095848991
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; ppc64le

### `bonita:7.6` - linux; amd64

```console
$ docker pull bonita@sha256:9bf4bcb0e87e97492910410e0404d3e0b3f7b86c9ad4403df50364f8a0e1aa77
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **215.1 MB (215063958 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:04e159d3b1790aaf740eb9de8a96646fef49544610a9ce9253cb80884e3e2da9`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Wed, 22 Aug 2018 17:31:28 GMT
ADD file:a83ab1826f43e88bc0d3ab6230f14cb9b2dacab70c762c3bfc555eda733b292c in / 
# Wed, 22 Aug 2018 17:31:29 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 22 Aug 2018 17:31:30 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:31:31 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 22 Aug 2018 17:31:32 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 22 Aug 2018 17:31:32 GMT
CMD ["/bin/bash"]
# Wed, 22 Aug 2018 17:54:06 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Wed, 22 Aug 2018 17:55:57 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:55:59 GMT
RUN mkdir /opt/custom-init.d/
# Wed, 22 Aug 2018 17:56:00 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Wed, 22 Aug 2018 17:56:01 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Wed, 22 Aug 2018 17:56:05 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_VERSION
# Wed, 22 Aug 2018 17:56:06 GMT
ARG TOMCAT_VERSION
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_SHA256
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_URL
# Wed, 22 Aug 2018 17:56:07 GMT
ENV BONITA_VERSION=7.6.3
# Wed, 22 Aug 2018 17:56:07 GMT
ENV TOMCAT_VERSION=8.5.23
# Wed, 22 Aug 2018 17:56:07 GMT
ENV BONITA_SHA256=54c6ed105b31a216a7db513bc16abc06f8c003ea9223329285a410158e8c52fc
# Wed, 22 Aug 2018 17:56:07 GMT
ENV BONITA_URL=https://download.forge.ow2.org/bonita/BonitaCommunity-7.6.3-Tomcat-8.5.23.zip
# Wed, 22 Aug 2018 17:56:21 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Wed, 22 Aug 2018 17:56:23 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Wed, 22 Aug 2018 17:56:25 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Wed, 22 Aug 2018 17:56:25 GMT
VOLUME [/opt/bonita]
# Wed, 22 Aug 2018 17:56:25 GMT
COPY dir:7d4489797b9c870351f0d813919cdacca2e45124e7f6a4a471b76d0b14b843d6 in /opt/files 
# Wed, 22 Aug 2018 17:56:26 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Wed, 22 Aug 2018 17:56:26 GMT
EXPOSE 8080/tcp
# Wed, 22 Aug 2018 17:56:26 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:3b37166ec61459e76e33282dda08f2a9cd698ca7e3d6bc44e6a6e7580cdeff8e`  
		Last Modified: Fri, 10 Aug 2018 22:11:36 GMT  
		Size: 43.3 MB (43252507 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba077e1ddb3aa8b95b2ecc5e58830800af4f5c06a5a37a3b7d7e0a67e178fb65`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34c83d2bc656952f573cee825d42e58622909b4be524b653f4f3df7464e57aa2`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 616.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84b69b6e47437924b207458fe7fc8f66812622983ae5a5d84bfdd2d83a9581e1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f72e97e1f61face716660657e4df5f70c2008a0b8b89e35dc6a460124fe01d1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b3941d0e4d6787f54c318480d145352e50c6ea92bc99dcb0e4e79e6655dd5a4`  
		Last Modified: Wed, 22 Aug 2018 17:58:21 GMT  
		Size: 82.8 MB (82836684 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d86ec4eedeb6664ea04f4d481f9c75e603b9154434f4458ce463d2deef59056b`  
		Last Modified: Wed, 22 Aug 2018 17:57:54 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00d47462548fe72ddcc0eb86cadb04e6b8dd5d73922d68124949a8d32bf0996d`  
		Last Modified: Wed, 22 Aug 2018 17:57:53 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bd34dc86fe233101d4f453ea9c76ce132a570be3421e074e91fd07780eb156c`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 140.6 KB (140588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:493f5f5f4be43dd73397fbfe3740caebdb4d0c71d32ddcd20cc11677cf6c36f7`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 500.7 KB (500740 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f0906ea599ce3d29bc452fa606052baeee71c9230d26d87551d13fc846210cdc`  
		Last Modified: Wed, 22 Aug 2018 17:58:00 GMT  
		Size: 88.3 MB (88320710 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:470ab4dfde3101770ed43abbb98728fdd1cbe5bdcb0c88d379df164e7f1c0b9d`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 6.4 KB (6395 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c18c66d397bb884d524b714cd6dd25ed6e243d0da5f7c5762f64223ebb420d9b`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 1.7 KB (1684 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `bonita:7.6` - linux; arm64 variant v8

```console
$ docker pull bonita@sha256:dc776c2fc7559bdbf91743cf885b9de34d12d386d15b8f2b6ed76ed3064b2cb2
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **201.9 MB (201861381 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:479cf98c7536a93e87a5ce45723521286b06f5d9f3ec3c2b88efcba75fc2b7c9`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 23 Aug 2018 18:00:02 GMT
ADD file:e5010797ac02efecbf22dd21592880fd5283c01d177c3f0d1274c6397683f8f0 in / 
# Thu, 23 Aug 2018 18:00:04 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 18:00:06 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 18:00:08 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 18:00:10 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 18:00:11 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 22:18:57 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 23 Aug 2018 22:21:18 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 22:21:25 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 23 Aug 2018 22:21:28 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 23 Aug 2018 22:21:48 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 23 Aug 2018 22:21:53 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 23 Aug 2018 22:22:09 GMT
ARG BONITA_VERSION
# Thu, 23 Aug 2018 22:22:10 GMT
ARG TOMCAT_VERSION
# Thu, 23 Aug 2018 22:22:10 GMT
ARG BONITA_SHA256
# Thu, 23 Aug 2018 22:22:11 GMT
ARG BONITA_URL
# Thu, 23 Aug 2018 22:22:12 GMT
ENV BONITA_VERSION=7.6.3
# Thu, 23 Aug 2018 22:22:13 GMT
ENV TOMCAT_VERSION=8.5.23
# Thu, 23 Aug 2018 22:22:14 GMT
ENV BONITA_SHA256=54c6ed105b31a216a7db513bc16abc06f8c003ea9223329285a410158e8c52fc
# Thu, 23 Aug 2018 22:22:14 GMT
ENV BONITA_URL=https://download.forge.ow2.org/bonita/BonitaCommunity-7.6.3-Tomcat-8.5.23.zip
# Thu, 23 Aug 2018 22:22:42 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 22:22:45 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 22:23:06 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 23 Aug 2018 22:23:06 GMT
VOLUME [/opt/bonita]
# Thu, 23 Aug 2018 22:23:27 GMT
COPY dir:7d4489797b9c870351f0d813919cdacca2e45124e7f6a4a471b76d0b14b843d6 in /opt/files 
# Thu, 23 Aug 2018 22:23:28 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Thu, 23 Aug 2018 22:23:29 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 22:23:49 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:672a69505838a80ab1d16038f6268944bf913e2b9df67785f4f560145b243625`  
		Last Modified: Fri, 10 Aug 2018 22:12:34 GMT  
		Size: 39.4 MB (39381352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:958416e5b29b0395ebf84d5442b4a440207871d06ab7b5b475bbfcbc64625d16`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b9b2df41f722dc826e75f4e3fadac77f1487ed4e1254e92645e664d785662036`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 538.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ea051153c5ecf9f78bc0528c6f4917ae8a6bb1910be9c1e23926fa80704160a`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7bdeb5fe2e665aecb71278bdb333b15048b051370afe97929d4abf456e456a22`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ccfb9f28b47f919b20dab3fe0f436a6a1bea3d91be3a0a4964989d3ce83fed2`  
		Last Modified: Thu, 23 Aug 2018 22:27:32 GMT  
		Size: 73.5 MB (73537277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23d26be524bf12625935ae607440747a952773d61c8f038d31faa8b442ae064f`  
		Last Modified: Thu, 23 Aug 2018 22:27:10 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b6a65f40d10b47d7409c91f0c934d17b5faca150e8a4b3b66eb50268722efe3`  
		Last Modified: Thu, 23 Aug 2018 22:27:09 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c466ee9e085c26be745f4ab66f688b669ee0eac208c4f23f7c891e28ae5b17c`  
		Last Modified: Thu, 23 Aug 2018 22:27:06 GMT  
		Size: 140.6 KB (140587 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87e2a88ed077d6ee1ffa243d1cff3121a5157b3606f2e781bad602dcf738eb81`  
		Last Modified: Thu, 23 Aug 2018 22:27:07 GMT  
		Size: 468.8 KB (468794 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7c787ac7b1bf9c4935ac776ba8abbb135a538018c07a4b8002770236366575d3`  
		Last Modified: Thu, 23 Aug 2018 22:27:18 GMT  
		Size: 88.3 MB (88320706 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b416a4fcf7b2c4f1fe1a651d829b27709f890769521aeac3e3fe3064401652b3`  
		Last Modified: Thu, 23 Aug 2018 22:27:07 GMT  
		Size: 6.4 KB (6395 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9364697cb03ba7ceeae317fab19868509ad7fd4bdbb15f098459329d911da784`  
		Last Modified: Thu, 23 Aug 2018 22:27:07 GMT  
		Size: 1.7 KB (1683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `bonita:7.6` - linux; ppc64le

```console
$ docker pull bonita@sha256:9dcf6ee760d8053d95da53db2355e8df3aa6e628c0fa8044afcfdf6bacea7b42
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **211.8 MB (211838674 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:45f111003e89c39dee8f0da38d432740ff23b2549bfd8279bf9ae2c5dc1f9965`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 23 Aug 2018 12:50:13 GMT
ADD file:b09779db95ed098d4ff481c60f9070c9855d49079531c872f7f306766b31a320 in / 
# Thu, 23 Aug 2018 12:50:19 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 12:50:22 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 12:50:25 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 12:50:29 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 12:50:31 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 15:54:12 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 23 Aug 2018 16:01:33 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 16:02:03 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 23 Aug 2018 16:02:14 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 23 Aug 2018 16:02:24 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 23 Aug 2018 16:02:34 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 23 Aug 2018 16:02:36 GMT
ARG BONITA_VERSION
# Thu, 23 Aug 2018 16:02:39 GMT
ARG TOMCAT_VERSION
# Thu, 23 Aug 2018 16:02:44 GMT
ARG BONITA_SHA256
# Thu, 23 Aug 2018 16:02:47 GMT
ARG BONITA_URL
# Thu, 23 Aug 2018 16:02:48 GMT
ENV BONITA_VERSION=7.6.3
# Thu, 23 Aug 2018 16:02:59 GMT
ENV TOMCAT_VERSION=8.5.23
# Thu, 23 Aug 2018 16:03:13 GMT
ENV BONITA_SHA256=54c6ed105b31a216a7db513bc16abc06f8c003ea9223329285a410158e8c52fc
# Thu, 23 Aug 2018 16:03:31 GMT
ENV BONITA_URL=https://download.forge.ow2.org/bonita/BonitaCommunity-7.6.3-Tomcat-8.5.23.zip
# Thu, 23 Aug 2018 16:04:53 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 16:05:09 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 16:05:26 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 23 Aug 2018 16:05:31 GMT
VOLUME [/opt/bonita]
# Thu, 23 Aug 2018 16:05:36 GMT
COPY dir:7d4489797b9c870351f0d813919cdacca2e45124e7f6a4a471b76d0b14b843d6 in /opt/files 
# Thu, 23 Aug 2018 16:05:39 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Thu, 23 Aug 2018 16:05:42 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 16:05:43 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:0d0dbb9a021cbff2129dab2bc36f95d25c2bde53c72d61c87f45f4b14b810ebc`  
		Last Modified: Thu, 23 Aug 2018 12:53:07 GMT  
		Size: 45.6 MB (45595505 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5cb08b3a0bd0961e0ecbe16b6c544124a22f1beca9f3621f59e5cd5e2346d49`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10066c30deaec81ef942231f5f84b5782b7cf7bcf78c389453617b7265465be2`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 579.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d604dc40c1d1c57ec0ba6faed21bc3b4e8ea4fa54eb547fbc134e7c73d468203`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 857.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12b9507f41bb4395530111a162394310249dfe8f51e0682c9c17747c09ff12f6`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c75e673f0cae40f078ff4c0bcfbca227aa9d334d42e80076c32c305d2ebb0440`  
		Last Modified: Thu, 23 Aug 2018 16:09:52 GMT  
		Size: 77.3 MB (77299108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9afea67a042db7e888ebbe0b4edb1e1af872e22ecadd4eea989f79546b5f8e1`  
		Last Modified: Thu, 23 Aug 2018 16:09:29 GMT  
		Size: 156.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80ae3f536d5e73d2c4a09b14f647aa3c6aeabaf4e319d36a6c990f53c612f346`  
		Last Modified: Thu, 23 Aug 2018 16:09:26 GMT  
		Size: 2.1 KB (2055 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b73165c62a51426107c72136a92a5d65a1666fefa9bc816280d1b129a890e5ef`  
		Last Modified: Thu, 23 Aug 2018 16:09:09 GMT  
		Size: 140.6 KB (140608 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:baa6822e1a23a13369ff5ab3f4f09c1fd6a66f63b8182460410f568ddefb248c`  
		Last Modified: Thu, 23 Aug 2018 16:09:08 GMT  
		Size: 469.9 KB (469926 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:179e71f0f435d5ed4be7beb29478d14df0d1e39f502dcaa223b4badf7f631b19`  
		Last Modified: Thu, 23 Aug 2018 16:09:16 GMT  
		Size: 88.3 MB (88320727 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ad75fc139ab279e859b5f35c238e31974324be424a625da5001ca9e5d7dc8d2`  
		Last Modified: Thu, 23 Aug 2018 16:09:08 GMT  
		Size: 6.4 KB (6421 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:666fc070e46f37a96bfa0582a7ceacb7dcbf16076bc2544fe922cf14c26b1081`  
		Last Modified: Thu, 23 Aug 2018 16:09:08 GMT  
		Size: 1.7 KB (1710 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `bonita:7.6.3`

```console
$ docker pull bonita@sha256:261aa6168642cfae76cf7de8610bbb0af1753ded3dd49a2882df94e095848991
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; ppc64le

### `bonita:7.6.3` - linux; amd64

```console
$ docker pull bonita@sha256:9bf4bcb0e87e97492910410e0404d3e0b3f7b86c9ad4403df50364f8a0e1aa77
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **215.1 MB (215063958 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:04e159d3b1790aaf740eb9de8a96646fef49544610a9ce9253cb80884e3e2da9`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Wed, 22 Aug 2018 17:31:28 GMT
ADD file:a83ab1826f43e88bc0d3ab6230f14cb9b2dacab70c762c3bfc555eda733b292c in / 
# Wed, 22 Aug 2018 17:31:29 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 22 Aug 2018 17:31:30 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:31:31 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 22 Aug 2018 17:31:32 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 22 Aug 2018 17:31:32 GMT
CMD ["/bin/bash"]
# Wed, 22 Aug 2018 17:54:06 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Wed, 22 Aug 2018 17:55:57 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:55:59 GMT
RUN mkdir /opt/custom-init.d/
# Wed, 22 Aug 2018 17:56:00 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Wed, 22 Aug 2018 17:56:01 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Wed, 22 Aug 2018 17:56:05 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_VERSION
# Wed, 22 Aug 2018 17:56:06 GMT
ARG TOMCAT_VERSION
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_SHA256
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_URL
# Wed, 22 Aug 2018 17:56:07 GMT
ENV BONITA_VERSION=7.6.3
# Wed, 22 Aug 2018 17:56:07 GMT
ENV TOMCAT_VERSION=8.5.23
# Wed, 22 Aug 2018 17:56:07 GMT
ENV BONITA_SHA256=54c6ed105b31a216a7db513bc16abc06f8c003ea9223329285a410158e8c52fc
# Wed, 22 Aug 2018 17:56:07 GMT
ENV BONITA_URL=https://download.forge.ow2.org/bonita/BonitaCommunity-7.6.3-Tomcat-8.5.23.zip
# Wed, 22 Aug 2018 17:56:21 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Wed, 22 Aug 2018 17:56:23 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Wed, 22 Aug 2018 17:56:25 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Wed, 22 Aug 2018 17:56:25 GMT
VOLUME [/opt/bonita]
# Wed, 22 Aug 2018 17:56:25 GMT
COPY dir:7d4489797b9c870351f0d813919cdacca2e45124e7f6a4a471b76d0b14b843d6 in /opt/files 
# Wed, 22 Aug 2018 17:56:26 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Wed, 22 Aug 2018 17:56:26 GMT
EXPOSE 8080/tcp
# Wed, 22 Aug 2018 17:56:26 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:3b37166ec61459e76e33282dda08f2a9cd698ca7e3d6bc44e6a6e7580cdeff8e`  
		Last Modified: Fri, 10 Aug 2018 22:11:36 GMT  
		Size: 43.3 MB (43252507 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba077e1ddb3aa8b95b2ecc5e58830800af4f5c06a5a37a3b7d7e0a67e178fb65`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34c83d2bc656952f573cee825d42e58622909b4be524b653f4f3df7464e57aa2`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 616.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84b69b6e47437924b207458fe7fc8f66812622983ae5a5d84bfdd2d83a9581e1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f72e97e1f61face716660657e4df5f70c2008a0b8b89e35dc6a460124fe01d1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b3941d0e4d6787f54c318480d145352e50c6ea92bc99dcb0e4e79e6655dd5a4`  
		Last Modified: Wed, 22 Aug 2018 17:58:21 GMT  
		Size: 82.8 MB (82836684 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d86ec4eedeb6664ea04f4d481f9c75e603b9154434f4458ce463d2deef59056b`  
		Last Modified: Wed, 22 Aug 2018 17:57:54 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00d47462548fe72ddcc0eb86cadb04e6b8dd5d73922d68124949a8d32bf0996d`  
		Last Modified: Wed, 22 Aug 2018 17:57:53 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bd34dc86fe233101d4f453ea9c76ce132a570be3421e074e91fd07780eb156c`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 140.6 KB (140588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:493f5f5f4be43dd73397fbfe3740caebdb4d0c71d32ddcd20cc11677cf6c36f7`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 500.7 KB (500740 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f0906ea599ce3d29bc452fa606052baeee71c9230d26d87551d13fc846210cdc`  
		Last Modified: Wed, 22 Aug 2018 17:58:00 GMT  
		Size: 88.3 MB (88320710 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:470ab4dfde3101770ed43abbb98728fdd1cbe5bdcb0c88d379df164e7f1c0b9d`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 6.4 KB (6395 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c18c66d397bb884d524b714cd6dd25ed6e243d0da5f7c5762f64223ebb420d9b`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 1.7 KB (1684 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `bonita:7.6.3` - linux; arm64 variant v8

```console
$ docker pull bonita@sha256:dc776c2fc7559bdbf91743cf885b9de34d12d386d15b8f2b6ed76ed3064b2cb2
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **201.9 MB (201861381 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:479cf98c7536a93e87a5ce45723521286b06f5d9f3ec3c2b88efcba75fc2b7c9`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 23 Aug 2018 18:00:02 GMT
ADD file:e5010797ac02efecbf22dd21592880fd5283c01d177c3f0d1274c6397683f8f0 in / 
# Thu, 23 Aug 2018 18:00:04 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 18:00:06 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 18:00:08 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 18:00:10 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 18:00:11 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 22:18:57 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 23 Aug 2018 22:21:18 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 22:21:25 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 23 Aug 2018 22:21:28 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 23 Aug 2018 22:21:48 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 23 Aug 2018 22:21:53 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 23 Aug 2018 22:22:09 GMT
ARG BONITA_VERSION
# Thu, 23 Aug 2018 22:22:10 GMT
ARG TOMCAT_VERSION
# Thu, 23 Aug 2018 22:22:10 GMT
ARG BONITA_SHA256
# Thu, 23 Aug 2018 22:22:11 GMT
ARG BONITA_URL
# Thu, 23 Aug 2018 22:22:12 GMT
ENV BONITA_VERSION=7.6.3
# Thu, 23 Aug 2018 22:22:13 GMT
ENV TOMCAT_VERSION=8.5.23
# Thu, 23 Aug 2018 22:22:14 GMT
ENV BONITA_SHA256=54c6ed105b31a216a7db513bc16abc06f8c003ea9223329285a410158e8c52fc
# Thu, 23 Aug 2018 22:22:14 GMT
ENV BONITA_URL=https://download.forge.ow2.org/bonita/BonitaCommunity-7.6.3-Tomcat-8.5.23.zip
# Thu, 23 Aug 2018 22:22:42 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 22:22:45 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 22:23:06 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 23 Aug 2018 22:23:06 GMT
VOLUME [/opt/bonita]
# Thu, 23 Aug 2018 22:23:27 GMT
COPY dir:7d4489797b9c870351f0d813919cdacca2e45124e7f6a4a471b76d0b14b843d6 in /opt/files 
# Thu, 23 Aug 2018 22:23:28 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Thu, 23 Aug 2018 22:23:29 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 22:23:49 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:672a69505838a80ab1d16038f6268944bf913e2b9df67785f4f560145b243625`  
		Last Modified: Fri, 10 Aug 2018 22:12:34 GMT  
		Size: 39.4 MB (39381352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:958416e5b29b0395ebf84d5442b4a440207871d06ab7b5b475bbfcbc64625d16`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b9b2df41f722dc826e75f4e3fadac77f1487ed4e1254e92645e664d785662036`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 538.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ea051153c5ecf9f78bc0528c6f4917ae8a6bb1910be9c1e23926fa80704160a`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7bdeb5fe2e665aecb71278bdb333b15048b051370afe97929d4abf456e456a22`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ccfb9f28b47f919b20dab3fe0f436a6a1bea3d91be3a0a4964989d3ce83fed2`  
		Last Modified: Thu, 23 Aug 2018 22:27:32 GMT  
		Size: 73.5 MB (73537277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23d26be524bf12625935ae607440747a952773d61c8f038d31faa8b442ae064f`  
		Last Modified: Thu, 23 Aug 2018 22:27:10 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b6a65f40d10b47d7409c91f0c934d17b5faca150e8a4b3b66eb50268722efe3`  
		Last Modified: Thu, 23 Aug 2018 22:27:09 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c466ee9e085c26be745f4ab66f688b669ee0eac208c4f23f7c891e28ae5b17c`  
		Last Modified: Thu, 23 Aug 2018 22:27:06 GMT  
		Size: 140.6 KB (140587 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87e2a88ed077d6ee1ffa243d1cff3121a5157b3606f2e781bad602dcf738eb81`  
		Last Modified: Thu, 23 Aug 2018 22:27:07 GMT  
		Size: 468.8 KB (468794 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7c787ac7b1bf9c4935ac776ba8abbb135a538018c07a4b8002770236366575d3`  
		Last Modified: Thu, 23 Aug 2018 22:27:18 GMT  
		Size: 88.3 MB (88320706 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b416a4fcf7b2c4f1fe1a651d829b27709f890769521aeac3e3fe3064401652b3`  
		Last Modified: Thu, 23 Aug 2018 22:27:07 GMT  
		Size: 6.4 KB (6395 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9364697cb03ba7ceeae317fab19868509ad7fd4bdbb15f098459329d911da784`  
		Last Modified: Thu, 23 Aug 2018 22:27:07 GMT  
		Size: 1.7 KB (1683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `bonita:7.6.3` - linux; ppc64le

```console
$ docker pull bonita@sha256:9dcf6ee760d8053d95da53db2355e8df3aa6e628c0fa8044afcfdf6bacea7b42
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **211.8 MB (211838674 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:45f111003e89c39dee8f0da38d432740ff23b2549bfd8279bf9ae2c5dc1f9965`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 23 Aug 2018 12:50:13 GMT
ADD file:b09779db95ed098d4ff481c60f9070c9855d49079531c872f7f306766b31a320 in / 
# Thu, 23 Aug 2018 12:50:19 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 12:50:22 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 12:50:25 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 12:50:29 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 12:50:31 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 15:54:12 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 23 Aug 2018 16:01:33 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 16:02:03 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 23 Aug 2018 16:02:14 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 23 Aug 2018 16:02:24 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 23 Aug 2018 16:02:34 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 23 Aug 2018 16:02:36 GMT
ARG BONITA_VERSION
# Thu, 23 Aug 2018 16:02:39 GMT
ARG TOMCAT_VERSION
# Thu, 23 Aug 2018 16:02:44 GMT
ARG BONITA_SHA256
# Thu, 23 Aug 2018 16:02:47 GMT
ARG BONITA_URL
# Thu, 23 Aug 2018 16:02:48 GMT
ENV BONITA_VERSION=7.6.3
# Thu, 23 Aug 2018 16:02:59 GMT
ENV TOMCAT_VERSION=8.5.23
# Thu, 23 Aug 2018 16:03:13 GMT
ENV BONITA_SHA256=54c6ed105b31a216a7db513bc16abc06f8c003ea9223329285a410158e8c52fc
# Thu, 23 Aug 2018 16:03:31 GMT
ENV BONITA_URL=https://download.forge.ow2.org/bonita/BonitaCommunity-7.6.3-Tomcat-8.5.23.zip
# Thu, 23 Aug 2018 16:04:53 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 16:05:09 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 16:05:26 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 23 Aug 2018 16:05:31 GMT
VOLUME [/opt/bonita]
# Thu, 23 Aug 2018 16:05:36 GMT
COPY dir:7d4489797b9c870351f0d813919cdacca2e45124e7f6a4a471b76d0b14b843d6 in /opt/files 
# Thu, 23 Aug 2018 16:05:39 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Thu, 23 Aug 2018 16:05:42 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 16:05:43 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:0d0dbb9a021cbff2129dab2bc36f95d25c2bde53c72d61c87f45f4b14b810ebc`  
		Last Modified: Thu, 23 Aug 2018 12:53:07 GMT  
		Size: 45.6 MB (45595505 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5cb08b3a0bd0961e0ecbe16b6c544124a22f1beca9f3621f59e5cd5e2346d49`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10066c30deaec81ef942231f5f84b5782b7cf7bcf78c389453617b7265465be2`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 579.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d604dc40c1d1c57ec0ba6faed21bc3b4e8ea4fa54eb547fbc134e7c73d468203`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 857.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12b9507f41bb4395530111a162394310249dfe8f51e0682c9c17747c09ff12f6`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c75e673f0cae40f078ff4c0bcfbca227aa9d334d42e80076c32c305d2ebb0440`  
		Last Modified: Thu, 23 Aug 2018 16:09:52 GMT  
		Size: 77.3 MB (77299108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9afea67a042db7e888ebbe0b4edb1e1af872e22ecadd4eea989f79546b5f8e1`  
		Last Modified: Thu, 23 Aug 2018 16:09:29 GMT  
		Size: 156.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80ae3f536d5e73d2c4a09b14f647aa3c6aeabaf4e319d36a6c990f53c612f346`  
		Last Modified: Thu, 23 Aug 2018 16:09:26 GMT  
		Size: 2.1 KB (2055 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b73165c62a51426107c72136a92a5d65a1666fefa9bc816280d1b129a890e5ef`  
		Last Modified: Thu, 23 Aug 2018 16:09:09 GMT  
		Size: 140.6 KB (140608 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:baa6822e1a23a13369ff5ab3f4f09c1fd6a66f63b8182460410f568ddefb248c`  
		Last Modified: Thu, 23 Aug 2018 16:09:08 GMT  
		Size: 469.9 KB (469926 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:179e71f0f435d5ed4be7beb29478d14df0d1e39f502dcaa223b4badf7f631b19`  
		Last Modified: Thu, 23 Aug 2018 16:09:16 GMT  
		Size: 88.3 MB (88320727 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ad75fc139ab279e859b5f35c238e31974324be424a625da5001ca9e5d7dc8d2`  
		Last Modified: Thu, 23 Aug 2018 16:09:08 GMT  
		Size: 6.4 KB (6421 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:666fc070e46f37a96bfa0582a7ceacb7dcbf16076bc2544fe922cf14c26b1081`  
		Last Modified: Thu, 23 Aug 2018 16:09:08 GMT  
		Size: 1.7 KB (1710 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `bonita:7.7`

```console
$ docker pull bonita@sha256:00598cb1c966ba87e06be2a5c189a7b5cb15deb04dea22be5deaf6c74906abce
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; ppc64le

### `bonita:7.7` - linux; amd64

```console
$ docker pull bonita@sha256:3c9311b1a4c307e9a05a93ec4434314d2eff2b58a1b5839db59939b2b5b4445d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **214.6 MB (214562181 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bc41b54e564f3cc28de1f28be9df6d74c3797a77853baf04e29999f990858d74`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Wed, 22 Aug 2018 17:31:28 GMT
ADD file:a83ab1826f43e88bc0d3ab6230f14cb9b2dacab70c762c3bfc555eda733b292c in / 
# Wed, 22 Aug 2018 17:31:29 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 22 Aug 2018 17:31:30 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:31:31 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 22 Aug 2018 17:31:32 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 22 Aug 2018 17:31:32 GMT
CMD ["/bin/bash"]
# Wed, 22 Aug 2018 17:54:06 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Wed, 22 Aug 2018 17:55:57 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:55:59 GMT
RUN mkdir /opt/custom-init.d/
# Wed, 22 Aug 2018 17:56:00 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Wed, 22 Aug 2018 17:56:01 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Wed, 22 Aug 2018 17:56:05 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_VERSION
# Wed, 22 Aug 2018 17:56:06 GMT
ARG TOMCAT_VERSION
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_SHA256
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_URL
# Wed, 22 Aug 2018 17:56:48 GMT
ENV BONITA_VERSION=7.7.3
# Wed, 22 Aug 2018 17:56:48 GMT
ENV TOMCAT_VERSION=8.5.31
# Wed, 22 Aug 2018 17:56:48 GMT
ENV BONITA_SHA256=a2c5c13359e90a99b143848b650be0cbee1b9bb6cfa9666904c123fc6d1e30a6
# Wed, 22 Aug 2018 17:56:48 GMT
ENV BONITA_URL=https://release.ow2.org/bonita/BonitaCommunity-7.7.3-Tomcat-8.5.31.zip
# Wed, 22 Aug 2018 17:57:00 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Wed, 22 Aug 2018 17:57:23 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Wed, 22 Aug 2018 17:57:25 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Wed, 22 Aug 2018 17:57:25 GMT
VOLUME [/opt/bonita]
# Wed, 22 Aug 2018 17:57:26 GMT
COPY dir:54e2aa3a901daf192e4916306de581c3b5abe3185f3c0ef0386107f80837ec74 in /opt/files 
# Wed, 22 Aug 2018 17:57:26 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Wed, 22 Aug 2018 17:57:26 GMT
EXPOSE 8080/tcp
# Wed, 22 Aug 2018 17:57:27 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:3b37166ec61459e76e33282dda08f2a9cd698ca7e3d6bc44e6a6e7580cdeff8e`  
		Last Modified: Fri, 10 Aug 2018 22:11:36 GMT  
		Size: 43.3 MB (43252507 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba077e1ddb3aa8b95b2ecc5e58830800af4f5c06a5a37a3b7d7e0a67e178fb65`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34c83d2bc656952f573cee825d42e58622909b4be524b653f4f3df7464e57aa2`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 616.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84b69b6e47437924b207458fe7fc8f66812622983ae5a5d84bfdd2d83a9581e1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f72e97e1f61face716660657e4df5f70c2008a0b8b89e35dc6a460124fe01d1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b3941d0e4d6787f54c318480d145352e50c6ea92bc99dcb0e4e79e6655dd5a4`  
		Last Modified: Wed, 22 Aug 2018 17:58:21 GMT  
		Size: 82.8 MB (82836684 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d86ec4eedeb6664ea04f4d481f9c75e603b9154434f4458ce463d2deef59056b`  
		Last Modified: Wed, 22 Aug 2018 17:57:54 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00d47462548fe72ddcc0eb86cadb04e6b8dd5d73922d68124949a8d32bf0996d`  
		Last Modified: Wed, 22 Aug 2018 17:57:53 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bd34dc86fe233101d4f453ea9c76ce132a570be3421e074e91fd07780eb156c`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 140.6 KB (140588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:493f5f5f4be43dd73397fbfe3740caebdb4d0c71d32ddcd20cc11677cf6c36f7`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 500.7 KB (500740 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a629406ed63f4a700a32150869cf1e2c96b00386ce71fb64773fcb872c67b63`  
		Last Modified: Wed, 22 Aug 2018 17:59:17 GMT  
		Size: 87.8 MB (87818924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:44eab2437acd1fa1366fa7ddfbeed5a20d0638135f3e11337907b4d048a61d1d`  
		Last Modified: Wed, 22 Aug 2018 17:59:08 GMT  
		Size: 6.4 KB (6403 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2725e7c4ac4c7cc0fa38e4a05c86c862f284e152e70088a2b4842ab76997310e`  
		Last Modified: Wed, 22 Aug 2018 17:59:07 GMT  
		Size: 1.7 KB (1685 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `bonita:7.7` - linux; arm64 variant v8

```console
$ docker pull bonita@sha256:a7b458ed225a83ef0706b458e3e874c5015c9302f96e8d6e9e716af9fdf3d8de
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **201.4 MB (201359608 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d2f90fe590184768901be188e48dd85afaf60c067cfd15ba9f32ddd0a2fd8d95`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 23 Aug 2018 18:00:02 GMT
ADD file:e5010797ac02efecbf22dd21592880fd5283c01d177c3f0d1274c6397683f8f0 in / 
# Thu, 23 Aug 2018 18:00:04 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 18:00:06 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 18:00:08 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 18:00:10 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 18:00:11 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 22:18:57 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 23 Aug 2018 22:21:18 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 22:21:25 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 23 Aug 2018 22:21:28 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 23 Aug 2018 22:21:48 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 23 Aug 2018 22:21:53 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 23 Aug 2018 22:22:09 GMT
ARG BONITA_VERSION
# Thu, 23 Aug 2018 22:22:10 GMT
ARG TOMCAT_VERSION
# Thu, 23 Aug 2018 22:22:10 GMT
ARG BONITA_SHA256
# Thu, 23 Aug 2018 22:22:11 GMT
ARG BONITA_URL
# Thu, 23 Aug 2018 22:24:31 GMT
ENV BONITA_VERSION=7.7.3
# Thu, 23 Aug 2018 22:24:32 GMT
ENV TOMCAT_VERSION=8.5.31
# Thu, 23 Aug 2018 22:24:33 GMT
ENV BONITA_SHA256=a2c5c13359e90a99b143848b650be0cbee1b9bb6cfa9666904c123fc6d1e30a6
# Thu, 23 Aug 2018 22:24:33 GMT
ENV BONITA_URL=https://release.ow2.org/bonita/BonitaCommunity-7.7.3-Tomcat-8.5.31.zip
# Thu, 23 Aug 2018 22:25:53 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 22:25:58 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 22:26:00 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 23 Aug 2018 22:26:01 GMT
VOLUME [/opt/bonita]
# Thu, 23 Aug 2018 22:26:02 GMT
COPY dir:54e2aa3a901daf192e4916306de581c3b5abe3185f3c0ef0386107f80837ec74 in /opt/files 
# Thu, 23 Aug 2018 22:26:03 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Thu, 23 Aug 2018 22:26:04 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 22:26:05 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:672a69505838a80ab1d16038f6268944bf913e2b9df67785f4f560145b243625`  
		Last Modified: Fri, 10 Aug 2018 22:12:34 GMT  
		Size: 39.4 MB (39381352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:958416e5b29b0395ebf84d5442b4a440207871d06ab7b5b475bbfcbc64625d16`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b9b2df41f722dc826e75f4e3fadac77f1487ed4e1254e92645e664d785662036`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 538.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ea051153c5ecf9f78bc0528c6f4917ae8a6bb1910be9c1e23926fa80704160a`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7bdeb5fe2e665aecb71278bdb333b15048b051370afe97929d4abf456e456a22`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ccfb9f28b47f919b20dab3fe0f436a6a1bea3d91be3a0a4964989d3ce83fed2`  
		Last Modified: Thu, 23 Aug 2018 22:27:32 GMT  
		Size: 73.5 MB (73537277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23d26be524bf12625935ae607440747a952773d61c8f038d31faa8b442ae064f`  
		Last Modified: Thu, 23 Aug 2018 22:27:10 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b6a65f40d10b47d7409c91f0c934d17b5faca150e8a4b3b66eb50268722efe3`  
		Last Modified: Thu, 23 Aug 2018 22:27:09 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c466ee9e085c26be745f4ab66f688b669ee0eac208c4f23f7c891e28ae5b17c`  
		Last Modified: Thu, 23 Aug 2018 22:27:06 GMT  
		Size: 140.6 KB (140587 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87e2a88ed077d6ee1ffa243d1cff3121a5157b3606f2e781bad602dcf738eb81`  
		Last Modified: Thu, 23 Aug 2018 22:27:07 GMT  
		Size: 468.8 KB (468794 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25b953ccb65b5856981f9a43fe8680cba3b1116b8e7a79605c08868e9029de8d`  
		Last Modified: Thu, 23 Aug 2018 22:28:34 GMT  
		Size: 87.8 MB (87818925 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c11df33243958e9cda4defdd099f5ab513aa51f95242dbf2eb9bca363d56ac30`  
		Last Modified: Thu, 23 Aug 2018 22:28:22 GMT  
		Size: 6.4 KB (6400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c523cef814681962a82097315b67c235ccabd02b6fc8628fb8d0843ccab22e5c`  
		Last Modified: Thu, 23 Aug 2018 22:28:21 GMT  
		Size: 1.7 KB (1686 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `bonita:7.7` - linux; ppc64le

```console
$ docker pull bonita@sha256:4db15ce69819b3f0bc89e469cd862c4ae6dddee53c48431d10106aa718f8cf32
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **211.3 MB (211336913 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f81b015b0179cd1e0ef1694876109a6cd5308276e7df5bd9549e621bcbd5090e`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 23 Aug 2018 12:50:13 GMT
ADD file:b09779db95ed098d4ff481c60f9070c9855d49079531c872f7f306766b31a320 in / 
# Thu, 23 Aug 2018 12:50:19 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 12:50:22 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 12:50:25 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 12:50:29 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 12:50:31 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 15:54:12 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 23 Aug 2018 16:01:33 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 16:02:03 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 23 Aug 2018 16:02:14 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 23 Aug 2018 16:02:24 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 23 Aug 2018 16:02:34 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 23 Aug 2018 16:02:36 GMT
ARG BONITA_VERSION
# Thu, 23 Aug 2018 16:02:39 GMT
ARG TOMCAT_VERSION
# Thu, 23 Aug 2018 16:02:44 GMT
ARG BONITA_SHA256
# Thu, 23 Aug 2018 16:02:47 GMT
ARG BONITA_URL
# Thu, 23 Aug 2018 16:05:59 GMT
ENV BONITA_VERSION=7.7.3
# Thu, 23 Aug 2018 16:06:03 GMT
ENV TOMCAT_VERSION=8.5.31
# Thu, 23 Aug 2018 16:06:05 GMT
ENV BONITA_SHA256=a2c5c13359e90a99b143848b650be0cbee1b9bb6cfa9666904c123fc6d1e30a6
# Thu, 23 Aug 2018 16:06:06 GMT
ENV BONITA_URL=https://release.ow2.org/bonita/BonitaCommunity-7.7.3-Tomcat-8.5.31.zip
# Thu, 23 Aug 2018 16:07:19 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 16:07:29 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 16:07:43 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 23 Aug 2018 16:07:45 GMT
VOLUME [/opt/bonita]
# Thu, 23 Aug 2018 16:08:12 GMT
COPY dir:54e2aa3a901daf192e4916306de581c3b5abe3185f3c0ef0386107f80837ec74 in /opt/files 
# Thu, 23 Aug 2018 16:08:25 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Thu, 23 Aug 2018 16:08:29 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 16:08:39 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:0d0dbb9a021cbff2129dab2bc36f95d25c2bde53c72d61c87f45f4b14b810ebc`  
		Last Modified: Thu, 23 Aug 2018 12:53:07 GMT  
		Size: 45.6 MB (45595505 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5cb08b3a0bd0961e0ecbe16b6c544124a22f1beca9f3621f59e5cd5e2346d49`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10066c30deaec81ef942231f5f84b5782b7cf7bcf78c389453617b7265465be2`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 579.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d604dc40c1d1c57ec0ba6faed21bc3b4e8ea4fa54eb547fbc134e7c73d468203`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 857.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12b9507f41bb4395530111a162394310249dfe8f51e0682c9c17747c09ff12f6`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c75e673f0cae40f078ff4c0bcfbca227aa9d334d42e80076c32c305d2ebb0440`  
		Last Modified: Thu, 23 Aug 2018 16:09:52 GMT  
		Size: 77.3 MB (77299108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9afea67a042db7e888ebbe0b4edb1e1af872e22ecadd4eea989f79546b5f8e1`  
		Last Modified: Thu, 23 Aug 2018 16:09:29 GMT  
		Size: 156.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80ae3f536d5e73d2c4a09b14f647aa3c6aeabaf4e319d36a6c990f53c612f346`  
		Last Modified: Thu, 23 Aug 2018 16:09:26 GMT  
		Size: 2.1 KB (2055 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b73165c62a51426107c72136a92a5d65a1666fefa9bc816280d1b129a890e5ef`  
		Last Modified: Thu, 23 Aug 2018 16:09:09 GMT  
		Size: 140.6 KB (140608 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:baa6822e1a23a13369ff5ab3f4f09c1fd6a66f63b8182460410f568ddefb248c`  
		Last Modified: Thu, 23 Aug 2018 16:09:08 GMT  
		Size: 469.9 KB (469926 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cfdbd237e559acd5493e9dd77e58ac3e87acf6332913d635f706df66c6dc469b`  
		Last Modified: Thu, 23 Aug 2018 16:10:29 GMT  
		Size: 87.8 MB (87818956 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee5b7001bfa431424dc995c4eeb32a74e25444df3a08087610e2188059ae8a19`  
		Last Modified: Thu, 23 Aug 2018 16:10:20 GMT  
		Size: 6.4 KB (6431 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f32d65743c57e0cd3c50160b528a2818309f7da67b76609ed974ee2d65c694ce`  
		Last Modified: Thu, 23 Aug 2018 16:10:20 GMT  
		Size: 1.7 KB (1710 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `bonita:7.7.3`

```console
$ docker pull bonita@sha256:00598cb1c966ba87e06be2a5c189a7b5cb15deb04dea22be5deaf6c74906abce
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; ppc64le

### `bonita:7.7.3` - linux; amd64

```console
$ docker pull bonita@sha256:3c9311b1a4c307e9a05a93ec4434314d2eff2b58a1b5839db59939b2b5b4445d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **214.6 MB (214562181 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bc41b54e564f3cc28de1f28be9df6d74c3797a77853baf04e29999f990858d74`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Wed, 22 Aug 2018 17:31:28 GMT
ADD file:a83ab1826f43e88bc0d3ab6230f14cb9b2dacab70c762c3bfc555eda733b292c in / 
# Wed, 22 Aug 2018 17:31:29 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 22 Aug 2018 17:31:30 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:31:31 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 22 Aug 2018 17:31:32 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 22 Aug 2018 17:31:32 GMT
CMD ["/bin/bash"]
# Wed, 22 Aug 2018 17:54:06 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Wed, 22 Aug 2018 17:55:57 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:55:59 GMT
RUN mkdir /opt/custom-init.d/
# Wed, 22 Aug 2018 17:56:00 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Wed, 22 Aug 2018 17:56:01 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Wed, 22 Aug 2018 17:56:05 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_VERSION
# Wed, 22 Aug 2018 17:56:06 GMT
ARG TOMCAT_VERSION
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_SHA256
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_URL
# Wed, 22 Aug 2018 17:56:48 GMT
ENV BONITA_VERSION=7.7.3
# Wed, 22 Aug 2018 17:56:48 GMT
ENV TOMCAT_VERSION=8.5.31
# Wed, 22 Aug 2018 17:56:48 GMT
ENV BONITA_SHA256=a2c5c13359e90a99b143848b650be0cbee1b9bb6cfa9666904c123fc6d1e30a6
# Wed, 22 Aug 2018 17:56:48 GMT
ENV BONITA_URL=https://release.ow2.org/bonita/BonitaCommunity-7.7.3-Tomcat-8.5.31.zip
# Wed, 22 Aug 2018 17:57:00 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Wed, 22 Aug 2018 17:57:23 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Wed, 22 Aug 2018 17:57:25 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Wed, 22 Aug 2018 17:57:25 GMT
VOLUME [/opt/bonita]
# Wed, 22 Aug 2018 17:57:26 GMT
COPY dir:54e2aa3a901daf192e4916306de581c3b5abe3185f3c0ef0386107f80837ec74 in /opt/files 
# Wed, 22 Aug 2018 17:57:26 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Wed, 22 Aug 2018 17:57:26 GMT
EXPOSE 8080/tcp
# Wed, 22 Aug 2018 17:57:27 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:3b37166ec61459e76e33282dda08f2a9cd698ca7e3d6bc44e6a6e7580cdeff8e`  
		Last Modified: Fri, 10 Aug 2018 22:11:36 GMT  
		Size: 43.3 MB (43252507 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba077e1ddb3aa8b95b2ecc5e58830800af4f5c06a5a37a3b7d7e0a67e178fb65`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34c83d2bc656952f573cee825d42e58622909b4be524b653f4f3df7464e57aa2`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 616.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84b69b6e47437924b207458fe7fc8f66812622983ae5a5d84bfdd2d83a9581e1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f72e97e1f61face716660657e4df5f70c2008a0b8b89e35dc6a460124fe01d1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b3941d0e4d6787f54c318480d145352e50c6ea92bc99dcb0e4e79e6655dd5a4`  
		Last Modified: Wed, 22 Aug 2018 17:58:21 GMT  
		Size: 82.8 MB (82836684 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d86ec4eedeb6664ea04f4d481f9c75e603b9154434f4458ce463d2deef59056b`  
		Last Modified: Wed, 22 Aug 2018 17:57:54 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00d47462548fe72ddcc0eb86cadb04e6b8dd5d73922d68124949a8d32bf0996d`  
		Last Modified: Wed, 22 Aug 2018 17:57:53 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bd34dc86fe233101d4f453ea9c76ce132a570be3421e074e91fd07780eb156c`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 140.6 KB (140588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:493f5f5f4be43dd73397fbfe3740caebdb4d0c71d32ddcd20cc11677cf6c36f7`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 500.7 KB (500740 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a629406ed63f4a700a32150869cf1e2c96b00386ce71fb64773fcb872c67b63`  
		Last Modified: Wed, 22 Aug 2018 17:59:17 GMT  
		Size: 87.8 MB (87818924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:44eab2437acd1fa1366fa7ddfbeed5a20d0638135f3e11337907b4d048a61d1d`  
		Last Modified: Wed, 22 Aug 2018 17:59:08 GMT  
		Size: 6.4 KB (6403 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2725e7c4ac4c7cc0fa38e4a05c86c862f284e152e70088a2b4842ab76997310e`  
		Last Modified: Wed, 22 Aug 2018 17:59:07 GMT  
		Size: 1.7 KB (1685 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `bonita:7.7.3` - linux; arm64 variant v8

```console
$ docker pull bonita@sha256:a7b458ed225a83ef0706b458e3e874c5015c9302f96e8d6e9e716af9fdf3d8de
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **201.4 MB (201359608 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d2f90fe590184768901be188e48dd85afaf60c067cfd15ba9f32ddd0a2fd8d95`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 23 Aug 2018 18:00:02 GMT
ADD file:e5010797ac02efecbf22dd21592880fd5283c01d177c3f0d1274c6397683f8f0 in / 
# Thu, 23 Aug 2018 18:00:04 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 18:00:06 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 18:00:08 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 18:00:10 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 18:00:11 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 22:18:57 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 23 Aug 2018 22:21:18 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 22:21:25 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 23 Aug 2018 22:21:28 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 23 Aug 2018 22:21:48 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 23 Aug 2018 22:21:53 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 23 Aug 2018 22:22:09 GMT
ARG BONITA_VERSION
# Thu, 23 Aug 2018 22:22:10 GMT
ARG TOMCAT_VERSION
# Thu, 23 Aug 2018 22:22:10 GMT
ARG BONITA_SHA256
# Thu, 23 Aug 2018 22:22:11 GMT
ARG BONITA_URL
# Thu, 23 Aug 2018 22:24:31 GMT
ENV BONITA_VERSION=7.7.3
# Thu, 23 Aug 2018 22:24:32 GMT
ENV TOMCAT_VERSION=8.5.31
# Thu, 23 Aug 2018 22:24:33 GMT
ENV BONITA_SHA256=a2c5c13359e90a99b143848b650be0cbee1b9bb6cfa9666904c123fc6d1e30a6
# Thu, 23 Aug 2018 22:24:33 GMT
ENV BONITA_URL=https://release.ow2.org/bonita/BonitaCommunity-7.7.3-Tomcat-8.5.31.zip
# Thu, 23 Aug 2018 22:25:53 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 22:25:58 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 22:26:00 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 23 Aug 2018 22:26:01 GMT
VOLUME [/opt/bonita]
# Thu, 23 Aug 2018 22:26:02 GMT
COPY dir:54e2aa3a901daf192e4916306de581c3b5abe3185f3c0ef0386107f80837ec74 in /opt/files 
# Thu, 23 Aug 2018 22:26:03 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Thu, 23 Aug 2018 22:26:04 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 22:26:05 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:672a69505838a80ab1d16038f6268944bf913e2b9df67785f4f560145b243625`  
		Last Modified: Fri, 10 Aug 2018 22:12:34 GMT  
		Size: 39.4 MB (39381352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:958416e5b29b0395ebf84d5442b4a440207871d06ab7b5b475bbfcbc64625d16`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b9b2df41f722dc826e75f4e3fadac77f1487ed4e1254e92645e664d785662036`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 538.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ea051153c5ecf9f78bc0528c6f4917ae8a6bb1910be9c1e23926fa80704160a`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7bdeb5fe2e665aecb71278bdb333b15048b051370afe97929d4abf456e456a22`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ccfb9f28b47f919b20dab3fe0f436a6a1bea3d91be3a0a4964989d3ce83fed2`  
		Last Modified: Thu, 23 Aug 2018 22:27:32 GMT  
		Size: 73.5 MB (73537277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23d26be524bf12625935ae607440747a952773d61c8f038d31faa8b442ae064f`  
		Last Modified: Thu, 23 Aug 2018 22:27:10 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b6a65f40d10b47d7409c91f0c934d17b5faca150e8a4b3b66eb50268722efe3`  
		Last Modified: Thu, 23 Aug 2018 22:27:09 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c466ee9e085c26be745f4ab66f688b669ee0eac208c4f23f7c891e28ae5b17c`  
		Last Modified: Thu, 23 Aug 2018 22:27:06 GMT  
		Size: 140.6 KB (140587 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87e2a88ed077d6ee1ffa243d1cff3121a5157b3606f2e781bad602dcf738eb81`  
		Last Modified: Thu, 23 Aug 2018 22:27:07 GMT  
		Size: 468.8 KB (468794 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25b953ccb65b5856981f9a43fe8680cba3b1116b8e7a79605c08868e9029de8d`  
		Last Modified: Thu, 23 Aug 2018 22:28:34 GMT  
		Size: 87.8 MB (87818925 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c11df33243958e9cda4defdd099f5ab513aa51f95242dbf2eb9bca363d56ac30`  
		Last Modified: Thu, 23 Aug 2018 22:28:22 GMT  
		Size: 6.4 KB (6400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c523cef814681962a82097315b67c235ccabd02b6fc8628fb8d0843ccab22e5c`  
		Last Modified: Thu, 23 Aug 2018 22:28:21 GMT  
		Size: 1.7 KB (1686 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `bonita:7.7.3` - linux; ppc64le

```console
$ docker pull bonita@sha256:4db15ce69819b3f0bc89e469cd862c4ae6dddee53c48431d10106aa718f8cf32
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **211.3 MB (211336913 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f81b015b0179cd1e0ef1694876109a6cd5308276e7df5bd9549e621bcbd5090e`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 23 Aug 2018 12:50:13 GMT
ADD file:b09779db95ed098d4ff481c60f9070c9855d49079531c872f7f306766b31a320 in / 
# Thu, 23 Aug 2018 12:50:19 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 12:50:22 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 12:50:25 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 12:50:29 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 12:50:31 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 15:54:12 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 23 Aug 2018 16:01:33 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 16:02:03 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 23 Aug 2018 16:02:14 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 23 Aug 2018 16:02:24 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 23 Aug 2018 16:02:34 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 23 Aug 2018 16:02:36 GMT
ARG BONITA_VERSION
# Thu, 23 Aug 2018 16:02:39 GMT
ARG TOMCAT_VERSION
# Thu, 23 Aug 2018 16:02:44 GMT
ARG BONITA_SHA256
# Thu, 23 Aug 2018 16:02:47 GMT
ARG BONITA_URL
# Thu, 23 Aug 2018 16:05:59 GMT
ENV BONITA_VERSION=7.7.3
# Thu, 23 Aug 2018 16:06:03 GMT
ENV TOMCAT_VERSION=8.5.31
# Thu, 23 Aug 2018 16:06:05 GMT
ENV BONITA_SHA256=a2c5c13359e90a99b143848b650be0cbee1b9bb6cfa9666904c123fc6d1e30a6
# Thu, 23 Aug 2018 16:06:06 GMT
ENV BONITA_URL=https://release.ow2.org/bonita/BonitaCommunity-7.7.3-Tomcat-8.5.31.zip
# Thu, 23 Aug 2018 16:07:19 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 16:07:29 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 16:07:43 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 23 Aug 2018 16:07:45 GMT
VOLUME [/opt/bonita]
# Thu, 23 Aug 2018 16:08:12 GMT
COPY dir:54e2aa3a901daf192e4916306de581c3b5abe3185f3c0ef0386107f80837ec74 in /opt/files 
# Thu, 23 Aug 2018 16:08:25 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Thu, 23 Aug 2018 16:08:29 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 16:08:39 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:0d0dbb9a021cbff2129dab2bc36f95d25c2bde53c72d61c87f45f4b14b810ebc`  
		Last Modified: Thu, 23 Aug 2018 12:53:07 GMT  
		Size: 45.6 MB (45595505 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5cb08b3a0bd0961e0ecbe16b6c544124a22f1beca9f3621f59e5cd5e2346d49`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10066c30deaec81ef942231f5f84b5782b7cf7bcf78c389453617b7265465be2`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 579.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d604dc40c1d1c57ec0ba6faed21bc3b4e8ea4fa54eb547fbc134e7c73d468203`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 857.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12b9507f41bb4395530111a162394310249dfe8f51e0682c9c17747c09ff12f6`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c75e673f0cae40f078ff4c0bcfbca227aa9d334d42e80076c32c305d2ebb0440`  
		Last Modified: Thu, 23 Aug 2018 16:09:52 GMT  
		Size: 77.3 MB (77299108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9afea67a042db7e888ebbe0b4edb1e1af872e22ecadd4eea989f79546b5f8e1`  
		Last Modified: Thu, 23 Aug 2018 16:09:29 GMT  
		Size: 156.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80ae3f536d5e73d2c4a09b14f647aa3c6aeabaf4e319d36a6c990f53c612f346`  
		Last Modified: Thu, 23 Aug 2018 16:09:26 GMT  
		Size: 2.1 KB (2055 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b73165c62a51426107c72136a92a5d65a1666fefa9bc816280d1b129a890e5ef`  
		Last Modified: Thu, 23 Aug 2018 16:09:09 GMT  
		Size: 140.6 KB (140608 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:baa6822e1a23a13369ff5ab3f4f09c1fd6a66f63b8182460410f568ddefb248c`  
		Last Modified: Thu, 23 Aug 2018 16:09:08 GMT  
		Size: 469.9 KB (469926 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cfdbd237e559acd5493e9dd77e58ac3e87acf6332913d635f706df66c6dc469b`  
		Last Modified: Thu, 23 Aug 2018 16:10:29 GMT  
		Size: 87.8 MB (87818956 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee5b7001bfa431424dc995c4eeb32a74e25444df3a08087610e2188059ae8a19`  
		Last Modified: Thu, 23 Aug 2018 16:10:20 GMT  
		Size: 6.4 KB (6431 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f32d65743c57e0cd3c50160b528a2818309f7da67b76609ed974ee2d65c694ce`  
		Last Modified: Thu, 23 Aug 2018 16:10:20 GMT  
		Size: 1.7 KB (1710 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `bonita:latest`

```console
$ docker pull bonita@sha256:00598cb1c966ba87e06be2a5c189a7b5cb15deb04dea22be5deaf6c74906abce
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; ppc64le

### `bonita:latest` - linux; amd64

```console
$ docker pull bonita@sha256:3c9311b1a4c307e9a05a93ec4434314d2eff2b58a1b5839db59939b2b5b4445d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **214.6 MB (214562181 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bc41b54e564f3cc28de1f28be9df6d74c3797a77853baf04e29999f990858d74`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Wed, 22 Aug 2018 17:31:28 GMT
ADD file:a83ab1826f43e88bc0d3ab6230f14cb9b2dacab70c762c3bfc555eda733b292c in / 
# Wed, 22 Aug 2018 17:31:29 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 22 Aug 2018 17:31:30 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:31:31 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 22 Aug 2018 17:31:32 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 22 Aug 2018 17:31:32 GMT
CMD ["/bin/bash"]
# Wed, 22 Aug 2018 17:54:06 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Wed, 22 Aug 2018 17:55:57 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:55:59 GMT
RUN mkdir /opt/custom-init.d/
# Wed, 22 Aug 2018 17:56:00 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Wed, 22 Aug 2018 17:56:01 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Wed, 22 Aug 2018 17:56:05 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_VERSION
# Wed, 22 Aug 2018 17:56:06 GMT
ARG TOMCAT_VERSION
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_SHA256
# Wed, 22 Aug 2018 17:56:06 GMT
ARG BONITA_URL
# Wed, 22 Aug 2018 17:56:48 GMT
ENV BONITA_VERSION=7.7.3
# Wed, 22 Aug 2018 17:56:48 GMT
ENV TOMCAT_VERSION=8.5.31
# Wed, 22 Aug 2018 17:56:48 GMT
ENV BONITA_SHA256=a2c5c13359e90a99b143848b650be0cbee1b9bb6cfa9666904c123fc6d1e30a6
# Wed, 22 Aug 2018 17:56:48 GMT
ENV BONITA_URL=https://release.ow2.org/bonita/BonitaCommunity-7.7.3-Tomcat-8.5.31.zip
# Wed, 22 Aug 2018 17:57:00 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Wed, 22 Aug 2018 17:57:23 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Wed, 22 Aug 2018 17:57:25 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Wed, 22 Aug 2018 17:57:25 GMT
VOLUME [/opt/bonita]
# Wed, 22 Aug 2018 17:57:26 GMT
COPY dir:54e2aa3a901daf192e4916306de581c3b5abe3185f3c0ef0386107f80837ec74 in /opt/files 
# Wed, 22 Aug 2018 17:57:26 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Wed, 22 Aug 2018 17:57:26 GMT
EXPOSE 8080/tcp
# Wed, 22 Aug 2018 17:57:27 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:3b37166ec61459e76e33282dda08f2a9cd698ca7e3d6bc44e6a6e7580cdeff8e`  
		Last Modified: Fri, 10 Aug 2018 22:11:36 GMT  
		Size: 43.3 MB (43252507 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba077e1ddb3aa8b95b2ecc5e58830800af4f5c06a5a37a3b7d7e0a67e178fb65`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34c83d2bc656952f573cee825d42e58622909b4be524b653f4f3df7464e57aa2`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 616.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84b69b6e47437924b207458fe7fc8f66812622983ae5a5d84bfdd2d83a9581e1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f72e97e1f61face716660657e4df5f70c2008a0b8b89e35dc6a460124fe01d1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b3941d0e4d6787f54c318480d145352e50c6ea92bc99dcb0e4e79e6655dd5a4`  
		Last Modified: Wed, 22 Aug 2018 17:58:21 GMT  
		Size: 82.8 MB (82836684 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d86ec4eedeb6664ea04f4d481f9c75e603b9154434f4458ce463d2deef59056b`  
		Last Modified: Wed, 22 Aug 2018 17:57:54 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00d47462548fe72ddcc0eb86cadb04e6b8dd5d73922d68124949a8d32bf0996d`  
		Last Modified: Wed, 22 Aug 2018 17:57:53 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bd34dc86fe233101d4f453ea9c76ce132a570be3421e074e91fd07780eb156c`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 140.6 KB (140588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:493f5f5f4be43dd73397fbfe3740caebdb4d0c71d32ddcd20cc11677cf6c36f7`  
		Last Modified: Wed, 22 Aug 2018 17:57:51 GMT  
		Size: 500.7 KB (500740 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a629406ed63f4a700a32150869cf1e2c96b00386ce71fb64773fcb872c67b63`  
		Last Modified: Wed, 22 Aug 2018 17:59:17 GMT  
		Size: 87.8 MB (87818924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:44eab2437acd1fa1366fa7ddfbeed5a20d0638135f3e11337907b4d048a61d1d`  
		Last Modified: Wed, 22 Aug 2018 17:59:08 GMT  
		Size: 6.4 KB (6403 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2725e7c4ac4c7cc0fa38e4a05c86c862f284e152e70088a2b4842ab76997310e`  
		Last Modified: Wed, 22 Aug 2018 17:59:07 GMT  
		Size: 1.7 KB (1685 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `bonita:latest` - linux; arm64 variant v8

```console
$ docker pull bonita@sha256:a7b458ed225a83ef0706b458e3e874c5015c9302f96e8d6e9e716af9fdf3d8de
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **201.4 MB (201359608 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d2f90fe590184768901be188e48dd85afaf60c067cfd15ba9f32ddd0a2fd8d95`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 23 Aug 2018 18:00:02 GMT
ADD file:e5010797ac02efecbf22dd21592880fd5283c01d177c3f0d1274c6397683f8f0 in / 
# Thu, 23 Aug 2018 18:00:04 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 18:00:06 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 18:00:08 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 18:00:10 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 18:00:11 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 22:18:57 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 23 Aug 2018 22:21:18 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 22:21:25 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 23 Aug 2018 22:21:28 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 23 Aug 2018 22:21:48 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 23 Aug 2018 22:21:53 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 23 Aug 2018 22:22:09 GMT
ARG BONITA_VERSION
# Thu, 23 Aug 2018 22:22:10 GMT
ARG TOMCAT_VERSION
# Thu, 23 Aug 2018 22:22:10 GMT
ARG BONITA_SHA256
# Thu, 23 Aug 2018 22:22:11 GMT
ARG BONITA_URL
# Thu, 23 Aug 2018 22:24:31 GMT
ENV BONITA_VERSION=7.7.3
# Thu, 23 Aug 2018 22:24:32 GMT
ENV TOMCAT_VERSION=8.5.31
# Thu, 23 Aug 2018 22:24:33 GMT
ENV BONITA_SHA256=a2c5c13359e90a99b143848b650be0cbee1b9bb6cfa9666904c123fc6d1e30a6
# Thu, 23 Aug 2018 22:24:33 GMT
ENV BONITA_URL=https://release.ow2.org/bonita/BonitaCommunity-7.7.3-Tomcat-8.5.31.zip
# Thu, 23 Aug 2018 22:25:53 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 22:25:58 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 22:26:00 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 23 Aug 2018 22:26:01 GMT
VOLUME [/opt/bonita]
# Thu, 23 Aug 2018 22:26:02 GMT
COPY dir:54e2aa3a901daf192e4916306de581c3b5abe3185f3c0ef0386107f80837ec74 in /opt/files 
# Thu, 23 Aug 2018 22:26:03 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Thu, 23 Aug 2018 22:26:04 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 22:26:05 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:672a69505838a80ab1d16038f6268944bf913e2b9df67785f4f560145b243625`  
		Last Modified: Fri, 10 Aug 2018 22:12:34 GMT  
		Size: 39.4 MB (39381352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:958416e5b29b0395ebf84d5442b4a440207871d06ab7b5b475bbfcbc64625d16`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b9b2df41f722dc826e75f4e3fadac77f1487ed4e1254e92645e664d785662036`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 538.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ea051153c5ecf9f78bc0528c6f4917ae8a6bb1910be9c1e23926fa80704160a`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7bdeb5fe2e665aecb71278bdb333b15048b051370afe97929d4abf456e456a22`  
		Last Modified: Thu, 23 Aug 2018 18:06:04 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ccfb9f28b47f919b20dab3fe0f436a6a1bea3d91be3a0a4964989d3ce83fed2`  
		Last Modified: Thu, 23 Aug 2018 22:27:32 GMT  
		Size: 73.5 MB (73537277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23d26be524bf12625935ae607440747a952773d61c8f038d31faa8b442ae064f`  
		Last Modified: Thu, 23 Aug 2018 22:27:10 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b6a65f40d10b47d7409c91f0c934d17b5faca150e8a4b3b66eb50268722efe3`  
		Last Modified: Thu, 23 Aug 2018 22:27:09 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c466ee9e085c26be745f4ab66f688b669ee0eac208c4f23f7c891e28ae5b17c`  
		Last Modified: Thu, 23 Aug 2018 22:27:06 GMT  
		Size: 140.6 KB (140587 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87e2a88ed077d6ee1ffa243d1cff3121a5157b3606f2e781bad602dcf738eb81`  
		Last Modified: Thu, 23 Aug 2018 22:27:07 GMT  
		Size: 468.8 KB (468794 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25b953ccb65b5856981f9a43fe8680cba3b1116b8e7a79605c08868e9029de8d`  
		Last Modified: Thu, 23 Aug 2018 22:28:34 GMT  
		Size: 87.8 MB (87818925 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c11df33243958e9cda4defdd099f5ab513aa51f95242dbf2eb9bca363d56ac30`  
		Last Modified: Thu, 23 Aug 2018 22:28:22 GMT  
		Size: 6.4 KB (6400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c523cef814681962a82097315b67c235ccabd02b6fc8628fb8d0843ccab22e5c`  
		Last Modified: Thu, 23 Aug 2018 22:28:21 GMT  
		Size: 1.7 KB (1686 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `bonita:latest` - linux; ppc64le

```console
$ docker pull bonita@sha256:4db15ce69819b3f0bc89e469cd862c4ae6dddee53c48431d10106aa718f8cf32
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **211.3 MB (211336913 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f81b015b0179cd1e0ef1694876109a6cd5308276e7df5bd9549e621bcbd5090e`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 23 Aug 2018 12:50:13 GMT
ADD file:b09779db95ed098d4ff481c60f9070c9855d49079531c872f7f306766b31a320 in / 
# Thu, 23 Aug 2018 12:50:19 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 12:50:22 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 12:50:25 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 12:50:29 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 12:50:31 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 15:54:12 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 23 Aug 2018 16:01:33 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 16:02:03 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 23 Aug 2018 16:02:14 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 23 Aug 2018 16:02:24 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 23 Aug 2018 16:02:34 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.10/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 23 Aug 2018 16:02:36 GMT
ARG BONITA_VERSION
# Thu, 23 Aug 2018 16:02:39 GMT
ARG TOMCAT_VERSION
# Thu, 23 Aug 2018 16:02:44 GMT
ARG BONITA_SHA256
# Thu, 23 Aug 2018 16:02:47 GMT
ARG BONITA_URL
# Thu, 23 Aug 2018 16:05:59 GMT
ENV BONITA_VERSION=7.7.3
# Thu, 23 Aug 2018 16:06:03 GMT
ENV TOMCAT_VERSION=8.5.31
# Thu, 23 Aug 2018 16:06:05 GMT
ENV BONITA_SHA256=a2c5c13359e90a99b143848b650be0cbee1b9bb6cfa9666904c123fc6d1e30a6
# Thu, 23 Aug 2018 16:06:06 GMT
ENV BONITA_URL=https://release.ow2.org/bonita/BonitaCommunity-7.7.3-Tomcat-8.5.31.zip
# Thu, 23 Aug 2018 16:07:19 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 16:07:29 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 23 Aug 2018 16:07:43 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 23 Aug 2018 16:07:45 GMT
VOLUME [/opt/bonita]
# Thu, 23 Aug 2018 16:08:12 GMT
COPY dir:54e2aa3a901daf192e4916306de581c3b5abe3185f3c0ef0386107f80837ec74 in /opt/files 
# Thu, 23 Aug 2018 16:08:25 GMT
COPY dir:1549f33c9631f90a53a4bb891fea7f7da9a3032b4b950f47dd3d0f6bb486411c in /opt/templates 
# Thu, 23 Aug 2018 16:08:29 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 16:08:39 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:0d0dbb9a021cbff2129dab2bc36f95d25c2bde53c72d61c87f45f4b14b810ebc`  
		Last Modified: Thu, 23 Aug 2018 12:53:07 GMT  
		Size: 45.6 MB (45595505 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5cb08b3a0bd0961e0ecbe16b6c544124a22f1beca9f3621f59e5cd5e2346d49`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10066c30deaec81ef942231f5f84b5782b7cf7bcf78c389453617b7265465be2`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 579.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d604dc40c1d1c57ec0ba6faed21bc3b4e8ea4fa54eb547fbc134e7c73d468203`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 857.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12b9507f41bb4395530111a162394310249dfe8f51e0682c9c17747c09ff12f6`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c75e673f0cae40f078ff4c0bcfbca227aa9d334d42e80076c32c305d2ebb0440`  
		Last Modified: Thu, 23 Aug 2018 16:09:52 GMT  
		Size: 77.3 MB (77299108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9afea67a042db7e888ebbe0b4edb1e1af872e22ecadd4eea989f79546b5f8e1`  
		Last Modified: Thu, 23 Aug 2018 16:09:29 GMT  
		Size: 156.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80ae3f536d5e73d2c4a09b14f647aa3c6aeabaf4e319d36a6c990f53c612f346`  
		Last Modified: Thu, 23 Aug 2018 16:09:26 GMT  
		Size: 2.1 KB (2055 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b73165c62a51426107c72136a92a5d65a1666fefa9bc816280d1b129a890e5ef`  
		Last Modified: Thu, 23 Aug 2018 16:09:09 GMT  
		Size: 140.6 KB (140608 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:baa6822e1a23a13369ff5ab3f4f09c1fd6a66f63b8182460410f568ddefb248c`  
		Last Modified: Thu, 23 Aug 2018 16:09:08 GMT  
		Size: 469.9 KB (469926 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cfdbd237e559acd5493e9dd77e58ac3e87acf6332913d635f706df66c6dc469b`  
		Last Modified: Thu, 23 Aug 2018 16:10:29 GMT  
		Size: 87.8 MB (87818956 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee5b7001bfa431424dc995c4eeb32a74e25444df3a08087610e2188059ae8a19`  
		Last Modified: Thu, 23 Aug 2018 16:10:20 GMT  
		Size: 6.4 KB (6431 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f32d65743c57e0cd3c50160b528a2818309f7da67b76609ed974ee2d65c694ce`  
		Last Modified: Thu, 23 Aug 2018 16:10:20 GMT  
		Size: 1.7 KB (1710 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
