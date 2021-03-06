## `couchbase:enterprise-4.6.5`

```console
$ docker pull couchbase@sha256:468dd813e1ed7f5da6e7528b960e70b3faed16e632899027f922cb5a49fa7dab
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `couchbase:enterprise-4.6.5` - linux; amd64

```console
$ docker pull couchbase@sha256:1663505d75d555a86f4c32ef1c7cc9045017e5e591e47d632ca6a83ce2ad9252
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **213.1 MB (213076099 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ab86bf9ee00a699bfb3a252b08dc101d232347f2edfd2c2f95686e2eb5eff168`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["couchbase-server"]`

```dockerfile
# Wed, 22 Aug 2018 17:30:42 GMT
ADD file:b52dc89539ef99aa7478debd2af0497ac50ee0d7658c05219bbf609440626583 in / 
# Wed, 22 Aug 2018 17:30:44 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 22 Aug 2018 17:30:44 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:30:46 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 22 Aug 2018 17:30:46 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 22 Aug 2018 17:30:47 GMT
CMD ["/bin/bash"]
# Wed, 22 Aug 2018 18:04:06 GMT
MAINTAINER Couchbase Docker Team <docker@couchbase.com>
# Wed, 22 Aug 2018 18:04:57 GMT
RUN apt-get update &&     apt-get install -yq runit wget python-httplib2 chrpath tzdata     lsof lshw sysstat net-tools numactl  &&     apt-get autoremove && apt-get clean &&     rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
# Wed, 22 Aug 2018 18:04:58 GMT
ARG CB_VERSION=4.6.5
# Wed, 22 Aug 2018 18:04:58 GMT
ARG CB_RELEASE_URL=https://packages.couchbase.com/releases
# Wed, 22 Aug 2018 18:04:58 GMT
ARG CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb
# Wed, 22 Aug 2018 18:04:58 GMT
ARG CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f
# Wed, 22 Aug 2018 18:04:59 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/opt/couchbase/bin:/opt/couchbase/bin/tools:/opt/couchbase/bin/install
# Wed, 22 Aug 2018 18:05:00 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f CB_VERSION=4.6.5
RUN groupadd -g 1000 couchbase && useradd couchbase -u 1000 -g couchbase -M
# Wed, 22 Aug 2018 18:05:23 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f CB_VERSION=4.6.5
RUN export INSTALL_DONT_START_SERVER=1 &&     wget -N $CB_RELEASE_URL/$CB_VERSION/$CB_PACKAGE &&     echo "$CB_SHA256  $CB_PACKAGE" | sha256sum -c - &&     dpkg -i ./$CB_PACKAGE && rm -f ./$CB_PACKAGE
# Wed, 22 Aug 2018 18:05:24 GMT
COPY file:9a90647aed4e88ee15c7efe9abbafbf7a89c3174cbe85d6b5492cde1aa9c6355 in /etc/service/couchbase-server/run 
# Wed, 22 Aug 2018 18:05:25 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f CB_VERSION=4.6.5
RUN chown -R couchbase:couchbase /etc/service
# Wed, 22 Aug 2018 18:05:25 GMT
COPY file:8196fd8e201c5fc3873a0faa3cec28b0d85633e363c0c5788434f5b9a81cfa5b in /usr/local/bin/ 
# Wed, 22 Aug 2018 18:05:26 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f CB_VERSION=4.6.5
RUN ln -s dummy.sh /usr/local/bin/iptables-save &&     ln -s dummy.sh /usr/local/bin/lvdisplay &&     ln -s dummy.sh /usr/local/bin/vgdisplay &&     ln -s dummy.sh /usr/local/bin/pvdisplay
# Wed, 22 Aug 2018 18:05:27 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f CB_VERSION=4.6.5
RUN chrpath -r '$ORIGIN/../lib' /opt/couchbase/bin/curl
# Wed, 22 Aug 2018 18:05:27 GMT
COPY file:5d67fa23771c82cbce2e1a74900e7c0ce4d1466a002273f57ab13d52d6b844b3 in / 
# Wed, 22 Aug 2018 18:05:28 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 22 Aug 2018 18:05:28 GMT
CMD ["couchbase-server"]
# Wed, 22 Aug 2018 18:05:28 GMT
EXPOSE 11207/tcp 11210/tcp 11211/tcp 18091/tcp 18092/tcp 18093/tcp 18094/tcp 18095/tcp 18096/tcp 8091/tcp 8092/tcp 8093/tcp 8094/tcp 8095/tcp 8096/tcp
# Wed, 22 Aug 2018 18:05:28 GMT
VOLUME [/opt/couchbase/var]
```

-	Layers:
	-	`sha256:72c01b436656c9a55ae968ed14e4f1b2a36e11a1103de1d78052edc926d5003f`  
		Last Modified: Wed, 22 Aug 2018 17:35:57 GMT  
		Size: 67.1 MB (67126755 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:944f9cf63457523d1b9cb2a03b24f959518a46db74340ec939cec53e6eaf4f7c`  
		Last Modified: Wed, 22 Aug 2018 17:35:33 GMT  
		Size: 72.7 KB (72650 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6856614e8780c7b74fd9f5448864511a0dbb4d2d30a67c32f7b34c72dba00e50`  
		Last Modified: Wed, 22 Aug 2018 17:35:33 GMT  
		Size: 363.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d0e4b6507f2bfe58324cac95a2327b9d8d14465b25cb07c1973f3236bcaf6f7`  
		Last Modified: Wed, 22 Aug 2018 17:35:33 GMT  
		Size: 850.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c00913272b9b1954235f892b11310c30df9a77bfad37ae48ca070bdd1ed2e0b6`  
		Last Modified: Wed, 22 Aug 2018 17:35:33 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecb9f9004e7668e19e591fba3d6d2909024fac7bd9e035c4cd5eb3a915034b4c`  
		Last Modified: Wed, 22 Aug 2018 18:11:00 GMT  
		Size: 11.4 MB (11391861 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6f757fe673c3e8e1196cab0a8b90b6fca1a443bc2ad27817de0b3f694506471`  
		Last Modified: Wed, 22 Aug 2018 18:10:52 GMT  
		Size: 1.9 KB (1912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6243bcae380e2b5bd485767e0d659ea91692a353c551cb2bb36b5b370d34628`  
		Last Modified: Wed, 22 Aug 2018 18:11:37 GMT  
		Size: 134.4 MB (134374013 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:faf6b6233b88a7e90fc29c956dae83f0b73d9b3d7302a15460b5d6cb56b098d1`  
		Last Modified: Wed, 22 Aug 2018 18:10:52 GMT  
		Size: 405.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ddcaa1195f7358e3ba9cd434391a143f1ff3ea2411e9ee37e0be66c1b1cedd81`  
		Last Modified: Wed, 22 Aug 2018 18:10:50 GMT  
		Size: 414.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c651af0e4de495b6fcfdd06852998eb18a2b85b05e2c9e7dec3611b024e5fc74`  
		Last Modified: Wed, 22 Aug 2018 18:10:49 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dbb8c4b41a77ef899593fdde0090c4bb154ce37933350ce614c3e7f18432b1b3`  
		Last Modified: Wed, 22 Aug 2018 18:10:49 GMT  
		Size: 217.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab4ca73ade8b4e305f60ab90c11e5761a98fcbc606a69113149be8f52a4be7f9`  
		Last Modified: Wed, 22 Aug 2018 18:10:49 GMT  
		Size: 105.4 KB (105404 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6b9239a252fdd893b76a5bc629bd570b5c75056a46196fd4e26e09d49f2bba75`  
		Last Modified: Wed, 22 Aug 2018 18:10:49 GMT  
		Size: 857.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
