## `gradle:jre10-slim`

```console
$ docker pull gradle@sha256:6e25857c32316910d0789e47386e0b4a2935514dd722b2d2b751906ffb1a944b
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

### `gradle:jre10-slim` - linux; amd64

```console
$ docker pull gradle@sha256:d7767302e52f105dc1e2e5ee4b7fd782962efdd3d3c16f7280c1b08240878238
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **183.7 MB (183698854 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:22f677bcc355ec97b512715618e87bd4603118c1a753fb8e60a348073dbbfaeb`
-	Default Command: `["gradle"]`

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
# Tue, 17 Jul 2018 06:14:14 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:14:14 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 21 Jul 2018 07:49:52 GMT
ENV JAVA_VERSION=10.0.2+13
# Sat, 21 Jul 2018 07:49:52 GMT
ENV JAVA_DEBIAN_VERSION=10.0.2+13-1
# Sat, 21 Jul 2018 07:52:29 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 29 Aug 2018 15:40:33 GMT
CMD ["gradle"]
# Wed, 29 Aug 2018 15:40:33 GMT
ENV GRADLE_HOME=/opt/gradle
# Wed, 29 Aug 2018 15:40:33 GMT
ENV GRADLE_VERSION=4.10
# Wed, 29 Aug 2018 15:40:45 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Wed, 29 Aug 2018 15:40:45 GMT
ARG GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
# Wed, 29 Aug 2018 15:40:51 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Wed, 29 Aug 2018 15:40:52 GMT
USER [gradle]
# Wed, 29 Aug 2018 15:40:52 GMT
VOLUME [/home/gradle/.gradle]
# Wed, 29 Aug 2018 15:40:52 GMT
WORKDIR /home/gradle
# Wed, 29 Aug 2018 15:41:01 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:6aab55a95cbe8505bad8207b291a71574247d047b00b7b0256d27cd342623b79`  
		Last Modified: Tue, 17 Jul 2018 06:45:47 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:758cbdfbf3382630dd9093b6418a2042878ccec1596d1fe8cbddffb0e5075454`  
		Last Modified: Sat, 21 Jul 2018 08:20:38 GMT  
		Size: 78.1 MB (78084541 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a4669ceff5b25daa9d9e9dc36cb06b2292aa43079a33aa3575eccbcbf87c9b66`  
		Last Modified: Wed, 29 Aug 2018 15:50:06 GMT  
		Size: 611.2 KB (611196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f9156870a036df1ed56b9411324a89795813369bce27c9d7cfba45da4484c8e`  
		Last Modified: Wed, 29 Aug 2018 15:50:16 GMT  
		Size: 78.4 MB (78388758 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec7809e0477ca9bd4991f64426b7adbd50716834b0c7b06dc1cc238e494d4a02`  
		Last Modified: Wed, 29 Aug 2018 15:50:03 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre10-slim` - linux; arm variant v5

```console
$ docker pull gradle@sha256:54e4835719318df5fbac0b714d1d7d1f510498a865abf7f939bafeee3a32c569
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **166.6 MB (166586242 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:09ffa155f7df23dadb9e4626c03d5d6d503e80691cb061e0ae08271184b95db2`
-	Default Command: `["gradle"]`

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
# Tue, 17 Jul 2018 09:16:38 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 09:16:38 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 21 Jul 2018 11:01:26 GMT
ENV JAVA_VERSION=10.0.2+13
# Sat, 21 Jul 2018 11:01:26 GMT
ENV JAVA_DEBIAN_VERSION=10.0.2+13-1
# Sat, 21 Jul 2018 11:04:37 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 21 Jul 2018 15:06:11 GMT
CMD ["gradle"]
# Sat, 21 Jul 2018 15:06:11 GMT
ENV GRADLE_HOME=/opt/gradle
# Tue, 28 Aug 2018 08:54:43 GMT
ENV GRADLE_VERSION=4.10
# Tue, 28 Aug 2018 08:54:52 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Tue, 28 Aug 2018 08:54:52 GMT
ARG GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
# Tue, 28 Aug 2018 08:54:58 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Tue, 28 Aug 2018 08:54:59 GMT
USER [gradle]
# Tue, 28 Aug 2018 08:54:59 GMT
VOLUME [/home/gradle/.gradle]
# Tue, 28 Aug 2018 08:54:59 GMT
WORKDIR /home/gradle
# Tue, 28 Aug 2018 08:55:07 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:fc7ade75d811335a8b747fc901bd34343e48e667e2625f9203c81b8c1b492afb`  
		Last Modified: Tue, 17 Jul 2018 09:24:51 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:54c208bb170ee11a81d7fb3c84c068d882aa305937a1d72abc20100d71d12034`  
		Last Modified: Sat, 21 Jul 2018 11:27:51 GMT  
		Size: 63.1 MB (63058098 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adba18cd768ae2dd50238c0f2625a19b7ac5e87ed41a19fac58e7cbf3f97773e`  
		Last Modified: Tue, 28 Aug 2018 09:06:22 GMT  
		Size: 598.9 KB (598851 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b2eff6c70b6692208aa3d5f6b5b216ae96ee00230bcf4b43735786c917916ce`  
		Last Modified: Tue, 28 Aug 2018 09:06:33 GMT  
		Size: 78.4 MB (78388850 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b62d5a986029b91c3576935cc8182511de6c04a4d339033c053182d662254ca`  
		Last Modified: Tue, 28 Aug 2018 09:06:22 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre10-slim` - linux; arm variant v7

```console
$ docker pull gradle@sha256:5d5779ddfe9f083679791c918a3105ce64885b165a27dd26e34fbc0e3a4c92c0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **166.4 MB (166370940 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:28d5a187704613bcae0fcd936fb1ec62b374d08259ade7c7c44728ac125305a1`
-	Default Command: `["gradle"]`

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
# Tue, 17 Jul 2018 12:37:47 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 12:37:47 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 21 Jul 2018 12:22:48 GMT
ENV JAVA_VERSION=10.0.2+13
# Sat, 21 Jul 2018 12:22:49 GMT
ENV JAVA_DEBIAN_VERSION=10.0.2+13-1
# Sat, 21 Jul 2018 12:25:30 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 21 Jul 2018 13:41:38 GMT
CMD ["gradle"]
# Sat, 21 Jul 2018 13:41:38 GMT
ENV GRADLE_HOME=/opt/gradle
# Tue, 28 Aug 2018 12:07:29 GMT
ENV GRADLE_VERSION=4.10
# Tue, 28 Aug 2018 12:07:40 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Tue, 28 Aug 2018 12:07:41 GMT
ARG GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
# Tue, 28 Aug 2018 12:07:51 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Tue, 28 Aug 2018 12:07:53 GMT
USER [gradle]
# Tue, 28 Aug 2018 12:07:54 GMT
VOLUME [/home/gradle/.gradle]
# Tue, 28 Aug 2018 12:07:54 GMT
WORKDIR /home/gradle
# Tue, 28 Aug 2018 12:07:57 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:e3ed576d8b5e79e9f11a620b7f8ba0faa366e3fa9dbf558f0c98439c6eefb3e0`  
		Last Modified: Tue, 17 Jul 2018 12:59:55 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81f0af3cc0b96496ae587de0fb58f6fddc76e60ea2ad75923278ca6685be20cf`  
		Last Modified: Sat, 21 Jul 2018 12:54:17 GMT  
		Size: 64.9 MB (64910670 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4d4000c553cb06279d04cce042e7bc81fe5752d0e094d7035e5d15f702f12996`  
		Last Modified: Tue, 28 Aug 2018 12:18:56 GMT  
		Size: 580.0 KB (579973 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7c66a48968a8c3f09acfaa708fd6a12a139db52ce6a01d999ff1f1fd83322886`  
		Last Modified: Tue, 28 Aug 2018 12:19:06 GMT  
		Size: 78.4 MB (78388877 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:97dee8754dda6a04dd76d0c24e95dc945f38ec01f8d2bdaf797791c6c45275ef`  
		Last Modified: Tue, 28 Aug 2018 12:18:55 GMT  
		Size: 233.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre10-slim` - linux; arm64 variant v8

```console
$ docker pull gradle@sha256:5a4c7f9d28b35e220fb7932abd98a1639f855434ee6ed6201f8325cd753106a3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **170.1 MB (170072160 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:961fb46f498f7a6dfe51f0bea02897d536f183242c2614be3d4904c7cf25d05f`
-	Default Command: `["gradle"]`

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
# Tue, 17 Jul 2018 10:06:38 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 10:06:39 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 21 Jul 2018 10:29:12 GMT
ENV JAVA_VERSION=10.0.2+13
# Sat, 21 Jul 2018 10:29:13 GMT
ENV JAVA_DEBIAN_VERSION=10.0.2+13-1
# Sat, 21 Jul 2018 10:42:47 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 21 Jul 2018 16:05:10 GMT
CMD ["gradle"]
# Sat, 21 Jul 2018 16:05:11 GMT
ENV GRADLE_HOME=/opt/gradle
# Tue, 28 Aug 2018 09:00:16 GMT
ENV GRADLE_VERSION=4.10
# Tue, 28 Aug 2018 09:00:28 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Tue, 28 Aug 2018 09:00:38 GMT
ARG GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
# Tue, 28 Aug 2018 09:00:48 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Tue, 28 Aug 2018 09:01:00 GMT
USER [gradle]
# Tue, 28 Aug 2018 09:01:01 GMT
VOLUME [/home/gradle/.gradle]
# Tue, 28 Aug 2018 09:01:02 GMT
WORKDIR /home/gradle
# Tue, 28 Aug 2018 09:01:07 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:9b01739fd7fc001c331d8e1198f0fbba5b85522f69feaf74321f78180073301d`  
		Last Modified: Tue, 17 Jul 2018 10:31:34 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ca51bd96f56212a4cdc4c1d7a478ed678d689ea2b5f44977555315dd8644dc6`  
		Last Modified: Sat, 21 Jul 2018 11:18:58 GMT  
		Size: 67.2 MB (67175327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2be96c394d7ef7bf42e2ec68f0662acffe736b7b3c5a033e998518c6c216de3a`  
		Last Modified: Tue, 28 Aug 2018 09:35:51 GMT  
		Size: 593.7 KB (593714 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6ffc8a4dc45bac8e8a266dd11c3e922d3b2ca189b811e25c05c3fa4b3766be4`  
		Last Modified: Tue, 28 Aug 2018 09:36:04 GMT  
		Size: 78.4 MB (78388790 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab0425caceeba734b4324744aaa22e327bc1936e1259447dc6dbc26f5e82f3d6`  
		Last Modified: Tue, 28 Aug 2018 09:35:51 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre10-slim` - linux; 386

```console
$ docker pull gradle@sha256:e56f980a9e8d9dc941eb63719def65f17916b0e78400b51ae711958c24ac5490
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **188.8 MB (188771822 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3d9e41e142cc1221260a7bd1185e0dad37cefc7f6d8506b10d7b70f600fa8929`
-	Default Command: `["gradle"]`

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
# Tue, 17 Jul 2018 11:25:32 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 11:25:33 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 21 Jul 2018 11:52:51 GMT
ENV JAVA_VERSION=10.0.2+13
# Sat, 21 Jul 2018 11:52:51 GMT
ENV JAVA_DEBIAN_VERSION=10.0.2+13-1
# Sat, 21 Jul 2018 11:56:23 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Fri, 31 Aug 2018 19:36:41 GMT
CMD ["gradle"]
# Fri, 31 Aug 2018 19:36:41 GMT
ENV GRADLE_HOME=/opt/gradle
# Fri, 31 Aug 2018 19:36:42 GMT
ENV GRADLE_VERSION=4.10
# Fri, 31 Aug 2018 19:36:49 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Fri, 31 Aug 2018 19:36:50 GMT
ARG GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
# Fri, 31 Aug 2018 19:36:55 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Fri, 31 Aug 2018 19:36:55 GMT
USER [gradle]
# Fri, 31 Aug 2018 19:36:55 GMT
VOLUME [/home/gradle/.gradle]
# Fri, 31 Aug 2018 19:36:56 GMT
WORKDIR /home/gradle
# Fri, 31 Aug 2018 19:36:58 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:e8c87cc8b7a196c1115781e18b928f3a64611eb3b77eff6bd62a2084d3cc5a61`  
		Last Modified: Tue, 17 Jul 2018 11:49:26 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5371b729bfacca71a81607c107cb5bceb596ab46c237c1f9051a9b54f3eb31f4`  
		Last Modified: Sat, 21 Jul 2018 12:23:21 GMT  
		Size: 82.4 MB (82438383 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c2482ff6ada252a1fbf5c591b77562e6ef10a8afd5cbe15fd3958d5d6d40702`  
		Last Modified: Fri, 31 Aug 2018 19:43:14 GMT  
		Size: 628.0 KB (627976 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9ffcae3e12ad70621e11d32041a938474211126474f31fc6dbbcb037b19093fc`  
		Last Modified: Fri, 31 Aug 2018 19:43:25 GMT  
		Size: 78.4 MB (78388732 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c6f383eca761d4548f9ca0a914b897a505d99bfcbaed7f8a00aa934fbeb2541`  
		Last Modified: Fri, 31 Aug 2018 19:43:14 GMT  
		Size: 138.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre10-slim` - linux; ppc64le

```console
$ docker pull gradle@sha256:7b82e0e231eb612f11673d50c3bff08fc8109b163b89521368e4316a2309e80a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **175.6 MB (175559626 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:56d8937b0413714afcd409da0e413dd6fa7867f14f741acfcfb950c74e357518`
-	Default Command: `["gradle"]`

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
# Tue, 17 Jul 2018 09:05:40 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 09:05:43 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 21 Jul 2018 09:11:51 GMT
ENV JAVA_VERSION=10.0.2+13
# Sat, 21 Jul 2018 09:11:52 GMT
ENV JAVA_DEBIAN_VERSION=10.0.2+13-1
# Sat, 21 Jul 2018 09:19:55 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 21 Jul 2018 12:08:36 GMT
CMD ["gradle"]
# Sat, 21 Jul 2018 12:08:36 GMT
ENV GRADLE_HOME=/opt/gradle
# Tue, 28 Aug 2018 08:34:00 GMT
ENV GRADLE_VERSION=4.10
# Tue, 28 Aug 2018 08:34:20 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Tue, 28 Aug 2018 08:34:24 GMT
ARG GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
# Tue, 28 Aug 2018 08:34:36 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Tue, 28 Aug 2018 08:34:49 GMT
USER [gradle]
# Tue, 28 Aug 2018 08:34:58 GMT
VOLUME [/home/gradle/.gradle]
# Tue, 28 Aug 2018 08:35:00 GMT
WORKDIR /home/gradle
# Tue, 28 Aug 2018 08:35:10 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:7bdeb42b4f85888ec77389f7da02b093a0b3c84dec414a590fd40f586afaf4ff`  
		Last Modified: Tue, 17 Jul 2018 09:51:57 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:168c4ff58c4e81a3030fac04f7fb3f951bf217395c748385a3b37e06ace41d30`  
		Last Modified: Sat, 21 Jul 2018 09:42:24 GMT  
		Size: 68.7 MB (68663290 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00c9d427ea8d06bd728b521a8bcf26023e6d24691f4c956b799f10bb583c2042`  
		Last Modified: Tue, 28 Aug 2018 08:47:52 GMT  
		Size: 628.4 KB (628377 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab0d762587fd994c0d656c920e86ae76118718e528facbaf5d24670a9877f1f9`  
		Last Modified: Tue, 28 Aug 2018 08:48:02 GMT  
		Size: 78.4 MB (78388874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fabf0d2aa7e9077a75ba686f433247a17c1cd852c035df6d9b6412334a835b5c`  
		Last Modified: Tue, 28 Aug 2018 08:47:51 GMT  
		Size: 234.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre10-slim` - linux; s390x

```console
$ docker pull gradle@sha256:94a4e16edcedaee0adeb3b0fe5365b59e69e01eec1c7352aaae8ce53e47a168f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **172.0 MB (172043611 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9096c29a583d6dbf3e87c56f81861ae714abda13a69e4ae8f43bf4a546b6c62c`
-	Default Command: `["gradle"]`

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
# Tue, 17 Jul 2018 12:05:16 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 12:05:17 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 21 Jul 2018 12:12:45 GMT
ENV JAVA_VERSION=10.0.2+13
# Sat, 21 Jul 2018 12:12:46 GMT
ENV JAVA_DEBIAN_VERSION=10.0.2+13-1
# Sat, 21 Jul 2018 12:14:58 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 21 Jul 2018 13:53:13 GMT
CMD ["gradle"]
# Sat, 21 Jul 2018 13:53:13 GMT
ENV GRADLE_HOME=/opt/gradle
# Tue, 28 Aug 2018 11:51:46 GMT
ENV GRADLE_VERSION=4.10
# Tue, 28 Aug 2018 11:51:50 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Tue, 28 Aug 2018 11:51:50 GMT
ARG GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
# Tue, 28 Aug 2018 11:51:53 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Tue, 28 Aug 2018 11:51:53 GMT
USER [gradle]
# Tue, 28 Aug 2018 11:51:54 GMT
VOLUME [/home/gradle/.gradle]
# Tue, 28 Aug 2018 11:51:54 GMT
WORKDIR /home/gradle
# Tue, 28 Aug 2018 11:51:55 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=248cfd92104ce12c5431ddb8309cf713fe58de8e330c63176543320022f59f18
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:9036c33525890fd71c86b6384e69ece5f4ef4ffab9a39099589053c95738977a`  
		Last Modified: Tue, 17 Jul 2018 12:13:05 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ab14cd81259328f4fafa2aba52f33272950a78409ed6ef42388afd2b0685bf5`  
		Last Modified: Sat, 21 Jul 2018 12:25:22 GMT  
		Size: 67.4 MB (67441592 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c4e24cf036111d727a03924f7e46a6d65122d14e3c8761f8f85ce0a8126cc61`  
		Last Modified: Tue, 28 Aug 2018 12:01:53 GMT  
		Size: 611.4 KB (611386 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0fa122953deff08fd2c3d7eb385b476ad941aea69ece9643454b447333d7ccfc`  
		Last Modified: Tue, 28 Aug 2018 12:02:00 GMT  
		Size: 78.4 MB (78388759 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bd47a0f11240198a8a821a73abb3f1599e3bd8a40bc83f2bdd4b87917326bef`  
		Last Modified: Tue, 28 Aug 2018 12:01:53 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
