## `buildpack-deps:cosmic-curl`

```console
$ docker pull buildpack-deps@sha256:6e9ff0e5846dcac5f4857c4efa8ca0d0091a2dceca7500f6a6d4301e31dafe30
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `buildpack-deps:cosmic-curl` - linux; amd64

```console
$ docker pull buildpack-deps@sha256:5c782ed7107eb86f9e2f99964b0981349454337c84b81dcf081dc80eca8df84e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **37.9 MB (37856952 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a395702c2729afd5832c312fef08571f772ee9314aaeb4424f730550d9759bf3`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Wed, 22 Aug 2018 17:29:35 GMT
ADD file:f6ffec9946318d0be6095c6bfcf92c5b822d4132d04ddda311f029c0672d19e4 in / 
# Wed, 22 Aug 2018 17:29:51 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 22 Aug 2018 17:29:51 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:29:52 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 22 Aug 2018 17:29:53 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 22 Aug 2018 17:29:53 GMT
CMD ["/bin/bash"]
# Wed, 22 Aug 2018 18:02:09 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 18:02:29 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:f6ce8dd4f6a328d2c7def7290df9c4bb616665794bf4d96d30a021041090c1fa`  
		Last Modified: Wed, 22 Aug 2018 17:34:06 GMT  
		Size: 29.0 MB (29041919 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12e0a5e5001c3581f009549f4bf72273abe2c6a6581baf13af9087ae59f4d567`  
		Last Modified: Wed, 22 Aug 2018 17:33:57 GMT  
		Size: 860.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3682c8c930ee6683b1c2e168f2baad62ac35231c234a86d5a4d41fb142a2cc0b`  
		Last Modified: Wed, 22 Aug 2018 17:33:56 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1aea40ddd174ef535393aeb138bddc3ad112518e417364cfa8c0e595fc745422`  
		Last Modified: Wed, 22 Aug 2018 17:33:56 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a44230b0cedada0cb31e5f6001e8e0821533fdc159bda9e9f65a4fe7bb44741d`  
		Last Modified: Wed, 22 Aug 2018 18:24:29 GMT  
		Size: 5.8 MB (5847248 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:74b6a9a7e06db1670f97d4da42e9d1b85adddb5f483ea9c7ce0472ad860cd59b`  
		Last Modified: Wed, 22 Aug 2018 18:24:27 GMT  
		Size: 3.0 MB (2965907 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `buildpack-deps:cosmic-curl` - linux; arm variant v7

```console
$ docker pull buildpack-deps@sha256:ef3453be8cdc8c78a91e8c8e4971cb7c71ac976873baae53aac39f43c4aee48c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **32.0 MB (32026127 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4ad0f30831f2686abb82efb7620987001825e96a16b55db1dcd50629d8b23690`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Thu, 23 Aug 2018 13:29:40 GMT
ADD file:6cdb197727426e76fee3c91e936eaf040136c37da29a447e5e258de6c0c823e7 in / 
# Thu, 23 Aug 2018 13:29:42 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 13:29:42 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 13:29:43 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 13:29:44 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 13:29:45 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 14:31:13 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 14:31:40 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:adee882f80c5e0ab18af071145a3e13884f7f3eb1d4805d56ad631d546c7fb21`  
		Last Modified: Thu, 23 Aug 2018 13:31:34 GMT  
		Size: 24.6 MB (24559659 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e40da2918936a568cda51c312ac13bfe4943c11defe6276d94a27bc1f658d7e6`  
		Last Modified: Thu, 23 Aug 2018 13:31:27 GMT  
		Size: 859.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7c6b1c05d480f7cfd28dfb18d41f799019a77174b1e93b125e76434ab7da8222`  
		Last Modified: Thu, 23 Aug 2018 13:31:27 GMT  
		Size: 852.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:602797cbbd5dfd999c5cee7ff11810fe8aa3034331912242330289e21acb9f64`  
		Last Modified: Thu, 23 Aug 2018 13:31:27 GMT  
		Size: 188.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f002da03f720a325e6abb9911ebd16f8a1b712ef225047a83d1f574efec45c6`  
		Last Modified: Thu, 23 Aug 2018 14:48:27 GMT  
		Size: 4.9 MB (4934913 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bc0e8765605d412a48575519cf1c361324637f55b0e77b2c9ad19e1d6ff27392`  
		Last Modified: Thu, 23 Aug 2018 14:48:26 GMT  
		Size: 2.5 MB (2529656 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `buildpack-deps:cosmic-curl` - linux; arm64 variant v8

```console
$ docker pull buildpack-deps@sha256:56a6117b67b1887650e3ce7a6a389c6fb69ed8a178d37b390a6852be88da1ab7
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **34.3 MB (34300983 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6f640e7a51f6ee485a9444a3a0ea3c5ac14d9d0698dc70350e891011d6f90887`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Thu, 23 Aug 2018 17:57:53 GMT
ADD file:c08411583fbd036cdfe52a57e60bc2135cf3eb5a2977dcb5d72108c418cbc3b9 in / 
# Thu, 23 Aug 2018 17:57:55 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 17:57:57 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 17:57:59 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 17:58:01 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 17:58:02 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 22:44:48 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 22:45:36 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:190c7faaa654089b6c9b07e24206c9a4c4f4fe35811239202386e1e34be4699f`  
		Last Modified: Thu, 23 Aug 2018 18:02:54 GMT  
		Size: 26.2 MB (26198122 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb7d65558fd4a4a93c465bec4d53f3dce1c0d987222b21e632f5c7b020539c05`  
		Last Modified: Thu, 23 Aug 2018 18:02:47 GMT  
		Size: 862.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:755dd2b40afb33c13be4c8289fb6c15d2fdab88d8fa5a68c1114837976770c41`  
		Last Modified: Thu, 23 Aug 2018 18:02:45 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ff283afd59de84a6fca251b29c062a8fc9db9db7e5607af70a5152fb07503bf`  
		Last Modified: Thu, 23 Aug 2018 18:02:45 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a3885a2c9cef3dba0afbedaebba7e87f4c41e1f4f0f377f850a85a38cc25046`  
		Last Modified: Thu, 23 Aug 2018 23:36:50 GMT  
		Size: 5.4 MB (5373073 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3c480a9baa374658c4e39008b27002cca21da120fe0a407869b9f3d4df6fd4f`  
		Last Modified: Thu, 23 Aug 2018 23:36:49 GMT  
		Size: 2.7 MB (2727908 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `buildpack-deps:cosmic-curl` - linux; 386

```console
$ docker pull buildpack-deps@sha256:11439490a77640e52f2b97efddb2eb0c83a34583cdcf47398081ad6205c11e22
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **38.8 MB (38779771 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3e7053bc9c1d504b36099ae0783beaae9095cb0c4a465837f022b19f62e5bf4c`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Thu, 23 Aug 2018 15:52:31 GMT
ADD file:e2c73b21ea136304a9476862191f300c35f04637e95e3c014fed9299cf57b34d in / 
# Thu, 23 Aug 2018 15:52:41 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 15:52:42 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 15:52:43 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 15:52:44 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 15:53:01 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 19:07:10 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 19:07:29 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:67ba0e3ea69efa214839b755fb5f5685c6edbe01dd4add5c30ebe46b1336db90`  
		Last Modified: Thu, 23 Aug 2018 15:59:46 GMT  
		Size: 29.5 MB (29453570 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:159808e5d4fe1b26fa365f9fe1d9df7e3ac489d9595bb33265f1012a96e6b470`  
		Last Modified: Thu, 23 Aug 2018 15:59:34 GMT  
		Size: 860.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ad8b6de326ee718f2ad39b754e3a155fdf21911b75fcdb9ba1c1a1530642977`  
		Last Modified: Thu, 23 Aug 2018 15:59:34 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d5f3ee0031f6d8726256426d889f122b8a5af5b9eea96c15e1bb604ce3693ba3`  
		Last Modified: Thu, 23 Aug 2018 15:59:34 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2126df7677189067826b731b88f13fb78c32477b585ec80a479cec7e48d19a27`  
		Last Modified: Thu, 23 Aug 2018 19:31:26 GMT  
		Size: 6.1 MB (6125872 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae23251d537233b57f82fc680d441d5e490b0df222b1636456704c246363891e`  
		Last Modified: Thu, 23 Aug 2018 19:31:25 GMT  
		Size: 3.2 MB (3198452 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `buildpack-deps:cosmic-curl` - linux; ppc64le

```console
$ docker pull buildpack-deps@sha256:a23dea136f7ef40362b65c02e2f710e0793e8b145281f07e37db48070ae106a5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **42.7 MB (42675715 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6c15919d7d6205d15809a27122aa1f0b19a9b998094e85cb50310cea7360d0d2`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Thu, 23 Aug 2018 12:48:50 GMT
ADD file:90ec39bdde69f12038306c80788caf1ca13570ed7352bc1bb849b15f3c820157 in / 
# Thu, 23 Aug 2018 12:48:57 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 12:49:00 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 12:49:04 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 12:49:07 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 12:49:08 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 16:26:13 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 16:26:51 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:d6916d90889e3acf9c06539b8da4bb9378ef3b50a3d20cfae32e2c4d25960068`  
		Last Modified: Thu, 23 Aug 2018 12:51:44 GMT  
		Size: 32.9 MB (32881701 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb1230894de7f2c99d6016f19275a22be4f5b2df1fb8a8f797b6dbc99a2a5a3a`  
		Last Modified: Thu, 23 Aug 2018 12:51:35 GMT  
		Size: 865.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b1ee4347c1f875bf9a455db5844337c4f7113f23f3b577daed5baa97e0350ff5`  
		Last Modified: Thu, 23 Aug 2018 12:51:35 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d90ebc6bb0e401eb3ce2fb5f015a1ac46e8ea3f845ae1a878735d7ce4320fe9`  
		Last Modified: Thu, 23 Aug 2018 12:51:35 GMT  
		Size: 186.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3aee4a3006faeeb49543179b09fbee1d725fa8116afec6dec5dca07cc3d3f3bd`  
		Last Modified: Thu, 23 Aug 2018 16:56:07 GMT  
		Size: 6.1 MB (6119526 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c1073515e47801981f1ddc78c026beed3ba2d55dfa618ae2255fa430db6e721`  
		Last Modified: Thu, 23 Aug 2018 16:56:06 GMT  
		Size: 3.7 MB (3672582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `buildpack-deps:cosmic-curl` - linux; s390x

```console
$ docker pull buildpack-deps@sha256:b58086c596009d55a9a33b58f7ac657424c08909fd89069eafcf22ae977af668
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **36.1 MB (36088742 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5fb983ab20d9c7c672aadb982e6b07e6a968978177247227d5a75bd8e0b18608`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Thu, 23 Aug 2018 14:48:57 GMT
ADD file:5933957b70ad980d7dcdb7e70ed4aec93ef92c18e73d5f3e2360d268d9508ed9 in / 
# Thu, 23 Aug 2018 14:48:58 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 14:48:58 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 14:48:59 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 14:49:00 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 14:49:00 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 15:48:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 15:48:41 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:42865ba64a2a07e0874f83a789c040e13cfa4e69647bbfce783a399cb44a2486`  
		Last Modified: Thu, 23 Aug 2018 14:50:42 GMT  
		Size: 27.6 MB (27641972 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55777ab21beca450166647db9a39d054cd5bb5b3fa9f372408116456e1f3c384`  
		Last Modified: Thu, 23 Aug 2018 14:50:27 GMT  
		Size: 856.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65ca04d5e7ebe189196398049ffede5640ea2f326f4eff72d36a844abb81f98d`  
		Last Modified: Thu, 23 Aug 2018 14:50:27 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5d2c90afb44d85ecac0c1363c8d326201fab7dda7ce9beb8251855dff27353d`  
		Last Modified: Thu, 23 Aug 2018 14:50:27 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:859bcf4299599efb644b09159a5fefebdb1867c7697ee039cdfc65f262021dc2`  
		Last Modified: Thu, 23 Aug 2018 15:59:53 GMT  
		Size: 5.5 MB (5525780 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8ff0939fa48b92aca2014ccbc466215d0080e8f249d32410421c194c83107978`  
		Last Modified: Thu, 23 Aug 2018 15:59:50 GMT  
		Size: 2.9 MB (2919117 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
