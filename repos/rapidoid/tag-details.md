<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `rapidoid`

-	[`rapidoid:5`](#rapidoid5)
-	[`rapidoid:5.4`](#rapidoid54)
-	[`rapidoid:5.4.6`](#rapidoid546)
-	[`rapidoid:latest`](#rapidoidlatest)

## `rapidoid:5`

```console
$ docker pull rapidoid@sha256:741659dba65ac36c022e9f2621c34d668829bce1e34fd9995a77ccd395718357
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8

### `rapidoid:5` - linux; amd64

```console
$ docker pull rapidoid@sha256:1b7c398ecc8c708ccf630f01a6264db419497c731af81048ea6ced17be345ad5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **94.1 MB (94123444 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2665fd22b9641e8e8930b8f269dea22faa16d591f483d9ccab6bdd7b3d1954da`
-	Entrypoint: `["\/opt\/entrypoint.sh"]`

```dockerfile
# Tue, 17 Jul 2018 00:28:04 GMT
ADD file:919939fa022472751b717443eea9f1d7ab5c0723f1f3a6b776d3b83d22bde818 in / 
# Tue, 17 Jul 2018 00:28:04 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 06:18:30 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:18:30 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 06:18:31 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 06:18:32 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:20:32 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 14 Aug 2018 20:36:12 GMT
ENV JAVA_VERSION=8u181
# Tue, 14 Aug 2018 20:36:12 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Tue, 14 Aug 2018 20:36:12 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 14 Aug 2018 20:36:39 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 14 Aug 2018 20:36:41 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 14 Aug 2018 22:32:41 GMT
MAINTAINER Nikolche Mihajlovski
# Tue, 14 Aug 2018 22:32:41 GMT
ENV GPG_KEY=E306FEF548C686C23DC00242B9B08D8F616EF49C
# Tue, 14 Aug 2018 22:32:42 GMT
ENV RAPIDOID_JAR=/opt/rapidoid.jar
# Tue, 14 Aug 2018 22:32:42 GMT
ENV RAPIDOID_TMP=/tmp/rapidoid
# Tue, 14 Aug 2018 22:32:43 GMT
WORKDIR /opt
# Tue, 14 Aug 2018 22:32:43 GMT
EXPOSE 8888/tcp
# Tue, 14 Aug 2018 22:32:44 GMT
VOLUME [/data]
# Tue, 14 Aug 2018 22:32:44 GMT
ENV RAPIDOID_VERSION=5.4.6
# Tue, 14 Aug 2018 22:32:44 GMT
ENV RAPIDOID_URL=https://repo1.maven.org/maven2/org/rapidoid/rapidoid-platform/5.4.6/rapidoid-platform-5.4.6.jar
# Tue, 14 Aug 2018 22:32:45 GMT
COPY file:604b8053d63179f0e45204cfaceba95b6ea008beaf1c685b80fa09ca1e982e4c in /opt/ 
# Tue, 14 Aug 2018 22:32:59 GMT
RUN set -xe     && apt-get update     && apt-get install -y --no-install-recommends         ca-certificates curl dirmngr gnupg     && mkdir /platform     && mkdir -p "$RAPIDOID_TMP" 	&& curl -SL "$RAPIDOID_URL" -o $RAPIDOID_JAR 	&& curl -SL "$RAPIDOID_URL.asc" -o $RAPIDOID_JAR.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys $GPG_KEY 	&& gpg --batch --verify $RAPIDOID_JAR.asc $RAPIDOID_JAR 	&& rm -rf "$GNUPGHOME" 	&& rm "$RAPIDOID_JAR.asc" 	&& rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 22:33:11 GMT
ENTRYPOINT ["/opt/entrypoint.sh"]
```

-	Layers:
	-	`sha256:be8881be8156e4068e611fe956aba2b9593ebd953be14fb7feea6d0659aa3abe`  
		Last Modified: Tue, 17 Jul 2018 00:44:17 GMT  
		Size: 22.5 MB (22485906 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87afd40ffc1e2ac132b1073f4b57c9f62d1a1096c3dcbd2cb5f5311a51598569`  
		Last Modified: Tue, 17 Jul 2018 06:58:30 GMT  
		Size: 454.8 KB (454827 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46c26bf1484f75a142df43d755acb0f4c9330ca74998af12b47b943409d48ed6`  
		Last Modified: Tue, 17 Jul 2018 06:58:30 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6f4da1ccc6247932be19ef1746b2e94063a6e08b9fa5da79d6ba35e71e0b7c25`  
		Last Modified: Tue, 17 Jul 2018 06:58:29 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d80f886906c83918ed786a160a2d8a71b9dae3a0f7aeef939f8b41fef97ae712`  
		Last Modified: Tue, 14 Aug 2018 20:48:50 GMT  
		Size: 55.8 MB (55834444 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bd436e56012eb11379db70e9eb5e980f3fd397dd44e8f6f43fb8777cecdb6fd`  
		Last Modified: Tue, 14 Aug 2018 20:48:34 GMT  
		Size: 246.7 KB (246689 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf5ca51ebdbc06938ffdf0f2739ce7ea4154927369a288f28a2bb8a85910e606`  
		Last Modified: Tue, 14 Aug 2018 22:33:40 GMT  
		Size: 365.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ce05d079ac600a4937e0fe5fbd6fa5ddb5d7901242b305c1912e08cb2eb1cf`  
		Last Modified: Tue, 14 Aug 2018 22:33:43 GMT  
		Size: 15.1 MB (15100836 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rapidoid:5` - linux; arm64 variant v8

```console
$ docker pull rapidoid@sha256:b4f423aa4999a2e4f7fdf938064f2e09fd91b9efa06d7c823e3730b79b9f816b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **83.4 MB (83400313 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:038bfdf7705b1419faa102d3e2b38a5a6c943e7aac83a47bc537076bdc87a8cb`
-	Entrypoint: `["\/opt\/entrypoint.sh"]`

```dockerfile
# Tue, 17 Jul 2018 08:48:06 GMT
ADD file:b6ea996ffd5aa4dade8cb1d721c2716614c03110d98683aca206c7ab52fcb9e5 in / 
# Tue, 17 Jul 2018 08:48:07 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 10:10:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 10:10:37 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 10:10:39 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 10:10:41 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 10:13:05 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 15 Aug 2018 09:32:34 GMT
ENV JAVA_VERSION=8u181
# Wed, 15 Aug 2018 09:32:35 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 15 Aug 2018 09:32:36 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 15 Aug 2018 09:33:46 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 15 Aug 2018 09:33:50 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 15 Aug 2018 10:41:14 GMT
MAINTAINER Nikolche Mihajlovski
# Wed, 15 Aug 2018 10:41:15 GMT
ENV GPG_KEY=E306FEF548C686C23DC00242B9B08D8F616EF49C
# Wed, 15 Aug 2018 10:41:16 GMT
ENV RAPIDOID_JAR=/opt/rapidoid.jar
# Wed, 15 Aug 2018 10:41:17 GMT
ENV RAPIDOID_TMP=/tmp/rapidoid
# Wed, 15 Aug 2018 10:41:17 GMT
WORKDIR /opt
# Wed, 15 Aug 2018 10:41:18 GMT
EXPOSE 8888/tcp
# Wed, 15 Aug 2018 10:41:19 GMT
VOLUME [/data]
# Wed, 15 Aug 2018 10:41:19 GMT
ENV RAPIDOID_VERSION=5.4.6
# Wed, 15 Aug 2018 10:41:20 GMT
ENV RAPIDOID_URL=https://repo1.maven.org/maven2/org/rapidoid/rapidoid-platform/5.4.6/rapidoid-platform-5.4.6.jar
# Wed, 15 Aug 2018 10:41:21 GMT
COPY file:604b8053d63179f0e45204cfaceba95b6ea008beaf1c685b80fa09ca1e982e4c in /opt/ 
# Wed, 15 Aug 2018 10:41:52 GMT
RUN set -xe     && apt-get update     && apt-get install -y --no-install-recommends         ca-certificates curl dirmngr gnupg     && mkdir /platform     && mkdir -p "$RAPIDOID_TMP" 	&& curl -SL "$RAPIDOID_URL" -o $RAPIDOID_JAR 	&& curl -SL "$RAPIDOID_URL.asc" -o $RAPIDOID_JAR.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys $GPG_KEY 	&& gpg --batch --verify $RAPIDOID_JAR.asc $RAPIDOID_JAR 	&& rm -rf "$GNUPGHOME" 	&& rm "$RAPIDOID_JAR.asc" 	&& rm -rf /var/lib/apt/lists/*
# Wed, 15 Aug 2018 10:41:53 GMT
ENTRYPOINT ["/opt/entrypoint.sh"]
```

-	Layers:
	-	`sha256:74a932489409d8d15db14c8a4a811fb46c7386bb06ea678ff27084d5657eeaaf`  
		Last Modified: Tue, 17 Jul 2018 08:57:35 GMT  
		Size: 20.3 MB (20331647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5433e5c94122fce8417f1e1de0c77f61db8737e6029447cb68ee02ca7a1518a9`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 440.8 KB (440832 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:002786a72ae7d2d250cccd3729163ff7a97d1993e5dfec3e2a222452355b26ff`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:451d05181013caa10cb13c8d0779c79735001a150f4290fa2a075ac5704dfe17`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c18731f311e831d48c0077229872b40d4720d6d9a2a6d4fb83e3d3b2221ba676`  
		Last Modified: Wed, 15 Aug 2018 09:43:54 GMT  
		Size: 48.0 MB (48005763 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e17012dd63a9d9b016e703702dbe12bf632dc920a39fb93b1e9148a458f71c7`  
		Last Modified: Wed, 15 Aug 2018 09:43:39 GMT  
		Size: 246.7 KB (246661 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbcb2d4203267c8ba3079a66d5f5a0ff660ae781b3abd3f554b193d30aad8a9a`  
		Last Modified: Wed, 15 Aug 2018 10:42:21 GMT  
		Size: 367.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f339d0e640f5ce0627bb61a4262f69c6fbf5a7729e195566de6b27dcc9c9db2`  
		Last Modified: Wed, 15 Aug 2018 10:42:24 GMT  
		Size: 14.4 MB (14374665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `rapidoid:5.4`

```console
$ docker pull rapidoid@sha256:741659dba65ac36c022e9f2621c34d668829bce1e34fd9995a77ccd395718357
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8

### `rapidoid:5.4` - linux; amd64

```console
$ docker pull rapidoid@sha256:1b7c398ecc8c708ccf630f01a6264db419497c731af81048ea6ced17be345ad5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **94.1 MB (94123444 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2665fd22b9641e8e8930b8f269dea22faa16d591f483d9ccab6bdd7b3d1954da`
-	Entrypoint: `["\/opt\/entrypoint.sh"]`

```dockerfile
# Tue, 17 Jul 2018 00:28:04 GMT
ADD file:919939fa022472751b717443eea9f1d7ab5c0723f1f3a6b776d3b83d22bde818 in / 
# Tue, 17 Jul 2018 00:28:04 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 06:18:30 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:18:30 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 06:18:31 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 06:18:32 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:20:32 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 14 Aug 2018 20:36:12 GMT
ENV JAVA_VERSION=8u181
# Tue, 14 Aug 2018 20:36:12 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Tue, 14 Aug 2018 20:36:12 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 14 Aug 2018 20:36:39 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 14 Aug 2018 20:36:41 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 14 Aug 2018 22:32:41 GMT
MAINTAINER Nikolche Mihajlovski
# Tue, 14 Aug 2018 22:32:41 GMT
ENV GPG_KEY=E306FEF548C686C23DC00242B9B08D8F616EF49C
# Tue, 14 Aug 2018 22:32:42 GMT
ENV RAPIDOID_JAR=/opt/rapidoid.jar
# Tue, 14 Aug 2018 22:32:42 GMT
ENV RAPIDOID_TMP=/tmp/rapidoid
# Tue, 14 Aug 2018 22:32:43 GMT
WORKDIR /opt
# Tue, 14 Aug 2018 22:32:43 GMT
EXPOSE 8888/tcp
# Tue, 14 Aug 2018 22:32:44 GMT
VOLUME [/data]
# Tue, 14 Aug 2018 22:32:44 GMT
ENV RAPIDOID_VERSION=5.4.6
# Tue, 14 Aug 2018 22:32:44 GMT
ENV RAPIDOID_URL=https://repo1.maven.org/maven2/org/rapidoid/rapidoid-platform/5.4.6/rapidoid-platform-5.4.6.jar
# Tue, 14 Aug 2018 22:32:45 GMT
COPY file:604b8053d63179f0e45204cfaceba95b6ea008beaf1c685b80fa09ca1e982e4c in /opt/ 
# Tue, 14 Aug 2018 22:32:59 GMT
RUN set -xe     && apt-get update     && apt-get install -y --no-install-recommends         ca-certificates curl dirmngr gnupg     && mkdir /platform     && mkdir -p "$RAPIDOID_TMP" 	&& curl -SL "$RAPIDOID_URL" -o $RAPIDOID_JAR 	&& curl -SL "$RAPIDOID_URL.asc" -o $RAPIDOID_JAR.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys $GPG_KEY 	&& gpg --batch --verify $RAPIDOID_JAR.asc $RAPIDOID_JAR 	&& rm -rf "$GNUPGHOME" 	&& rm "$RAPIDOID_JAR.asc" 	&& rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 22:33:11 GMT
ENTRYPOINT ["/opt/entrypoint.sh"]
```

-	Layers:
	-	`sha256:be8881be8156e4068e611fe956aba2b9593ebd953be14fb7feea6d0659aa3abe`  
		Last Modified: Tue, 17 Jul 2018 00:44:17 GMT  
		Size: 22.5 MB (22485906 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87afd40ffc1e2ac132b1073f4b57c9f62d1a1096c3dcbd2cb5f5311a51598569`  
		Last Modified: Tue, 17 Jul 2018 06:58:30 GMT  
		Size: 454.8 KB (454827 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46c26bf1484f75a142df43d755acb0f4c9330ca74998af12b47b943409d48ed6`  
		Last Modified: Tue, 17 Jul 2018 06:58:30 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6f4da1ccc6247932be19ef1746b2e94063a6e08b9fa5da79d6ba35e71e0b7c25`  
		Last Modified: Tue, 17 Jul 2018 06:58:29 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d80f886906c83918ed786a160a2d8a71b9dae3a0f7aeef939f8b41fef97ae712`  
		Last Modified: Tue, 14 Aug 2018 20:48:50 GMT  
		Size: 55.8 MB (55834444 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bd436e56012eb11379db70e9eb5e980f3fd397dd44e8f6f43fb8777cecdb6fd`  
		Last Modified: Tue, 14 Aug 2018 20:48:34 GMT  
		Size: 246.7 KB (246689 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf5ca51ebdbc06938ffdf0f2739ce7ea4154927369a288f28a2bb8a85910e606`  
		Last Modified: Tue, 14 Aug 2018 22:33:40 GMT  
		Size: 365.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ce05d079ac600a4937e0fe5fbd6fa5ddb5d7901242b305c1912e08cb2eb1cf`  
		Last Modified: Tue, 14 Aug 2018 22:33:43 GMT  
		Size: 15.1 MB (15100836 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rapidoid:5.4` - linux; arm64 variant v8

```console
$ docker pull rapidoid@sha256:b4f423aa4999a2e4f7fdf938064f2e09fd91b9efa06d7c823e3730b79b9f816b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **83.4 MB (83400313 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:038bfdf7705b1419faa102d3e2b38a5a6c943e7aac83a47bc537076bdc87a8cb`
-	Entrypoint: `["\/opt\/entrypoint.sh"]`

```dockerfile
# Tue, 17 Jul 2018 08:48:06 GMT
ADD file:b6ea996ffd5aa4dade8cb1d721c2716614c03110d98683aca206c7ab52fcb9e5 in / 
# Tue, 17 Jul 2018 08:48:07 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 10:10:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 10:10:37 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 10:10:39 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 10:10:41 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 10:13:05 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 15 Aug 2018 09:32:34 GMT
ENV JAVA_VERSION=8u181
# Wed, 15 Aug 2018 09:32:35 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 15 Aug 2018 09:32:36 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 15 Aug 2018 09:33:46 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 15 Aug 2018 09:33:50 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 15 Aug 2018 10:41:14 GMT
MAINTAINER Nikolche Mihajlovski
# Wed, 15 Aug 2018 10:41:15 GMT
ENV GPG_KEY=E306FEF548C686C23DC00242B9B08D8F616EF49C
# Wed, 15 Aug 2018 10:41:16 GMT
ENV RAPIDOID_JAR=/opt/rapidoid.jar
# Wed, 15 Aug 2018 10:41:17 GMT
ENV RAPIDOID_TMP=/tmp/rapidoid
# Wed, 15 Aug 2018 10:41:17 GMT
WORKDIR /opt
# Wed, 15 Aug 2018 10:41:18 GMT
EXPOSE 8888/tcp
# Wed, 15 Aug 2018 10:41:19 GMT
VOLUME [/data]
# Wed, 15 Aug 2018 10:41:19 GMT
ENV RAPIDOID_VERSION=5.4.6
# Wed, 15 Aug 2018 10:41:20 GMT
ENV RAPIDOID_URL=https://repo1.maven.org/maven2/org/rapidoid/rapidoid-platform/5.4.6/rapidoid-platform-5.4.6.jar
# Wed, 15 Aug 2018 10:41:21 GMT
COPY file:604b8053d63179f0e45204cfaceba95b6ea008beaf1c685b80fa09ca1e982e4c in /opt/ 
# Wed, 15 Aug 2018 10:41:52 GMT
RUN set -xe     && apt-get update     && apt-get install -y --no-install-recommends         ca-certificates curl dirmngr gnupg     && mkdir /platform     && mkdir -p "$RAPIDOID_TMP" 	&& curl -SL "$RAPIDOID_URL" -o $RAPIDOID_JAR 	&& curl -SL "$RAPIDOID_URL.asc" -o $RAPIDOID_JAR.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys $GPG_KEY 	&& gpg --batch --verify $RAPIDOID_JAR.asc $RAPIDOID_JAR 	&& rm -rf "$GNUPGHOME" 	&& rm "$RAPIDOID_JAR.asc" 	&& rm -rf /var/lib/apt/lists/*
# Wed, 15 Aug 2018 10:41:53 GMT
ENTRYPOINT ["/opt/entrypoint.sh"]
```

-	Layers:
	-	`sha256:74a932489409d8d15db14c8a4a811fb46c7386bb06ea678ff27084d5657eeaaf`  
		Last Modified: Tue, 17 Jul 2018 08:57:35 GMT  
		Size: 20.3 MB (20331647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5433e5c94122fce8417f1e1de0c77f61db8737e6029447cb68ee02ca7a1518a9`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 440.8 KB (440832 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:002786a72ae7d2d250cccd3729163ff7a97d1993e5dfec3e2a222452355b26ff`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:451d05181013caa10cb13c8d0779c79735001a150f4290fa2a075ac5704dfe17`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c18731f311e831d48c0077229872b40d4720d6d9a2a6d4fb83e3d3b2221ba676`  
		Last Modified: Wed, 15 Aug 2018 09:43:54 GMT  
		Size: 48.0 MB (48005763 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e17012dd63a9d9b016e703702dbe12bf632dc920a39fb93b1e9148a458f71c7`  
		Last Modified: Wed, 15 Aug 2018 09:43:39 GMT  
		Size: 246.7 KB (246661 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbcb2d4203267c8ba3079a66d5f5a0ff660ae781b3abd3f554b193d30aad8a9a`  
		Last Modified: Wed, 15 Aug 2018 10:42:21 GMT  
		Size: 367.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f339d0e640f5ce0627bb61a4262f69c6fbf5a7729e195566de6b27dcc9c9db2`  
		Last Modified: Wed, 15 Aug 2018 10:42:24 GMT  
		Size: 14.4 MB (14374665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `rapidoid:5.4.6`

```console
$ docker pull rapidoid@sha256:741659dba65ac36c022e9f2621c34d668829bce1e34fd9995a77ccd395718357
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8

### `rapidoid:5.4.6` - linux; amd64

```console
$ docker pull rapidoid@sha256:1b7c398ecc8c708ccf630f01a6264db419497c731af81048ea6ced17be345ad5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **94.1 MB (94123444 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2665fd22b9641e8e8930b8f269dea22faa16d591f483d9ccab6bdd7b3d1954da`
-	Entrypoint: `["\/opt\/entrypoint.sh"]`

```dockerfile
# Tue, 17 Jul 2018 00:28:04 GMT
ADD file:919939fa022472751b717443eea9f1d7ab5c0723f1f3a6b776d3b83d22bde818 in / 
# Tue, 17 Jul 2018 00:28:04 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 06:18:30 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:18:30 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 06:18:31 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 06:18:32 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:20:32 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 14 Aug 2018 20:36:12 GMT
ENV JAVA_VERSION=8u181
# Tue, 14 Aug 2018 20:36:12 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Tue, 14 Aug 2018 20:36:12 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 14 Aug 2018 20:36:39 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 14 Aug 2018 20:36:41 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 14 Aug 2018 22:32:41 GMT
MAINTAINER Nikolche Mihajlovski
# Tue, 14 Aug 2018 22:32:41 GMT
ENV GPG_KEY=E306FEF548C686C23DC00242B9B08D8F616EF49C
# Tue, 14 Aug 2018 22:32:42 GMT
ENV RAPIDOID_JAR=/opt/rapidoid.jar
# Tue, 14 Aug 2018 22:32:42 GMT
ENV RAPIDOID_TMP=/tmp/rapidoid
# Tue, 14 Aug 2018 22:32:43 GMT
WORKDIR /opt
# Tue, 14 Aug 2018 22:32:43 GMT
EXPOSE 8888/tcp
# Tue, 14 Aug 2018 22:32:44 GMT
VOLUME [/data]
# Tue, 14 Aug 2018 22:32:44 GMT
ENV RAPIDOID_VERSION=5.4.6
# Tue, 14 Aug 2018 22:32:44 GMT
ENV RAPIDOID_URL=https://repo1.maven.org/maven2/org/rapidoid/rapidoid-platform/5.4.6/rapidoid-platform-5.4.6.jar
# Tue, 14 Aug 2018 22:32:45 GMT
COPY file:604b8053d63179f0e45204cfaceba95b6ea008beaf1c685b80fa09ca1e982e4c in /opt/ 
# Tue, 14 Aug 2018 22:32:59 GMT
RUN set -xe     && apt-get update     && apt-get install -y --no-install-recommends         ca-certificates curl dirmngr gnupg     && mkdir /platform     && mkdir -p "$RAPIDOID_TMP" 	&& curl -SL "$RAPIDOID_URL" -o $RAPIDOID_JAR 	&& curl -SL "$RAPIDOID_URL.asc" -o $RAPIDOID_JAR.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys $GPG_KEY 	&& gpg --batch --verify $RAPIDOID_JAR.asc $RAPIDOID_JAR 	&& rm -rf "$GNUPGHOME" 	&& rm "$RAPIDOID_JAR.asc" 	&& rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 22:33:11 GMT
ENTRYPOINT ["/opt/entrypoint.sh"]
```

-	Layers:
	-	`sha256:be8881be8156e4068e611fe956aba2b9593ebd953be14fb7feea6d0659aa3abe`  
		Last Modified: Tue, 17 Jul 2018 00:44:17 GMT  
		Size: 22.5 MB (22485906 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87afd40ffc1e2ac132b1073f4b57c9f62d1a1096c3dcbd2cb5f5311a51598569`  
		Last Modified: Tue, 17 Jul 2018 06:58:30 GMT  
		Size: 454.8 KB (454827 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46c26bf1484f75a142df43d755acb0f4c9330ca74998af12b47b943409d48ed6`  
		Last Modified: Tue, 17 Jul 2018 06:58:30 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6f4da1ccc6247932be19ef1746b2e94063a6e08b9fa5da79d6ba35e71e0b7c25`  
		Last Modified: Tue, 17 Jul 2018 06:58:29 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d80f886906c83918ed786a160a2d8a71b9dae3a0f7aeef939f8b41fef97ae712`  
		Last Modified: Tue, 14 Aug 2018 20:48:50 GMT  
		Size: 55.8 MB (55834444 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bd436e56012eb11379db70e9eb5e980f3fd397dd44e8f6f43fb8777cecdb6fd`  
		Last Modified: Tue, 14 Aug 2018 20:48:34 GMT  
		Size: 246.7 KB (246689 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf5ca51ebdbc06938ffdf0f2739ce7ea4154927369a288f28a2bb8a85910e606`  
		Last Modified: Tue, 14 Aug 2018 22:33:40 GMT  
		Size: 365.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ce05d079ac600a4937e0fe5fbd6fa5ddb5d7901242b305c1912e08cb2eb1cf`  
		Last Modified: Tue, 14 Aug 2018 22:33:43 GMT  
		Size: 15.1 MB (15100836 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rapidoid:5.4.6` - linux; arm64 variant v8

```console
$ docker pull rapidoid@sha256:b4f423aa4999a2e4f7fdf938064f2e09fd91b9efa06d7c823e3730b79b9f816b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **83.4 MB (83400313 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:038bfdf7705b1419faa102d3e2b38a5a6c943e7aac83a47bc537076bdc87a8cb`
-	Entrypoint: `["\/opt\/entrypoint.sh"]`

```dockerfile
# Tue, 17 Jul 2018 08:48:06 GMT
ADD file:b6ea996ffd5aa4dade8cb1d721c2716614c03110d98683aca206c7ab52fcb9e5 in / 
# Tue, 17 Jul 2018 08:48:07 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 10:10:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 10:10:37 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 10:10:39 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 10:10:41 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 10:13:05 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 15 Aug 2018 09:32:34 GMT
ENV JAVA_VERSION=8u181
# Wed, 15 Aug 2018 09:32:35 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 15 Aug 2018 09:32:36 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 15 Aug 2018 09:33:46 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 15 Aug 2018 09:33:50 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 15 Aug 2018 10:41:14 GMT
MAINTAINER Nikolche Mihajlovski
# Wed, 15 Aug 2018 10:41:15 GMT
ENV GPG_KEY=E306FEF548C686C23DC00242B9B08D8F616EF49C
# Wed, 15 Aug 2018 10:41:16 GMT
ENV RAPIDOID_JAR=/opt/rapidoid.jar
# Wed, 15 Aug 2018 10:41:17 GMT
ENV RAPIDOID_TMP=/tmp/rapidoid
# Wed, 15 Aug 2018 10:41:17 GMT
WORKDIR /opt
# Wed, 15 Aug 2018 10:41:18 GMT
EXPOSE 8888/tcp
# Wed, 15 Aug 2018 10:41:19 GMT
VOLUME [/data]
# Wed, 15 Aug 2018 10:41:19 GMT
ENV RAPIDOID_VERSION=5.4.6
# Wed, 15 Aug 2018 10:41:20 GMT
ENV RAPIDOID_URL=https://repo1.maven.org/maven2/org/rapidoid/rapidoid-platform/5.4.6/rapidoid-platform-5.4.6.jar
# Wed, 15 Aug 2018 10:41:21 GMT
COPY file:604b8053d63179f0e45204cfaceba95b6ea008beaf1c685b80fa09ca1e982e4c in /opt/ 
# Wed, 15 Aug 2018 10:41:52 GMT
RUN set -xe     && apt-get update     && apt-get install -y --no-install-recommends         ca-certificates curl dirmngr gnupg     && mkdir /platform     && mkdir -p "$RAPIDOID_TMP" 	&& curl -SL "$RAPIDOID_URL" -o $RAPIDOID_JAR 	&& curl -SL "$RAPIDOID_URL.asc" -o $RAPIDOID_JAR.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys $GPG_KEY 	&& gpg --batch --verify $RAPIDOID_JAR.asc $RAPIDOID_JAR 	&& rm -rf "$GNUPGHOME" 	&& rm "$RAPIDOID_JAR.asc" 	&& rm -rf /var/lib/apt/lists/*
# Wed, 15 Aug 2018 10:41:53 GMT
ENTRYPOINT ["/opt/entrypoint.sh"]
```

-	Layers:
	-	`sha256:74a932489409d8d15db14c8a4a811fb46c7386bb06ea678ff27084d5657eeaaf`  
		Last Modified: Tue, 17 Jul 2018 08:57:35 GMT  
		Size: 20.3 MB (20331647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5433e5c94122fce8417f1e1de0c77f61db8737e6029447cb68ee02ca7a1518a9`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 440.8 KB (440832 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:002786a72ae7d2d250cccd3729163ff7a97d1993e5dfec3e2a222452355b26ff`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:451d05181013caa10cb13c8d0779c79735001a150f4290fa2a075ac5704dfe17`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c18731f311e831d48c0077229872b40d4720d6d9a2a6d4fb83e3d3b2221ba676`  
		Last Modified: Wed, 15 Aug 2018 09:43:54 GMT  
		Size: 48.0 MB (48005763 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e17012dd63a9d9b016e703702dbe12bf632dc920a39fb93b1e9148a458f71c7`  
		Last Modified: Wed, 15 Aug 2018 09:43:39 GMT  
		Size: 246.7 KB (246661 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbcb2d4203267c8ba3079a66d5f5a0ff660ae781b3abd3f554b193d30aad8a9a`  
		Last Modified: Wed, 15 Aug 2018 10:42:21 GMT  
		Size: 367.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f339d0e640f5ce0627bb61a4262f69c6fbf5a7729e195566de6b27dcc9c9db2`  
		Last Modified: Wed, 15 Aug 2018 10:42:24 GMT  
		Size: 14.4 MB (14374665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `rapidoid:latest`

```console
$ docker pull rapidoid@sha256:741659dba65ac36c022e9f2621c34d668829bce1e34fd9995a77ccd395718357
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8

### `rapidoid:latest` - linux; amd64

```console
$ docker pull rapidoid@sha256:1b7c398ecc8c708ccf630f01a6264db419497c731af81048ea6ced17be345ad5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **94.1 MB (94123444 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2665fd22b9641e8e8930b8f269dea22faa16d591f483d9ccab6bdd7b3d1954da`
-	Entrypoint: `["\/opt\/entrypoint.sh"]`

```dockerfile
# Tue, 17 Jul 2018 00:28:04 GMT
ADD file:919939fa022472751b717443eea9f1d7ab5c0723f1f3a6b776d3b83d22bde818 in / 
# Tue, 17 Jul 2018 00:28:04 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 06:18:30 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:18:30 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 06:18:31 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 06:18:32 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:20:32 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 14 Aug 2018 20:36:12 GMT
ENV JAVA_VERSION=8u181
# Tue, 14 Aug 2018 20:36:12 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Tue, 14 Aug 2018 20:36:12 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 14 Aug 2018 20:36:39 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 14 Aug 2018 20:36:41 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 14 Aug 2018 22:32:41 GMT
MAINTAINER Nikolche Mihajlovski
# Tue, 14 Aug 2018 22:32:41 GMT
ENV GPG_KEY=E306FEF548C686C23DC00242B9B08D8F616EF49C
# Tue, 14 Aug 2018 22:32:42 GMT
ENV RAPIDOID_JAR=/opt/rapidoid.jar
# Tue, 14 Aug 2018 22:32:42 GMT
ENV RAPIDOID_TMP=/tmp/rapidoid
# Tue, 14 Aug 2018 22:32:43 GMT
WORKDIR /opt
# Tue, 14 Aug 2018 22:32:43 GMT
EXPOSE 8888/tcp
# Tue, 14 Aug 2018 22:32:44 GMT
VOLUME [/data]
# Tue, 14 Aug 2018 22:32:44 GMT
ENV RAPIDOID_VERSION=5.4.6
# Tue, 14 Aug 2018 22:32:44 GMT
ENV RAPIDOID_URL=https://repo1.maven.org/maven2/org/rapidoid/rapidoid-platform/5.4.6/rapidoid-platform-5.4.6.jar
# Tue, 14 Aug 2018 22:32:45 GMT
COPY file:604b8053d63179f0e45204cfaceba95b6ea008beaf1c685b80fa09ca1e982e4c in /opt/ 
# Tue, 14 Aug 2018 22:32:59 GMT
RUN set -xe     && apt-get update     && apt-get install -y --no-install-recommends         ca-certificates curl dirmngr gnupg     && mkdir /platform     && mkdir -p "$RAPIDOID_TMP" 	&& curl -SL "$RAPIDOID_URL" -o $RAPIDOID_JAR 	&& curl -SL "$RAPIDOID_URL.asc" -o $RAPIDOID_JAR.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys $GPG_KEY 	&& gpg --batch --verify $RAPIDOID_JAR.asc $RAPIDOID_JAR 	&& rm -rf "$GNUPGHOME" 	&& rm "$RAPIDOID_JAR.asc" 	&& rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 22:33:11 GMT
ENTRYPOINT ["/opt/entrypoint.sh"]
```

-	Layers:
	-	`sha256:be8881be8156e4068e611fe956aba2b9593ebd953be14fb7feea6d0659aa3abe`  
		Last Modified: Tue, 17 Jul 2018 00:44:17 GMT  
		Size: 22.5 MB (22485906 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87afd40ffc1e2ac132b1073f4b57c9f62d1a1096c3dcbd2cb5f5311a51598569`  
		Last Modified: Tue, 17 Jul 2018 06:58:30 GMT  
		Size: 454.8 KB (454827 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46c26bf1484f75a142df43d755acb0f4c9330ca74998af12b47b943409d48ed6`  
		Last Modified: Tue, 17 Jul 2018 06:58:30 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6f4da1ccc6247932be19ef1746b2e94063a6e08b9fa5da79d6ba35e71e0b7c25`  
		Last Modified: Tue, 17 Jul 2018 06:58:29 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d80f886906c83918ed786a160a2d8a71b9dae3a0f7aeef939f8b41fef97ae712`  
		Last Modified: Tue, 14 Aug 2018 20:48:50 GMT  
		Size: 55.8 MB (55834444 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bd436e56012eb11379db70e9eb5e980f3fd397dd44e8f6f43fb8777cecdb6fd`  
		Last Modified: Tue, 14 Aug 2018 20:48:34 GMT  
		Size: 246.7 KB (246689 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf5ca51ebdbc06938ffdf0f2739ce7ea4154927369a288f28a2bb8a85910e606`  
		Last Modified: Tue, 14 Aug 2018 22:33:40 GMT  
		Size: 365.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ce05d079ac600a4937e0fe5fbd6fa5ddb5d7901242b305c1912e08cb2eb1cf`  
		Last Modified: Tue, 14 Aug 2018 22:33:43 GMT  
		Size: 15.1 MB (15100836 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rapidoid:latest` - linux; arm64 variant v8

```console
$ docker pull rapidoid@sha256:b4f423aa4999a2e4f7fdf938064f2e09fd91b9efa06d7c823e3730b79b9f816b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **83.4 MB (83400313 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:038bfdf7705b1419faa102d3e2b38a5a6c943e7aac83a47bc537076bdc87a8cb`
-	Entrypoint: `["\/opt\/entrypoint.sh"]`

```dockerfile
# Tue, 17 Jul 2018 08:48:06 GMT
ADD file:b6ea996ffd5aa4dade8cb1d721c2716614c03110d98683aca206c7ab52fcb9e5 in / 
# Tue, 17 Jul 2018 08:48:07 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 10:10:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 10:10:37 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 10:10:39 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 10:10:41 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 10:13:05 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 15 Aug 2018 09:32:34 GMT
ENV JAVA_VERSION=8u181
# Wed, 15 Aug 2018 09:32:35 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 15 Aug 2018 09:32:36 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 15 Aug 2018 09:33:46 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 15 Aug 2018 09:33:50 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 15 Aug 2018 10:41:14 GMT
MAINTAINER Nikolche Mihajlovski
# Wed, 15 Aug 2018 10:41:15 GMT
ENV GPG_KEY=E306FEF548C686C23DC00242B9B08D8F616EF49C
# Wed, 15 Aug 2018 10:41:16 GMT
ENV RAPIDOID_JAR=/opt/rapidoid.jar
# Wed, 15 Aug 2018 10:41:17 GMT
ENV RAPIDOID_TMP=/tmp/rapidoid
# Wed, 15 Aug 2018 10:41:17 GMT
WORKDIR /opt
# Wed, 15 Aug 2018 10:41:18 GMT
EXPOSE 8888/tcp
# Wed, 15 Aug 2018 10:41:19 GMT
VOLUME [/data]
# Wed, 15 Aug 2018 10:41:19 GMT
ENV RAPIDOID_VERSION=5.4.6
# Wed, 15 Aug 2018 10:41:20 GMT
ENV RAPIDOID_URL=https://repo1.maven.org/maven2/org/rapidoid/rapidoid-platform/5.4.6/rapidoid-platform-5.4.6.jar
# Wed, 15 Aug 2018 10:41:21 GMT
COPY file:604b8053d63179f0e45204cfaceba95b6ea008beaf1c685b80fa09ca1e982e4c in /opt/ 
# Wed, 15 Aug 2018 10:41:52 GMT
RUN set -xe     && apt-get update     && apt-get install -y --no-install-recommends         ca-certificates curl dirmngr gnupg     && mkdir /platform     && mkdir -p "$RAPIDOID_TMP" 	&& curl -SL "$RAPIDOID_URL" -o $RAPIDOID_JAR 	&& curl -SL "$RAPIDOID_URL.asc" -o $RAPIDOID_JAR.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys $GPG_KEY 	&& gpg --batch --verify $RAPIDOID_JAR.asc $RAPIDOID_JAR 	&& rm -rf "$GNUPGHOME" 	&& rm "$RAPIDOID_JAR.asc" 	&& rm -rf /var/lib/apt/lists/*
# Wed, 15 Aug 2018 10:41:53 GMT
ENTRYPOINT ["/opt/entrypoint.sh"]
```

-	Layers:
	-	`sha256:74a932489409d8d15db14c8a4a811fb46c7386bb06ea678ff27084d5657eeaaf`  
		Last Modified: Tue, 17 Jul 2018 08:57:35 GMT  
		Size: 20.3 MB (20331647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5433e5c94122fce8417f1e1de0c77f61db8737e6029447cb68ee02ca7a1518a9`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 440.8 KB (440832 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:002786a72ae7d2d250cccd3729163ff7a97d1993e5dfec3e2a222452355b26ff`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:451d05181013caa10cb13c8d0779c79735001a150f4290fa2a075ac5704dfe17`  
		Last Modified: Tue, 17 Jul 2018 10:37:29 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c18731f311e831d48c0077229872b40d4720d6d9a2a6d4fb83e3d3b2221ba676`  
		Last Modified: Wed, 15 Aug 2018 09:43:54 GMT  
		Size: 48.0 MB (48005763 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e17012dd63a9d9b016e703702dbe12bf632dc920a39fb93b1e9148a458f71c7`  
		Last Modified: Wed, 15 Aug 2018 09:43:39 GMT  
		Size: 246.7 KB (246661 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbcb2d4203267c8ba3079a66d5f5a0ff660ae781b3abd3f554b193d30aad8a9a`  
		Last Modified: Wed, 15 Aug 2018 10:42:21 GMT  
		Size: 367.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f339d0e640f5ce0627bb61a4262f69c6fbf5a7729e195566de6b27dcc9c9db2`  
		Last Modified: Wed, 15 Aug 2018 10:42:24 GMT  
		Size: 14.4 MB (14374665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
