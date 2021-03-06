## `maven:3-jdk-11-slim`

```console
$ docker pull maven@sha256:bf9a7a31555b404186a92f1e55ba647710882f0997fb309d0ee57e25a442ea1c
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `maven:3-jdk-11-slim` - linux; amd64

```console
$ docker pull maven@sha256:533aa10bdb30edc3fec9dd32effbf536245004a605ab66174c3c294282a168d3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **327.2 MB (327180962 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:647a4a8b92c6823d5194451c4168b0f9cb30632bef23cf9f143707ed171fe31e`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 00:25:12 GMT
ADD file:f91110c5482cb29a759356df06fea755606755e05306ca55f921f44a5b9470fb in / 
# Tue, 17 Jul 2018 00:25:12 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 06:09:53 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:09:54 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 06:09:55 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 06:09:55 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:09:56 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 22 Aug 2018 21:13:17 GMT
ENV JAVA_VERSION=11-ea+27
# Wed, 22 Aug 2018 21:13:17 GMT
ENV JAVA_DEBIAN_VERSION=11~27-1
# Wed, 22 Aug 2018 21:14:04 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 22 Aug 2018 21:14:05 GMT
CMD ["jshell"]
# Wed, 22 Aug 2018 22:20:24 GMT
ARG MAVEN_VERSION=3.5.4
# Wed, 22 Aug 2018 22:20:24 GMT
ARG USER_HOME_DIR=/root
# Wed, 22 Aug 2018 22:20:25 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Wed, 22 Aug 2018 22:20:25 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Wed, 22 Aug 2018 22:20:38 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 22:20:39 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Wed, 22 Aug 2018 22:20:42 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Wed, 22 Aug 2018 22:20:42 GMT
ENV MAVEN_HOME=/usr/share/maven
# Wed, 22 Aug 2018 22:20:43 GMT
ENV MAVEN_CONFIG=/root/.m2
# Wed, 22 Aug 2018 22:20:43 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Wed, 22 Aug 2018 22:20:44 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Wed, 22 Aug 2018 22:20:44 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Wed, 22 Aug 2018 22:20:44 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:21c77be511c9830e11f7da7f8796340d6103e5b1e4124bb1639947aa0f11c19e`  
		Last Modified: Tue, 17 Jul 2018 00:40:27 GMT  
		Size: 26.2 MB (26153708 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c9a9bc4c131a474462e235e575844d60055d3904745b1cd7e9bcb0bbd1ed82b7`  
		Last Modified: Tue, 17 Jul 2018 06:33:28 GMT  
		Size: 460.1 KB (460144 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a85403034af41f2da36b479c531eb04f843b0af4715e65ee84a91e1fbb5f1bf9`  
		Last Modified: Tue, 17 Jul 2018 06:33:27 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcd5e0c34299187bbde044e4b8e5f7de695a016f6b69d6794a3ea6142e320d1a`  
		Last Modified: Tue, 17 Jul 2018 06:33:28 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f9f0e1e5ed5073f7f0b6e20d7e3dc35236f0cab4befa5494830871d6df6bfb9`  
		Last Modified: Wed, 22 Aug 2018 21:26:49 GMT  
		Size: 289.4 MB (289409141 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:77d548335fd4aa6895ffc76673b271789a59bae036eae8742f240cfc73925dfb`  
		Last Modified: Wed, 22 Aug 2018 22:23:23 GMT  
		Size: 2.2 MB (2167061 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9c06071916ba7beaa173764e8035f8237e48bd00d5fdd77fe52fe25241820eb`  
		Last Modified: Wed, 22 Aug 2018 22:23:22 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:574b44836831f3fe685d3c99df9313c83739b5412ce9390f6619491f82810b38`  
		Last Modified: Wed, 22 Aug 2018 22:23:23 GMT  
		Size: 9.0 MB (8989212 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70240c6c6f6b7f1076014286689e9e1c59c057b7e408430c14cb0fcaa518b513`  
		Last Modified: Wed, 22 Aug 2018 22:23:22 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23fa4a89af0f44b1b5f805fd5c8ec92455a02bf84b2be0d83cd1f80938fce4c0`  
		Last Modified: Wed, 22 Aug 2018 22:23:22 GMT  
		Size: 359.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; arm variant v5

```console
$ docker pull maven@sha256:771749de774a3b5cadfa2011baa8dde0c394a0ae8aa71c87f379227a4ba05635
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **259.8 MB (259842749 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8b3ab370f4899d6119369a9b5f7f3d289140f61d131f46e2dc7388110cd3c879`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 08:54:21 GMT
ADD file:0107574479f07d37c0ea231a8738bc043ef67d41f1a4730c4004055700bb0492 in / 
# Tue, 17 Jul 2018 08:54:22 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 09:14:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 09:14:16 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 09:14:17 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 09:14:18 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 09:14:18 GMT
ENV JAVA_HOME=/docker-java-home
# Thu, 23 Aug 2018 08:53:28 GMT
ENV JAVA_VERSION=11-ea+27
# Thu, 23 Aug 2018 08:53:28 GMT
ENV JAVA_DEBIAN_VERSION=11~27-1
# Thu, 23 Aug 2018 08:54:12 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 23 Aug 2018 08:54:12 GMT
CMD ["jshell"]
# Thu, 23 Aug 2018 11:30:02 GMT
ARG MAVEN_VERSION=3.5.4
# Thu, 23 Aug 2018 11:30:02 GMT
ARG USER_HOME_DIR=/root
# Thu, 23 Aug 2018 11:30:02 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Thu, 23 Aug 2018 11:30:02 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Thu, 23 Aug 2018 11:30:17 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 11:30:22 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Thu, 23 Aug 2018 11:30:27 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Thu, 23 Aug 2018 11:30:28 GMT
ENV MAVEN_HOME=/usr/share/maven
# Thu, 23 Aug 2018 11:30:28 GMT
ENV MAVEN_CONFIG=/root/.m2
# Thu, 23 Aug 2018 11:30:28 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Thu, 23 Aug 2018 11:30:29 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Thu, 23 Aug 2018 11:30:29 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Thu, 23 Aug 2018 11:30:29 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:acea72f1ecd7951289e77c440c4f3aaf77848b2faad76bd7e8db097abfd2d14d`  
		Last Modified: Tue, 17 Jul 2018 09:06:47 GMT  
		Size: 24.1 MB (24086179 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a7f1b1d984fcd3ca8b479950705e6b86d08f519f9188906659654128bb914826`  
		Last Modified: Tue, 17 Jul 2018 09:24:51 GMT  
		Size: 453.7 KB (453659 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b1f488e93cd0d679131e5e9688de12c41011ef24684777d7b3752a1f7b3ff8f8`  
		Last Modified: Tue, 17 Jul 2018 09:24:50 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14f280a5dce6cfac3dc45f43e3940509a8a59d388361aa6e3f6efe35df7ed4c3`  
		Last Modified: Sat, 21 Jul 2018 11:10:16 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:283236d5e0dac024b8981f0a51e6c646cacb495e6c10cea12d7022f9fbb52523`  
		Last Modified: Thu, 23 Aug 2018 08:59:51 GMT  
		Size: 224.3 MB (224282068 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0a70ebf9b351f7bfc3e9c48dba5292dc9e93d16ccc3a5da19c3c56c80f91f48`  
		Last Modified: Thu, 23 Aug 2018 11:31:27 GMT  
		Size: 2.0 MB (2029915 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c87974286de2dd11e3eb0036f3c6667baa3c0b17dbf85adb911458f4c5c2a619`  
		Last Modified: Thu, 23 Aug 2018 11:31:27 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b3acaaa76990598a36dd4624489af7a73c1053421eb72726ce277f62b1a30b9b`  
		Last Modified: Thu, 23 Aug 2018 11:31:29 GMT  
		Size: 9.0 MB (8989235 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:765fb2a80a3ff71e5d11c0b394bf955982dcb6e3a8800a631b4302c43f1c5994`  
		Last Modified: Thu, 23 Aug 2018 11:31:27 GMT  
		Size: 741.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fbb999e7f63b659879e892e37162af2d077daade1406eb73300e93f61e8bd7dc`  
		Last Modified: Thu, 23 Aug 2018 11:31:27 GMT  
		Size: 361.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; arm variant v7

```console
$ docker pull maven@sha256:db6f408dd2ca6529f3bb30f48055fccec9cd5980d651af059778156e002bc2b9
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **282.4 MB (282350638 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0aa2903495f7ece6da6eb2bcf86ca661ab2ac847daad6ebe3430ef214ae2bdef`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 12:03:40 GMT
ADD file:430c173aee26cd9ee26f12a79095a7590ef88c7c48a0ae19a07a09942eaae79a in / 
# Tue, 17 Jul 2018 12:03:41 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 12:34:47 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 12:34:48 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 12:34:49 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 12:34:50 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 12:34:50 GMT
ENV JAVA_HOME=/docker-java-home
# Thu, 23 Aug 2018 11:59:55 GMT
ENV JAVA_VERSION=11-ea+27
# Thu, 23 Aug 2018 11:59:56 GMT
ENV JAVA_DEBIAN_VERSION=11~27-1
# Thu, 23 Aug 2018 12:00:53 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 23 Aug 2018 12:00:53 GMT
CMD ["jshell"]
# Thu, 23 Aug 2018 13:36:54 GMT
ARG MAVEN_VERSION=3.5.4
# Thu, 23 Aug 2018 13:36:54 GMT
ARG USER_HOME_DIR=/root
# Thu, 23 Aug 2018 13:36:54 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Thu, 23 Aug 2018 13:36:55 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Thu, 23 Aug 2018 13:37:03 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 13:37:04 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Thu, 23 Aug 2018 13:37:10 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Thu, 23 Aug 2018 13:37:15 GMT
ENV MAVEN_HOME=/usr/share/maven
# Thu, 23 Aug 2018 13:37:15 GMT
ENV MAVEN_CONFIG=/root/.m2
# Thu, 23 Aug 2018 13:37:15 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Thu, 23 Aug 2018 13:37:16 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Thu, 23 Aug 2018 13:37:16 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Thu, 23 Aug 2018 13:37:16 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:1e5341b5f8a7f0c7e651d696478846f375e478fc35a15daad21057ed34c86aa0`  
		Last Modified: Tue, 17 Jul 2018 12:16:07 GMT  
		Size: 22.1 MB (22054548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:201706a9d8742be6b39b2112a52a81180a89c547979584ec52ab950ef13a4768`  
		Last Modified: Tue, 17 Jul 2018 12:55:17 GMT  
		Size: 436.3 KB (436272 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1db9f0721f2ca238b0a84c406f829b0b7c9a960dd91b6ebd65d2e4825db85f79`  
		Last Modified: Tue, 17 Jul 2018 12:55:17 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4dc9b2cda3454dd54d9134d49524faa78c52f7dbf220f21d80d55fb384c98815`  
		Last Modified: Tue, 17 Jul 2018 12:55:17 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:943adbb2e0699122cabad595e5929c3cdbf90be50f384514c9dc29ed5231213c`  
		Last Modified: Thu, 23 Aug 2018 12:12:44 GMT  
		Size: 249.0 MB (248979934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00766965f1404188704780037efe6d08391599ab38ab731e1e8e0af352ed1637`  
		Last Modified: Thu, 23 Aug 2018 13:38:06 GMT  
		Size: 1.9 MB (1888952 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a4634f5f74255b7a94bd5d5c06ff84191bd1fd4b8a644278f99fd1a09618d11e`  
		Last Modified: Thu, 23 Aug 2018 13:38:06 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:569a3c69f769a57e8bd9fe2a3667335999691c1303f1da1175455b594bb37ad3`  
		Last Modified: Thu, 23 Aug 2018 13:38:07 GMT  
		Size: 9.0 MB (8989237 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48fe779116f8ef06a77ec19b03888d27768451e7f9bc5a5c21cc0af4005ba48f`  
		Last Modified: Thu, 23 Aug 2018 13:38:06 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80ea9d686e9d8612adcf0dda29cb823c692517b26c424c8b7e6733464faab0af`  
		Last Modified: Thu, 23 Aug 2018 13:38:06 GMT  
		Size: 361.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; arm64 variant v8

```console
$ docker pull maven@sha256:cb884154d19dc39af15d18cdc693d961e1455cf586e605d7f288b23638ed65b9
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **313.2 MB (313212452 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5250d264efa52f0aef30605e0cbbe6e1cd36a3f4723c994107c57ca29efd5be4`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 08:44:27 GMT
ADD file:7441783fb02cfd0ec33462b944c21331e3ad1da6f38a9c835f677cb88c6dd7ec in / 
# Tue, 17 Jul 2018 08:44:33 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 09:56:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 09:56:59 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 09:57:01 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 09:57:03 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 09:57:04 GMT
ENV JAVA_HOME=/docker-java-home
# Thu, 23 Aug 2018 09:40:35 GMT
ENV JAVA_VERSION=11-ea+27
# Thu, 23 Aug 2018 09:40:37 GMT
ENV JAVA_DEBIAN_VERSION=11~27-1
# Thu, 23 Aug 2018 09:43:13 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 23 Aug 2018 09:43:15 GMT
CMD ["jshell"]
# Thu, 23 Aug 2018 19:14:00 GMT
ARG MAVEN_VERSION=3.5.4
# Thu, 23 Aug 2018 19:14:00 GMT
ARG USER_HOME_DIR=/root
# Thu, 23 Aug 2018 19:14:01 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Thu, 23 Aug 2018 19:14:02 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Thu, 23 Aug 2018 19:14:31 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 19:14:45 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Thu, 23 Aug 2018 19:14:49 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Thu, 23 Aug 2018 19:14:50 GMT
ENV MAVEN_HOME=/usr/share/maven
# Thu, 23 Aug 2018 19:14:50 GMT
ENV MAVEN_CONFIG=/root/.m2
# Thu, 23 Aug 2018 19:14:51 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Thu, 23 Aug 2018 19:14:52 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Thu, 23 Aug 2018 19:14:53 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Thu, 23 Aug 2018 19:14:54 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:458ba916572f94d66f19aa3ff0115bc9864ed4d91c67787dcfcbb4b00bfbdb97`  
		Last Modified: Tue, 17 Jul 2018 08:53:47 GMT  
		Size: 23.5 MB (23468736 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7e2b81cd49e56ea3c4cae916184f441c675aa527aa693a54010d266d76746f7`  
		Last Modified: Tue, 17 Jul 2018 10:23:50 GMT  
		Size: 445.0 KB (445018 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a478f77447653d89e7bb16b1270e51445b598b0c48ed8f7046fcc124bae1ae83`  
		Last Modified: Tue, 17 Jul 2018 10:23:50 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1bc9f58532813326e8baa3cbeec0ebfb917decee942701852fd3967c2502cc4a`  
		Last Modified: Tue, 17 Jul 2018 10:23:50 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee34b4f7921de3dd13b3dc435d3c2b06865a9e32ef091effabfa89688558425f`  
		Last Modified: Thu, 23 Aug 2018 10:03:33 GMT  
		Size: 278.2 MB (278243161 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f36ae8bf35e4b6c5377d00f30661ba97f01515d3560edfb57d19a47087920458`  
		Last Modified: Thu, 23 Aug 2018 19:17:06 GMT  
		Size: 2.1 MB (2064631 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:307cf6ebd5b3fd8bc1f825213d4d862ed3de153a33a89da691ae38ca06443c99`  
		Last Modified: Thu, 23 Aug 2018 19:17:03 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:560db2c17687e85f16cf1c1f7485e5257695a4a4c33e15ff8d23ae770a8d4634`  
		Last Modified: Thu, 23 Aug 2018 19:17:04 GMT  
		Size: 9.0 MB (8989208 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d84a5b9be033dccd29c12f6e4fabb5cc90a7799603c883892482f91e0a32ee4`  
		Last Modified: Thu, 23 Aug 2018 19:17:04 GMT  
		Size: 744.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1556a635cff243c6c5d52e082ad002ea8538f98bf92da0f5c0ab19d586df7edd`  
		Last Modified: Thu, 23 Aug 2018 19:17:03 GMT  
		Size: 360.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; 386

```console
$ docker pull maven@sha256:dfc2d801c7a1d992cf9175c92c1a34533c20cba1fb2ad849d668fec384f71bab
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **411.3 MB (411265405 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6297dd987de89357f3640e9cca8398744082d53108bf14ddda84a507478ef45c`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 10:47:10 GMT
ADD file:20144dcfd227e7e2fd2fa000865bff7a8586b26f763501c4602235f1d4f04119 in / 
# Tue, 17 Jul 2018 10:47:18 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 11:22:04 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 11:22:06 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 11:22:07 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 11:22:09 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 11:22:09 GMT
ENV JAVA_HOME=/docker-java-home
# Thu, 23 Aug 2018 11:12:36 GMT
ENV JAVA_VERSION=11-ea+27
# Thu, 23 Aug 2018 11:12:36 GMT
ENV JAVA_DEBIAN_VERSION=11~27-1
# Thu, 23 Aug 2018 11:13:45 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 23 Aug 2018 11:13:45 GMT
CMD ["jshell"]
# Thu, 23 Aug 2018 16:08:22 GMT
ARG MAVEN_VERSION=3.5.4
# Thu, 23 Aug 2018 16:08:23 GMT
ARG USER_HOME_DIR=/root
# Thu, 23 Aug 2018 16:08:23 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Thu, 23 Aug 2018 16:08:23 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Thu, 23 Aug 2018 16:08:53 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 16:08:57 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Thu, 23 Aug 2018 16:09:00 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Thu, 23 Aug 2018 16:09:01 GMT
ENV MAVEN_HOME=/usr/share/maven
# Thu, 23 Aug 2018 16:09:01 GMT
ENV MAVEN_CONFIG=/root/.m2
# Thu, 23 Aug 2018 16:09:01 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Thu, 23 Aug 2018 16:09:02 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Thu, 23 Aug 2018 16:09:02 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Thu, 23 Aug 2018 16:09:02 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:5dfc5302b4bfc84b249f67f2e7094fdf4be54645eb3b6ce014c0c7ecca1e6df4`  
		Last Modified: Tue, 17 Jul 2018 11:04:29 GMT  
		Size: 26.8 MB (26847422 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5c2f3a405923c070ef2fc1a30ce2d9036eee908d3d315c21569898eb8390c12e`  
		Last Modified: Tue, 17 Jul 2018 11:40:12 GMT  
		Size: 468.8 KB (468803 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12d96811d096ea29f146e1f9e59c6100f66189bee526673d4cc256ae946095fe`  
		Last Modified: Tue, 17 Jul 2018 11:40:12 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f4c5731eb629f64cb6cf33bd9be4f0ccc2af036f5e4d4fc2cd686c5dd88a1832`  
		Last Modified: Tue, 17 Jul 2018 11:40:12 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b0adbdd3512807a7dcf4af442f5100cd2e9f0a32412cc4f5f7e7c755d2b9ff9c`  
		Last Modified: Thu, 23 Aug 2018 11:23:33 GMT  
		Size: 372.7 MB (372683473 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:066fdb85f5c9b14b5825f19251f041175d81278f298ac61586d6032127343f42`  
		Last Modified: Thu, 23 Aug 2018 16:10:23 GMT  
		Size: 2.3 MB (2274795 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dafc4590e3096e6d322c3a084d6e2639f5fa9ebb75307e3d4c06653559e3ff71`  
		Last Modified: Thu, 23 Aug 2018 16:10:22 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70a249ead7e1b6a7a98a6ee52a790c2537b23f47283af7e1558c4ba7d753dbe1`  
		Last Modified: Thu, 23 Aug 2018 16:10:24 GMT  
		Size: 9.0 MB (8989214 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:26ea9a97c86d44ea193c8feb4499b5fcc63694d2c5745555913f747501d71fd7`  
		Last Modified: Thu, 23 Aug 2018 16:10:22 GMT  
		Size: 745.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:447dc1b996d9282a7a23bd1cb324d5ff887e2f85505470fd051f33599a48221c`  
		Last Modified: Thu, 23 Aug 2018 16:10:22 GMT  
		Size: 361.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; ppc64le

```console
$ docker pull maven@sha256:80f65c62a801acb22297e51cb6fdf3f8d46ba06669793a723e4ac83118bf26bc
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **303.5 MB (303474900 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1d853158b5e7794d3888eba13b64a1f9e58ca8bc7f9a13a63a0ee5a1d9846fae`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 08:18:51 GMT
ADD file:2854a5536a6cd3d364473dbde290890875599447fe57e02214642a7ea4c4199a in / 
# Tue, 17 Jul 2018 08:18:54 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 08:49:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 08:49:34 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 08:49:37 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 08:49:38 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 08:49:39 GMT
ENV JAVA_HOME=/docker-java-home
# Thu, 23 Aug 2018 08:55:30 GMT
ENV JAVA_VERSION=11-ea+27
# Thu, 23 Aug 2018 08:55:32 GMT
ENV JAVA_DEBIAN_VERSION=11~27-1
# Thu, 23 Aug 2018 08:56:54 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 23 Aug 2018 08:56:56 GMT
CMD ["jshell"]
# Thu, 23 Aug 2018 13:16:52 GMT
ARG MAVEN_VERSION=3.5.4
# Thu, 23 Aug 2018 13:16:55 GMT
ARG USER_HOME_DIR=/root
# Thu, 23 Aug 2018 13:17:15 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Thu, 23 Aug 2018 13:17:40 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Thu, 23 Aug 2018 13:18:24 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 13:18:29 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Thu, 23 Aug 2018 13:18:39 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Thu, 23 Aug 2018 13:18:45 GMT
ENV MAVEN_HOME=/usr/share/maven
# Thu, 23 Aug 2018 13:19:45 GMT
ENV MAVEN_CONFIG=/root/.m2
# Thu, 23 Aug 2018 13:20:42 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Thu, 23 Aug 2018 13:20:43 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Thu, 23 Aug 2018 13:20:45 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Thu, 23 Aug 2018 13:20:46 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:c0079deb5131e41ff48e218a11dc6d4aaf2ee6f48d4674431d4da149f01bd944`  
		Last Modified: Tue, 17 Jul 2018 08:24:11 GMT  
		Size: 27.4 MB (27423639 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dcf7a34d4ae23534bc74ed18c6c3b2d4528589acd4a6c4ed1172442e070315e5`  
		Last Modified: Tue, 17 Jul 2018 09:43:03 GMT  
		Size: 454.8 KB (454843 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2189ec7f1e039011f776c44f0becd3e5065e0a06e25dca83d56e0698d7c16fdc`  
		Last Modified: Tue, 17 Jul 2018 09:43:02 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:20a24d44be9692f4c723c652f3ab74ad80496ecfa0a51aecc2f812334ba67821`  
		Last Modified: Tue, 17 Jul 2018 09:43:01 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3977eb21b8eee11c8a485a4fa15beedc4f636a86e7efde564d0d21480b431a0f`  
		Last Modified: Thu, 23 Aug 2018 09:06:27 GMT  
		Size: 264.3 MB (264275620 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1df7c53435c9a462423a0675d91dd0fedfc8cc73d8629f48a98358549e2f56b`  
		Last Modified: Thu, 23 Aug 2018 13:23:40 GMT  
		Size: 2.3 MB (2329857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:73ef39ef42c1aab2e51cd03dbc7b6406a5170daf9c63916fc354547fbe329cc3`  
		Last Modified: Thu, 23 Aug 2018 13:23:39 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9140c3fd30bdb623e85eab98576fcfcf7b7bfe852a3abf4e2ee2cd07a62f03b3`  
		Last Modified: Thu, 23 Aug 2018 13:23:41 GMT  
		Size: 9.0 MB (8989242 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c7181ff01b7478d228424b17d2b800c1c095ee844a3a68cbcb893b3af1100973`  
		Last Modified: Thu, 23 Aug 2018 13:23:39 GMT  
		Size: 744.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4beb511695dde56602e1bb6ad5d829f35391ce14d1c4b51b597bb357e44e8e4b`  
		Last Modified: Thu, 23 Aug 2018 13:23:40 GMT  
		Size: 361.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-11-slim` - linux; s390x

```console
$ docker pull maven@sha256:8c2cbcf67641d18eb4bb090262dc754c7efc0f54c16bf40d21d5e55924e865f3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **297.0 MB (297041735 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b0f059f60e00283dd53fe3f14bc92bcb5f95bd3c08015bf45a41f40ed675e4b5`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 11:42:33 GMT
ADD file:34516dd4f3a5de10b651fdb63328fddb718471eaf74d2efaa6760e1cc35f585c in / 
# Tue, 17 Jul 2018 11:42:34 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 12:03:10 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 12:03:10 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 12:03:11 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 12:03:12 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 12:03:12 GMT
ENV JAVA_HOME=/docker-java-home
# Thu, 23 Aug 2018 12:06:51 GMT
ENV JAVA_VERSION=11-ea+27
# Thu, 23 Aug 2018 12:06:51 GMT
ENV JAVA_DEBIAN_VERSION=11~27-1
# Thu, 23 Aug 2018 12:07:34 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 23 Aug 2018 12:07:34 GMT
CMD ["jshell"]
# Thu, 23 Aug 2018 15:11:35 GMT
ARG MAVEN_VERSION=3.5.4
# Thu, 23 Aug 2018 15:11:35 GMT
ARG USER_HOME_DIR=/root
# Thu, 23 Aug 2018 15:11:36 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Thu, 23 Aug 2018 15:11:36 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Thu, 23 Aug 2018 15:11:43 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN apt-get update &&     apt-get install -y       curl procps   && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 15:11:44 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN ln -s /etc/java-11-openjdk /usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)/conf
# Thu, 23 Aug 2018 15:11:54 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Thu, 23 Aug 2018 15:11:54 GMT
ENV MAVEN_HOME=/usr/share/maven
# Thu, 23 Aug 2018 15:11:54 GMT
ENV MAVEN_CONFIG=/root/.m2
# Thu, 23 Aug 2018 15:11:54 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Thu, 23 Aug 2018 15:11:55 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Thu, 23 Aug 2018 15:11:55 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Thu, 23 Aug 2018 15:11:55 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:1a7175b896da3e09b9a3ca6e3eb08f48c4a4243431b90adbec26e8baa7abec49`  
		Last Modified: Tue, 17 Jul 2018 11:45:48 GMT  
		Size: 25.1 MB (25130390 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aae7fd283a35bc996c3e40072f47e06f5a1863d130778afd8486985973fe079c`  
		Last Modified: Tue, 17 Jul 2018 12:10:30 GMT  
		Size: 470.9 KB (470909 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6b36a405f4357de759ca613cac9db408120a959b381a08b4c3ca780fe0e66965`  
		Last Modified: Tue, 17 Jul 2018 12:10:29 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13be106628117d44b0baab4035a3607a1dcbe5ece4061889f3546aec4b6304a7`  
		Last Modified: Tue, 17 Jul 2018 12:10:29 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f4838c7d4b43ec0153153e66b8f709af0f84c4e13aec68018549b74e7ff2140`  
		Last Modified: Thu, 23 Aug 2018 12:16:45 GMT  
		Size: 260.3 MB (260318268 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2cc3ce838604a4c10fb2c079b07f28fa92ea5ee5b8a60c9edd182e5e0034b3b5`  
		Last Modified: Thu, 23 Aug 2018 15:13:02 GMT  
		Size: 2.1 MB (2131246 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa41773bd71a0853997ecff3ebd1bc5672379c61ee59ee06425c213b18dcae3e`  
		Last Modified: Thu, 23 Aug 2018 15:13:01 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:364d495894d07d98550582de31659459eee2124d830baa00f825db273fa49b52`  
		Last Modified: Thu, 23 Aug 2018 15:13:09 GMT  
		Size: 9.0 MB (8989224 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e9849130c1aba257e972356ced3fff7d3a97d3f61195a07362f6e8a98e392feb`  
		Last Modified: Thu, 23 Aug 2018 15:13:01 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02a36bb23f68f91924ef10679a8df050a9e8c6cc838636c5d15c1f93d9289bf7`  
		Last Modified: Thu, 23 Aug 2018 15:13:00 GMT  
		Size: 360.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
