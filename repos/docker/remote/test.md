## `docker:test`

```console
$ docker pull docker@sha256:9067d60cb6f252eb26b39665ef9ae22155bb2e4e4c0a0e05f4c10b2795ef45cc
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v6
	-	linux; arm64 variant v8

### `docker:test` - linux; amd64

```console
$ docker pull docker@sha256:265f40e9f5b3d4ef68e3da038e142314423faec60a6ba8b796f29e3d2b754fab
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **51.1 MB (51132275 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:228a322128e95577a3687465669d5d89e32b4a3b4d25d034c9f892dbfb354a01`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["sh"]`

```dockerfile
# Fri, 06 Jul 2018 14:14:06 GMT
ADD file:25f61d70254b9807a40cd3e8d820f6a5ec0e1e596de04e325f6a33810393e95a in / 
# Fri, 06 Jul 2018 14:14:06 GMT
CMD ["/bin/sh"]
# Thu, 30 Aug 2018 21:46:58 GMT
RUN apk add --no-cache 		ca-certificates
# Thu, 30 Aug 2018 21:46:58 GMT
RUN [ ! -e /etc/nsswitch.conf ] && echo 'hosts: files dns' > /etc/nsswitch.conf
# Thu, 30 Aug 2018 21:46:58 GMT
ENV DOCKER_CHANNEL=test
# Thu, 30 Aug 2018 21:46:59 GMT
ENV DOCKER_VERSION=18.09.0-ce-tp4
# Thu, 30 Aug 2018 21:47:11 GMT
RUN set -ex; 	apk add --no-cache --virtual .fetch-deps 		curl 		tar 	; 		apkArch="$(apk --print-arch)"; 	case "$apkArch" in 		x86_64) dockerArch='x86_64' ;; 		armhf) dockerArch='armel' ;; 		aarch64) dockerArch='aarch64' ;; 		ppc64le) dockerArch='ppc64le' ;; 		s390x) dockerArch='s390x' ;; 		*) echo >&2 "error: unsupported architecture ($apkArch)"; exit 1 ;;	esac; 		if ! curl -fL -o docker.tgz "https://download.docker.com/linux/static/${DOCKER_CHANNEL}/${dockerArch}/docker-${DOCKER_VERSION}.tgz"; then 		echo >&2 "error: failed to download 'docker-${DOCKER_VERSION}' from '${DOCKER_CHANNEL}' for '${dockerArch}'"; 		exit 1; 	fi; 		tar --extract 		--file docker.tgz 		--strip-components 1 		--directory /usr/local/bin/ 	; 	rm docker.tgz; 		apk del .fetch-deps; 		dockerd -v; 	docker -v
# Thu, 30 Aug 2018 21:47:11 GMT
COPY file:016ebcc5aefa6b28f6c484a299057d5b236e1d4f3baf44cc76eb4cd578821691 in /usr/local/bin/modprobe 
# Thu, 30 Aug 2018 21:47:11 GMT
COPY file:0d94e1cd679f133aab807891a1b00b6aef1a9f1f884108e7a17ddf50ab88f1fb in /usr/local/bin/ 
# Thu, 30 Aug 2018 21:47:11 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 30 Aug 2018 21:47:11 GMT
CMD ["sh"]
```

-	Layers:
	-	`sha256:8e3ba11ec2a2b39ab372c60c16b421536e50e5ce64a0bc81765c2e38381bcff6`  
		Last Modified: Fri, 06 Jul 2018 04:15:58 GMT  
		Size: 2.2 MB (2206542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10ba875c1cb72dff6366f4dcebaff7668c4e7a0840aa337aac83d888e847e6a5`  
		Last Modified: Thu, 30 Aug 2018 21:47:51 GMT  
		Size: 309.0 KB (308992 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9177e336ded02870da56507110e1f4640d84ef81e956662b41b6cb5d065b1518`  
		Last Modified: Thu, 30 Aug 2018 21:47:52 GMT  
		Size: 154.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2807f64d419bbb2f24b9e2492f325f641e47eb2628319ebfea6aff7dc24c7632`  
		Last Modified: Thu, 30 Aug 2018 21:48:02 GMT  
		Size: 48.6 MB (48615295 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12a773efea07e1cbcd9d1b1e70c83202d4eba1f8b13761e0a0831054c6f1a17a`  
		Last Modified: Thu, 30 Aug 2018 21:47:51 GMT  
		Size: 549.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6f9c92eee5cf3121b8e7ac5dcb3acc8ac2ea09e96467f2ee61d7199ec9150fa3`  
		Last Modified: Thu, 30 Aug 2018 21:47:51 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `docker:test` - linux; arm variant v6

```console
$ docker pull docker@sha256:eba647d9ccf1f6dd7e35b73a0fe5be2b12216cc5e42547fe9af6c4d15ebc8142
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **48.2 MB (48208231 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e1d560dc39a1debf5c353a44bbbd1b430ca825bb97fe5cb46fd8f06669e70e37`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["sh"]`

```dockerfile
# Fri, 06 Jul 2018 07:53:29 GMT
ADD file:122e3422d9afa971806601812374fdd9d00c8edc8e9a6df7256e2caa85fab6d1 in / 
# Fri, 06 Jul 2018 07:53:30 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 07:53:30 GMT
CMD ["/bin/sh"]
# Fri, 17 Aug 2018 07:54:18 GMT
RUN apk add --no-cache 		ca-certificates
# Fri, 17 Aug 2018 07:54:18 GMT
RUN [ ! -e /etc/nsswitch.conf ] && echo 'hosts: files dns' > /etc/nsswitch.conf
# Fri, 17 Aug 2018 07:54:19 GMT
ENV DOCKER_CHANNEL=test
# Tue, 28 Aug 2018 07:51:22 GMT
ENV DOCKER_VERSION=18.09.0-ce-tp4
# Tue, 28 Aug 2018 07:51:31 GMT
RUN set -ex; 	apk add --no-cache --virtual .fetch-deps 		curl 		tar 	; 		apkArch="$(apk --print-arch)"; 	case "$apkArch" in 		x86_64) dockerArch='x86_64' ;; 		armhf) dockerArch='armel' ;; 		aarch64) dockerArch='aarch64' ;; 		ppc64le) dockerArch='ppc64le' ;; 		s390x) dockerArch='s390x' ;; 		*) echo >&2 "error: unsupported architecture ($apkArch)"; exit 1 ;;	esac; 		if ! curl -fL -o docker.tgz "https://download.docker.com/linux/static/${DOCKER_CHANNEL}/${dockerArch}/docker-${DOCKER_VERSION}.tgz"; then 		echo >&2 "error: failed to download 'docker-${DOCKER_VERSION}' from '${DOCKER_CHANNEL}' for '${dockerArch}'"; 		exit 1; 	fi; 		tar --extract 		--file docker.tgz 		--strip-components 1 		--directory /usr/local/bin/ 	; 	rm docker.tgz; 		apk del .fetch-deps; 		dockerd -v; 	docker -v
# Tue, 28 Aug 2018 07:51:32 GMT
COPY file:016ebcc5aefa6b28f6c484a299057d5b236e1d4f3baf44cc76eb4cd578821691 in /usr/local/bin/modprobe 
# Tue, 28 Aug 2018 07:51:33 GMT
COPY file:0d94e1cd679f133aab807891a1b00b6aef1a9f1f884108e7a17ddf50ab88f1fb in /usr/local/bin/ 
# Tue, 28 Aug 2018 07:51:33 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 28 Aug 2018 07:51:33 GMT
CMD ["sh"]
```

-	Layers:
	-	`sha256:ee7d700abbf209aa401ef5d53f86af298a25e8154b3259036e9307d08f255c5d`  
		Last Modified: Fri, 06 Jul 2018 07:53:45 GMT  
		Size: 2.1 MB (2145998 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1653f4692c1ccea69cd46121d4f1371957f66e97a20141371dd4da10ebaec19`  
		Last Modified: Fri, 06 Jul 2018 07:53:45 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8914d45f1b2cabdf98026bbfec8b70ebb63e829a8ebde571f733abaad018de39`  
		Last Modified: Fri, 17 Aug 2018 07:55:31 GMT  
		Size: 309.1 KB (309072 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6579bc6b32fc36451455300d9a15571bf468bcfe7f8b52ddc36f24590628d2b`  
		Last Modified: Fri, 17 Aug 2018 07:55:32 GMT  
		Size: 154.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:573b461b0f40521edaf90abb642ea4c402dc3e883d166115dc7d52c40796bb50`  
		Last Modified: Tue, 28 Aug 2018 07:52:23 GMT  
		Size: 45.8 MB (45751545 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a28cc8ab4d6be57d81b00946a041fefce2d0c7432da31048d5b40c8eef3aa12e`  
		Last Modified: Tue, 28 Aug 2018 07:52:08 GMT  
		Size: 547.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6d267e777c655f99f1cd283b635be84e1949c5aa9c3327d68d49b0af5912b1`  
		Last Modified: Tue, 28 Aug 2018 07:52:08 GMT  
		Size: 740.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `docker:test` - linux; arm64 variant v8

```console
$ docker pull docker@sha256:cbc6ff0bf8003ba482d5ba63ee9b43f38e68edc3a88730bba75c6c2161ac9c0d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **46.2 MB (46206151 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e4062117a58f089dcfc66985532c6094aa1be62d1d90f1983e94ef2f03fa25de`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["sh"]`

```dockerfile
# Fri, 06 Jul 2018 08:41:03 GMT
ADD file:199a5a48bddabaf1f649f58f3b17c323a1aa1a50e939dfdea3542e4041e91b7b in / 
# Fri, 06 Jul 2018 08:41:03 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 08:41:04 GMT
CMD ["/bin/sh"]
# Fri, 13 Jul 2018 08:41:59 GMT
RUN apk add --no-cache 		ca-certificates
# Fri, 13 Jul 2018 08:42:00 GMT
RUN [ ! -e /etc/nsswitch.conf ] && echo 'hosts: files dns' > /etc/nsswitch.conf
# Fri, 17 Aug 2018 08:39:43 GMT
ENV DOCKER_CHANNEL=test
# Tue, 28 Aug 2018 08:40:24 GMT
ENV DOCKER_VERSION=18.09.0-ce-tp4
# Tue, 28 Aug 2018 08:40:35 GMT
RUN set -ex; 	apk add --no-cache --virtual .fetch-deps 		curl 		tar 	; 		apkArch="$(apk --print-arch)"; 	case "$apkArch" in 		x86_64) dockerArch='x86_64' ;; 		armhf) dockerArch='armel' ;; 		aarch64) dockerArch='aarch64' ;; 		ppc64le) dockerArch='ppc64le' ;; 		s390x) dockerArch='s390x' ;; 		*) echo >&2 "error: unsupported architecture ($apkArch)"; exit 1 ;;	esac; 		if ! curl -fL -o docker.tgz "https://download.docker.com/linux/static/${DOCKER_CHANNEL}/${dockerArch}/docker-${DOCKER_VERSION}.tgz"; then 		echo >&2 "error: failed to download 'docker-${DOCKER_VERSION}' from '${DOCKER_CHANNEL}' for '${dockerArch}'"; 		exit 1; 	fi; 		tar --extract 		--file docker.tgz 		--strip-components 1 		--directory /usr/local/bin/ 	; 	rm docker.tgz; 		apk del .fetch-deps; 		dockerd -v; 	docker -v
# Tue, 28 Aug 2018 08:40:35 GMT
COPY file:016ebcc5aefa6b28f6c484a299057d5b236e1d4f3baf44cc76eb4cd578821691 in /usr/local/bin/modprobe 
# Tue, 28 Aug 2018 08:40:36 GMT
COPY file:0d94e1cd679f133aab807891a1b00b6aef1a9f1f884108e7a17ddf50ab88f1fb in /usr/local/bin/ 
# Tue, 28 Aug 2018 08:40:37 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 28 Aug 2018 08:40:58 GMT
CMD ["sh"]
```

-	Layers:
	-	`sha256:47e04371c99027fae42871b720fdc6cdddcb65062bfa05f0c3bb0a594cb5bbbd`  
		Last Modified: Wed, 27 Jun 2018 19:15:35 GMT  
		Size: 2.1 MB (2099514 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b4103359e1ecd9a7253d8b8a041d4e81db1ff4a5e1950bc0e02305d221c9e6c2`  
		Last Modified: Fri, 06 Jul 2018 08:42:09 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fdcf8e21e8f5edb742758a8dcd7868dc15b1b1ad2605c214d159d58216e7944a`  
		Last Modified: Fri, 13 Jul 2018 08:52:12 GMT  
		Size: 308.5 KB (308530 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38e221838d317e50636dd30af1175c5672e49c137b7163688ad18fd895860a23`  
		Last Modified: Fri, 13 Jul 2018 08:52:12 GMT  
		Size: 154.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e95b5a7567c097a5e1dd05667a813b29566770e89f526511e060407c6754f8cc`  
		Last Modified: Tue, 28 Aug 2018 08:43:51 GMT  
		Size: 43.8 MB (43796485 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8253cbf93003536f402f4f3fc19fcd28557d7eadcc193abf1d35efe23986a4b0`  
		Last Modified: Tue, 28 Aug 2018 08:43:33 GMT  
		Size: 548.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c9f144421bf2b05b51f8a6c9d9beeaebf42b051869ec56f2a2c50a8022e3beaa`  
		Last Modified: Tue, 28 Aug 2018 08:43:32 GMT  
		Size: 744.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
