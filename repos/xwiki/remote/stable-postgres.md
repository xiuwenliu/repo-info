## `xwiki:stable-postgres`

```console
$ docker pull xwiki@sha256:01b688a4a90f8e889c14b0ef7d4f7b8a14e91f61fba1d1555e9522c0a5541c35
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8

### `xwiki:stable-postgres` - linux; amd64

```console
$ docker pull xwiki@sha256:c98ecee230fb5df5d9667559a9ff600c5c1ada1648e963ae6152bd05e97a8deb
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **592.6 MB (592646589 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ad385bafe1abd4036ceb14d868c5fc346a169164ec4fbd48d658445c8b75e7fa`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["xwiki"]`

```dockerfile
# Tue, 17 Jul 2018 00:27:24 GMT
ADD file:370028dca6e8ca9ed228549d52231cf8139515cc3a14c00aaed75a60b679775f in / 
# Tue, 17 Jul 2018 00:27:24 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 03:12:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 03:13:02 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 06:19:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:19:33 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 06:19:34 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 06:19:34 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:19:35 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 14 Aug 2018 20:34:46 GMT
ENV JAVA_VERSION=8u181
# Tue, 14 Aug 2018 20:34:46 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Tue, 14 Aug 2018 20:34:46 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 14 Aug 2018 20:35:31 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 14 Aug 2018 20:35:34 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 14 Aug 2018 22:36:03 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Tue, 14 Aug 2018 22:36:03 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 22:36:04 GMT
RUN mkdir -p "$CATALINA_HOME"
# Tue, 14 Aug 2018 22:36:05 GMT
WORKDIR /usr/local/tomcat
# Tue, 14 Aug 2018 22:36:05 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Tue, 14 Aug 2018 22:36:05 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Tue, 14 Aug 2018 22:36:05 GMT
ENV OPENSSL_VERSION=1.1.0f-3+deb9u2
# Tue, 14 Aug 2018 22:36:06 GMT
RUN set -ex; 	currentVersion="$(dpkg-query --show --showformat '${Version}\n' openssl)"; 	if dpkg --compare-versions "$currentVersion" '<<' "$OPENSSL_VERSION"; then 		if ! grep -q stretch /etc/apt/sources.list; then 			{ 				echo 'deb http://deb.debian.org/debian stretch main'; 				echo 'deb http://security.debian.org stretch/updates main'; 				echo 'deb http://deb.debian.org/debian stretch-updates main'; 			} > /etc/apt/sources.list.d/stretch.list; 			{ 				echo 'Package: *'; 				echo 'Pin: release n=stretch*'; 				echo 'Pin-Priority: -10'; 				echo; 				echo 'Package: openssl libssl*'; 				echo "Pin: version $OPENSSL_VERSION"; 				echo 'Pin-Priority: 990'; 			} > /etc/apt/preferences.d/stretch-openssl; 		fi; 		apt-get update; 		apt-get install -y --no-install-recommends openssl="$OPENSSL_VERSION"; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 14 Aug 2018 22:36:13 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 	&& rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 22:36:13 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 713DA88BE50911535FE716F5208B0AB1D63011C7 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 9BA44C2621385CB966EBA586F72C284D731FABEE A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Tue, 14 Aug 2018 22:40:34 GMT
ENV TOMCAT_MAJOR=8
# Thu, 23 Aug 2018 00:46:55 GMT
ENV TOMCAT_VERSION=8.5.33
# Thu, 23 Aug 2018 00:46:55 GMT
ENV TOMCAT_SHA512=bb6b3c27284697a835d1625bf63921b6147f98f3e1167b896d28b05bbcf7d6c71baa0aef35d8405ad41f897985dacf288f3a403b7d65bd726808637d97bfad11
# Thu, 23 Aug 2018 00:46:55 GMT
ENV TOMCAT_TGZ_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz 	https://www-us.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz 	https://www.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz 	https://archive.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz
# Thu, 23 Aug 2018 00:46:56 GMT
ENV TOMCAT_ASC_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz.asc 	https://www-us.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz.asc 	https://www.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz.asc 	https://archive.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz.asc
# Thu, 23 Aug 2018 00:47:45 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 		apt-get install -y --no-install-recommends gnupg dirmngr; 		export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 		apt-get install -y --no-install-recommends wget ca-certificates; 		success=; 	for url in $TOMCAT_TGZ_URLS; do 		if wget -O tomcat.tar.gz "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		echo "$TOMCAT_SHA512 *tomcat.tar.gz" | sha512sum -c -; 		success=; 	for url in $TOMCAT_ASC_URLS; do 		if wget -O tomcat.tar.gz.asc "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz; 	tar -xvf tomcat.tar.gz --strip-components=1; 	rm bin/*.bat; 	rm tomcat.tar.gz*; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		nativeBuildDir="$(mktemp -d)"; 	tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1; 	apt-get install -y --no-install-recommends 		dpkg-dev 		gcc 		libapr1-dev 		libssl-dev 		make 		"openjdk-${JAVA_VERSION%%[.~bu-]*}-jdk=$JAVA_DEBIAN_VERSION" 	; 	( 		export CATALINA_HOME="$PWD"; 		cd "$nativeBuildDir/native"; 		gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 		./configure 			--build="$gnuArch" 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes; 		make -j "$(nproc)"; 		make install; 	); 	rm -rf "$nativeBuildDir"; 	rm bin/tomcat-native.tar.gz; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 	rm -rf /var/lib/apt/lists/*; 		find ./bin/ -name '*.sh' -exec sed -ri 's|^#!/bin/sh$|#!/usr/bin/env bash|' '{}' +
# Thu, 23 Aug 2018 00:47:48 GMT
RUN set -e 	&& nativeLines="$(catalina.sh configtest 2>&1)" 	&& nativeLines="$(echo "$nativeLines" | grep 'Apache Tomcat Native')" 	&& nativeLines="$(echo "$nativeLines" | sort -u)" 	&& if ! echo "$nativeLines" | grep 'INFO: Loaded APR based Apache Tomcat Native library' >&2; then 		echo >&2 "$nativeLines"; 		exit 1; 	fi
# Thu, 23 Aug 2018 00:47:48 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 00:47:48 GMT
CMD ["catalina.sh" "run"]
# Thu, 30 Aug 2018 22:09:50 GMT
MAINTAINER Vincent Massol <vincent@massol.net>
# Thu, 30 Aug 2018 22:12:29 GMT
RUN apt-get update &&   apt-get --no-install-recommends -y install     curl     libreoffice     unzip     procps     libpostgresql-jdbc-java &&   rm -rf /var/lib/apt/lists/*
# Thu, 30 Aug 2018 22:14:23 GMT
ENV XWIKI_VERSION=10.7
# Thu, 30 Aug 2018 22:14:23 GMT
ENV XWIKI_URL_PREFIX=http://maven.xwiki.org/releases/org/xwiki/platform/xwiki-platform-distribution-war/10.7
# Thu, 30 Aug 2018 22:14:23 GMT
ENV XWIKI_DOWNLOAD_SHA256=500965a5e074d6df2e07822db85e551e260c2cf59dfac47dfaeb44687aa4592c
# Thu, 30 Aug 2018 22:15:07 GMT
RUN rm -rf /usr/local/tomcat/webapps/* &&   mkdir -p /usr/local/tomcat/temp &&   mkdir -p /usr/local/xwiki/data &&   curl -fSL "${XWIKI_URL_PREFIX}/xwiki-platform-distribution-war-${XWIKI_VERSION}.war" -o xwiki.war &&   echo "$XWIKI_DOWNLOAD_SHA256 xwiki.war" | sha256sum -c - &&   unzip -d /usr/local/tomcat/webapps/ROOT xwiki.war &&   rm -f xwiki.war
# Thu, 30 Aug 2018 22:15:08 GMT
RUN cp /usr/share/java/postgresql-jdbc4.jar /usr/local/tomcat/webapps/ROOT/WEB-INF/lib/
# Thu, 30 Aug 2018 22:15:08 GMT
COPY file:d8e7562dd4a94d06d6d74beeabe967320ea6ad96741a14a4dbf93f7e6e89e47c in /usr/local/tomcat/bin/ 
# Thu, 30 Aug 2018 22:15:09 GMT
COPY file:7a0ce36c7348308f7754e7d70a4cad74b1c6a11e342ab82fe6e57f1bef38e533 in /usr/local/tomcat/webapps/ROOT/WEB-INF/hibernate.cfg.xml 
# Thu, 30 Aug 2018 22:15:10 GMT
RUN sed -i 's/<id>org.xwiki.platform:xwiki-platform-distribution-war/<id>org.xwiki.platform:xwiki-platform-distribution-docker/'   /usr/local/tomcat/webapps/ROOT/META-INF/extension.xed
# Thu, 30 Aug 2018 22:15:10 GMT
COPY file:5f5be420889bdee3bc9520aa2af7c24fe855aaf5aafcc84e301666b86aa545eb in /usr/local/bin/docker-entrypoint.sh 
# Thu, 30 Aug 2018 22:15:10 GMT
VOLUME [/usr/local/xwiki]
# Thu, 30 Aug 2018 22:15:11 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 30 Aug 2018 22:15:11 GMT
CMD ["xwiki"]
```

-	Layers:
	-	`sha256:55cbf04beb7001d222c71bfdeae780bda19d5cb37b8dbd65ff0d3e6a0b9b74e6`  
		Last Modified: Tue, 17 Jul 2018 00:42:31 GMT  
		Size: 45.3 MB (45310044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1607093a898cc241de8712e4361dcd907898fff35b945adca42db3963f3827b3`  
		Last Modified: Tue, 17 Jul 2018 03:53:34 GMT  
		Size: 10.7 MB (10740168 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a8ea045c9261c180a34df19cfc9bb3c3f28f29b279bf964ee801536e8244f2f`  
		Last Modified: Tue, 17 Jul 2018 03:53:32 GMT  
		Size: 4.3 MB (4336107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1290813abd9d0a07ce709b4e491f4194f2b854295d93bdc068b7a576756fb515`  
		Last Modified: Tue, 17 Jul 2018 07:03:58 GMT  
		Size: 852.9 KB (852875 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6b982ad6d7f57b4a8a4052561dc7b0377bd8d4028bce8a93a4d31e60b79329`  
		Last Modified: Tue, 17 Jul 2018 07:03:58 GMT  
		Size: 246.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:abb029e68402beca7edc4627d5034aa72b37c74d8af9badb3284a69f17b91bb6`  
		Last Modified: Tue, 17 Jul 2018 07:03:57 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d068d0a738e5053cbca5643bc07bc278f76d3769cd69b8afda717c695c210f18`  
		Last Modified: Tue, 14 Aug 2018 20:46:59 GMT  
		Size: 122.1 MB (122120099 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42ee47bb0c52e5210fb8b964b20a471bc9591949cc7c6c45d14d4679eae2f2ed`  
		Last Modified: Tue, 14 Aug 2018 20:46:23 GMT  
		Size: 246.7 KB (246699 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae9c861aed252f048e32383d4f54fe14a59facff54504b421ee7818543a43bd6`  
		Last Modified: Tue, 14 Aug 2018 22:51:38 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60bba9d0dc8d1f5a1a7c972a86427b45f4e62736531f7534d2c002aa0a01c0c4`  
		Last Modified: Tue, 14 Aug 2018 22:51:39 GMT  
		Size: 528.4 KB (528408 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:091c11d70257d1ca60c8094bd2e17ba58bfe579bfb1d561d9a5e202197bb8de3`  
		Last Modified: Thu, 23 Aug 2018 01:02:58 GMT  
		Size: 10.6 MB (10592880 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:869034383fc79000c9525311dc2c6fe6ce2b5700bc18afedb00ce39f96f753e4`  
		Last Modified: Thu, 23 Aug 2018 01:02:56 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f4938ef36237c446bbc89757450414328077684dd25259ae8bb1b8ba1e34490`  
		Last Modified: Thu, 30 Aug 2018 22:16:43 GMT  
		Size: 161.0 MB (161029079 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8254131195cb9cc042846b1d53fe132e97df3a38de0cca9e1ec4b0a15229817f`  
		Last Modified: Thu, 30 Aug 2018 22:17:54 GMT  
		Size: 236.3 MB (236261028 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f4991801a67bbd03c2f74f25f3b2cb9abb82984453bf7265a24cc309fce5be56`  
		Last Modified: Thu, 30 Aug 2018 22:17:30 GMT  
		Size: 618.9 KB (618877 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62c8fdf657b844297996cab8fef4b40539a1a6a274c5e0fea517dc3c6c778067`  
		Last Modified: Thu, 30 Aug 2018 22:17:30 GMT  
		Size: 1.1 KB (1147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c2da5e4d254640c4656b8515b293ae720c97087abd9ca469bbbadbe5c716b0f5`  
		Last Modified: Thu, 30 Aug 2018 22:17:30 GMT  
		Size: 2.4 KB (2421 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2e37961c3bf3dbe6358b2dd9be2c49fc0d99a366b4a54f5fa50a0154d9248742`  
		Last Modified: Thu, 30 Aug 2018 22:17:31 GMT  
		Size: 3.7 KB (3723 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6ba531cefeb13698b02a731898aa63487d5625771d43335c49aa3f33c7abf93f`  
		Last Modified: Thu, 30 Aug 2018 22:17:30 GMT  
		Size: 2.4 KB (2377 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `xwiki:stable-postgres` - linux; arm64 variant v8

```console
$ docker pull xwiki@sha256:c8cd1ba51921df01843ea02661cae1f75820762316356a5cf65249558811eb4c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **572.6 MB (572648205 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a9b6a0ca342f9c8ebb99ab7bf1881437731d21d6f930d03c6f7e7a14313541cc`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["xwiki"]`

```dockerfile
# Tue, 17 Jul 2018 08:47:22 GMT
ADD file:5e1a1aab339b0b1e3047eeab5d0c6c74ad3f388d0407dc86f41e4a78b99c6fd8 in / 
# Tue, 17 Jul 2018 08:47:23 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 14:51:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 14:52:06 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 20:24:53 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 20:24:55 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 20:24:59 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 20:25:03 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 20:25:04 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 15 Aug 2018 09:27:47 GMT
ENV JAVA_VERSION=8u181
# Wed, 15 Aug 2018 09:27:48 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 15 Aug 2018 09:27:49 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 15 Aug 2018 09:32:01 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 15 Aug 2018 09:32:06 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 15 Aug 2018 12:33:43 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Wed, 15 Aug 2018 12:33:44 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 15 Aug 2018 12:33:46 GMT
RUN mkdir -p "$CATALINA_HOME"
# Wed, 15 Aug 2018 12:33:47 GMT
WORKDIR /usr/local/tomcat
# Wed, 15 Aug 2018 12:33:47 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Wed, 15 Aug 2018 12:33:48 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Wed, 15 Aug 2018 12:33:49 GMT
ENV OPENSSL_VERSION=1.1.0f-3+deb9u2
# Wed, 15 Aug 2018 12:33:51 GMT
RUN set -ex; 	currentVersion="$(dpkg-query --show --showformat '${Version}\n' openssl)"; 	if dpkg --compare-versions "$currentVersion" '<<' "$OPENSSL_VERSION"; then 		if ! grep -q stretch /etc/apt/sources.list; then 			{ 				echo 'deb http://deb.debian.org/debian stretch main'; 				echo 'deb http://security.debian.org stretch/updates main'; 				echo 'deb http://deb.debian.org/debian stretch-updates main'; 			} > /etc/apt/sources.list.d/stretch.list; 			{ 				echo 'Package: *'; 				echo 'Pin: release n=stretch*'; 				echo 'Pin-Priority: -10'; 				echo; 				echo 'Package: openssl libssl*'; 				echo "Pin: version $OPENSSL_VERSION"; 				echo 'Pin-Priority: 990'; 			} > /etc/apt/preferences.d/stretch-openssl; 		fi; 		apt-get update; 		apt-get install -y --no-install-recommends openssl="$OPENSSL_VERSION"; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 15 Aug 2018 12:34:03 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 	&& rm -rf /var/lib/apt/lists/*
# Wed, 15 Aug 2018 12:34:15 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 713DA88BE50911535FE716F5208B0AB1D63011C7 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 9BA44C2621385CB966EBA586F72C284D731FABEE A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Wed, 15 Aug 2018 12:47:56 GMT
ENV TOMCAT_MAJOR=8
# Thu, 23 Aug 2018 16:19:25 GMT
ENV TOMCAT_VERSION=8.5.33
# Thu, 23 Aug 2018 16:19:26 GMT
ENV TOMCAT_SHA512=bb6b3c27284697a835d1625bf63921b6147f98f3e1167b896d28b05bbcf7d6c71baa0aef35d8405ad41f897985dacf288f3a403b7d65bd726808637d97bfad11
# Thu, 23 Aug 2018 16:19:26 GMT
ENV TOMCAT_TGZ_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz 	https://www-us.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz 	https://www.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz 	https://archive.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz
# Thu, 23 Aug 2018 16:19:27 GMT
ENV TOMCAT_ASC_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz.asc 	https://www-us.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz.asc 	https://www.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz.asc 	https://archive.apache.org/dist/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz.asc
# Thu, 23 Aug 2018 16:21:04 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 		apt-get install -y --no-install-recommends gnupg dirmngr; 		export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 		apt-get install -y --no-install-recommends wget ca-certificates; 		success=; 	for url in $TOMCAT_TGZ_URLS; do 		if wget -O tomcat.tar.gz "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		echo "$TOMCAT_SHA512 *tomcat.tar.gz" | sha512sum -c -; 		success=; 	for url in $TOMCAT_ASC_URLS; do 		if wget -O tomcat.tar.gz.asc "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz; 	tar -xvf tomcat.tar.gz --strip-components=1; 	rm bin/*.bat; 	rm tomcat.tar.gz*; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		nativeBuildDir="$(mktemp -d)"; 	tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1; 	apt-get install -y --no-install-recommends 		dpkg-dev 		gcc 		libapr1-dev 		libssl-dev 		make 		"openjdk-${JAVA_VERSION%%[.~bu-]*}-jdk=$JAVA_DEBIAN_VERSION" 	; 	( 		export CATALINA_HOME="$PWD"; 		cd "$nativeBuildDir/native"; 		gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 		./configure 			--build="$gnuArch" 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes; 		make -j "$(nproc)"; 		make install; 	); 	rm -rf "$nativeBuildDir"; 	rm bin/tomcat-native.tar.gz; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 	rm -rf /var/lib/apt/lists/*; 		find ./bin/ -name '*.sh' -exec sed -ri 's|^#!/bin/sh$|#!/usr/bin/env bash|' '{}' +
# Thu, 23 Aug 2018 16:21:10 GMT
RUN set -e 	&& nativeLines="$(catalina.sh configtest 2>&1)" 	&& nativeLines="$(echo "$nativeLines" | grep 'Apache Tomcat Native')" 	&& nativeLines="$(echo "$nativeLines" | sort -u)" 	&& if ! echo "$nativeLines" | grep 'INFO: Loaded APR based Apache Tomcat Native library' >&2; then 		echo >&2 "$nativeLines"; 		exit 1; 	fi
# Thu, 23 Aug 2018 16:21:10 GMT
EXPOSE 8080/tcp
# Thu, 23 Aug 2018 16:21:11 GMT
CMD ["catalina.sh" "run"]
# Thu, 23 Aug 2018 18:07:47 GMT
MAINTAINER Vincent Massol <vincent@massol.net>
# Thu, 23 Aug 2018 18:11:28 GMT
RUN apt-get update &&   apt-get --no-install-recommends -y install     curl     libreoffice     unzip     procps     libpostgresql-jdbc-java &&   rm -rf /var/lib/apt/lists/*
# Wed, 29 Aug 2018 09:38:23 GMT
ENV XWIKI_VERSION=10.7
# Wed, 29 Aug 2018 09:38:24 GMT
ENV XWIKI_URL_PREFIX=http://maven.xwiki.org/releases/org/xwiki/platform/xwiki-platform-distribution-war/10.7
# Wed, 29 Aug 2018 09:38:25 GMT
ENV XWIKI_DOWNLOAD_SHA256=500965a5e074d6df2e07822db85e551e260c2cf59dfac47dfaeb44687aa4592c
# Wed, 29 Aug 2018 09:41:55 GMT
RUN rm -rf /usr/local/tomcat/webapps/* &&   mkdir -p /usr/local/tomcat/temp &&   mkdir -p /usr/local/xwiki/data &&   curl -fSL "${XWIKI_URL_PREFIX}/xwiki-platform-distribution-war-${XWIKI_VERSION}.war" -o xwiki.war &&   echo "$XWIKI_DOWNLOAD_SHA256 xwiki.war" | sha256sum -c - &&   unzip -d /usr/local/tomcat/webapps/ROOT xwiki.war &&   rm -f xwiki.war
# Wed, 29 Aug 2018 09:42:04 GMT
RUN cp /usr/share/java/postgresql-jdbc4.jar /usr/local/tomcat/webapps/ROOT/WEB-INF/lib/
# Wed, 29 Aug 2018 09:42:05 GMT
COPY file:d8e7562dd4a94d06d6d74beeabe967320ea6ad96741a14a4dbf93f7e6e89e47c in /usr/local/tomcat/bin/ 
# Wed, 29 Aug 2018 09:42:26 GMT
COPY file:7a0ce36c7348308f7754e7d70a4cad74b1c6a11e342ab82fe6e57f1bef38e533 in /usr/local/tomcat/webapps/ROOT/WEB-INF/hibernate.cfg.xml 
# Wed, 29 Aug 2018 09:42:28 GMT
RUN sed -i 's/<id>org.xwiki.platform:xwiki-platform-distribution-war/<id>org.xwiki.platform:xwiki-platform-distribution-docker/'   /usr/local/tomcat/webapps/ROOT/META-INF/extension.xed
# Wed, 29 Aug 2018 09:42:48 GMT
COPY file:5f5be420889bdee3bc9520aa2af7c24fe855aaf5aafcc84e301666b86aa545eb in /usr/local/bin/docker-entrypoint.sh 
# Wed, 29 Aug 2018 09:42:49 GMT
VOLUME [/usr/local/xwiki]
# Wed, 29 Aug 2018 09:43:10 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 29 Aug 2018 09:43:11 GMT
CMD ["xwiki"]
```

-	Layers:
	-	`sha256:24e48664c69560cde9534aadde23364122f1feb02b5db0ab3776983a4788ea63`  
		Last Modified: Tue, 17 Jul 2018 08:56:03 GMT  
		Size: 43.1 MB (43123568 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbcf842c718cc953be45905967fc6a0114f55314ce412b80107e20d8b43fdcdb`  
		Last Modified: Tue, 17 Jul 2018 15:10:44 GMT  
		Size: 9.7 MB (9690273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:317d79a9c0a5c766d03c1c253fa09f645ed7321dc3a80e0ae33599958677cd1d`  
		Last Modified: Tue, 17 Jul 2018 15:10:41 GMT  
		Size: 4.1 MB (4088491 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f34353c71abcb0a3423640b466779e00b7da4d2d4ebcdd89f3611d4c936b14ef`  
		Last Modified: Tue, 17 Jul 2018 20:53:29 GMT  
		Size: 839.2 KB (839215 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11a58de95103410c7614c07fbfbd2339f5b6657abdb8d847198c246eb1d753e3`  
		Last Modified: Tue, 17 Jul 2018 20:53:30 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:523b8fda53cc2bfd5306eedc221a547f3dd09df4aa2eeb8b0a72da68eace3c68`  
		Last Modified: Tue, 17 Jul 2018 20:53:29 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cf4fd39dafb9ad45f57c89125992e8197ddf2b218db872801723f2f7f9c0d9e5`  
		Last Modified: Wed, 15 Aug 2018 09:42:17 GMT  
		Size: 112.7 MB (112749799 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df7e84d92bb0c762009e72f6bcebe6327697bba2477ece3bf08ad63e7b8dce4f`  
		Last Modified: Wed, 15 Aug 2018 09:41:41 GMT  
		Size: 246.7 KB (246667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:551345d277a191d95debd27b75bdbdb78648d06685944c72086801e3487f9442`  
		Last Modified: Wed, 15 Aug 2018 13:21:46 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:32bd54ef0d6ed3ddbb887253ddb5b5c19ded33aa90ea991722ec94e042daae24`  
		Last Modified: Wed, 15 Aug 2018 13:21:46 GMT  
		Size: 512.9 KB (512933 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3aa8a78965fad6f729ab09ccfa615ea8ac70e7344db699d4d37e063f962884f1`  
		Last Modified: Thu, 23 Aug 2018 17:34:56 GMT  
		Size: 10.6 MB (10599321 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e796164c542112444c7f9b9d82c983d8fbfd17333a5ae714365928c15d2c7aa8`  
		Last Modified: Thu, 23 Aug 2018 17:34:53 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05f3219a30e8b203aea7be28cfcd616e6eb32a1f2732b545d50e11edde95f3a1`  
		Last Modified: Thu, 23 Aug 2018 18:22:38 GMT  
		Size: 153.9 MB (153907732 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b5fe0b6ad20a4fd38f663a9f0d8d7b8136f2fdcce7f0c0ca5af548bb18828dd`  
		Last Modified: Wed, 29 Aug 2018 09:44:43 GMT  
		Size: 236.3 MB (236260983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a4075cd594139c9965c2a4634411572051c15ff316d80908a6cd3bdb3697931d`  
		Last Modified: Wed, 29 Aug 2018 09:44:05 GMT  
		Size: 618.9 KB (618880 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3096d6c897cac1932d433b7cc3bfb2da3637cd69a17971e24fffd84521a870b9`  
		Last Modified: Wed, 29 Aug 2018 09:44:04 GMT  
		Size: 1.2 KB (1151 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b566ab8909126e6c394e9d0c01d53f76c70a5b59a7dbb231f12aa96b6b95b53e`  
		Last Modified: Wed, 29 Aug 2018 09:44:04 GMT  
		Size: 2.4 KB (2428 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b186a3e9d6a5722b6eba3b88521284d7caf0ef4adb4ab5ad0804739148384c43`  
		Last Modified: Wed, 29 Aug 2018 09:44:04 GMT  
		Size: 3.7 KB (3726 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f52f3db8c2cbb12c06aa8dbc33e087be19800e4379c1c48d12496a06a1f16aa`  
		Last Modified: Wed, 29 Aug 2018 09:44:05 GMT  
		Size: 2.4 KB (2381 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
