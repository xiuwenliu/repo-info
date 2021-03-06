## `known:latest`

```console
$ docker pull known@sha256:097cb1462cdaf31faa630e27f4fe7bd726423ba527331f3552ca97fb2d267966
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8

### `known:latest` - linux; amd64

```console
$ docker pull known@sha256:2de3fe7faafc07adbfdaa4d8e7e74d2c69aedd6e2c7bede3571e2a47551f2334
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **172.9 MB (172939958 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9283b2f09c35b33d8a3b64f35d11cbecc388c41cc30eaeee81f9462e11d5e8c4`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Tue, 17 Jul 2018 00:28:04 GMT
ADD file:919939fa022472751b717443eea9f1d7ab5c0723f1f3a6b776d3b83d22bde818 in / 
# Tue, 17 Jul 2018 00:28:04 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 04:49:37 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Tue, 17 Jul 2018 04:49:37 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 17 Jul 2018 04:50:16 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 17 Jul 2018 04:50:16 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 17 Jul 2018 04:50:17 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 17 Jul 2018 04:59:01 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data --disable-cgi
# Tue, 17 Jul 2018 04:59:01 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 04:59:01 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 04:59:02 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 17 Jul 2018 06:29:56 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Sat, 21 Jul 2018 10:12:01 GMT
ENV PHP_VERSION=5.6.37
# Sat, 21 Jul 2018 10:12:01 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.37.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.37.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 10:12:01 GMT
ENV PHP_SHA256=5000d82610f9134aaedef28854ec3591f68dedf26a17b8935727dac2843bd256 PHP_MD5=
# Sat, 21 Jul 2018 10:12:15 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Sat, 21 Jul 2018 10:12:16 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 10:15:36 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl1.0-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 10:15:47 GMT
COPY multi:af8a06a5cfc82b17b169c6d1e48630a516582fa7ce00d8e59e5a378e100d064a in /usr/local/bin/ 
# Sat, 21 Jul 2018 10:15:47 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 10:15:47 GMT
WORKDIR /var/www/html
# Sat, 21 Jul 2018 10:15:48 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = 9000'; 	} | tee php-fpm.d/zz-docker.conf
# Sat, 21 Jul 2018 10:15:48 GMT
EXPOSE 9000/tcp
# Sat, 21 Jul 2018 10:15:49 GMT
CMD ["php-fpm"]
# Mon, 06 Aug 2018 19:51:50 GMT
LABEL maintainer=hello@withknown.com
# Mon, 06 Aug 2018 19:55:32 GMT
RUN apt-get update  && apt-get install -y --no-install-recommends mysql-client  && savedAptMark="$(apt-mark showmanual)"  && apt-get install -y --no-install-recommends       libfreetype6-dev       libicu-dev       libjpeg-dev       libmcrypt-dev       libpng-dev       libxml2-dev  && docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr  && docker-php-ext-install exif gd intl mcrypt opcache pdo_mysql zip json xmlrpc  && apt-mark auto '.*' > /dev/null  && apt-mark manual $savedAptMark  && ldd "$(php -r 'echo ini_get("extension_dir");')"/*.so     | awk '/=>/ { print $3 }'     | sort -u     | xargs -r dpkg-query -S     | cut -d: -f1     | sort -u     | xargs -rt apt-mark manual  && apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false  && rm -rf /var/lib/apt/lists/*
# Mon, 06 Aug 2018 19:55:40 GMT
RUN {   echo 'opcache.memory_consumption=128';   echo 'opcache.interned_strings_buffer=8';   echo 'opcache.max_accelerated_files=4000';   echo 'opcache.revalidate_freq=60';   echo 'opcache.fast_shutdown=1';   echo 'opcache.enable_cli=1'; } > /usr/local/etc/php/conf.d/opcache-recommended.ini
# Mon, 06 Aug 2018 19:55:59 GMT
RUN pecl install APCu-4.0.11  && docker-php-ext-enable apcu
# Mon, 06 Aug 2018 19:55:59 GMT
ENV KNOWN_VERSION=0.9.9
# Mon, 06 Aug 2018 19:55:59 GMT
VOLUME [/var/www/html]
# Mon, 06 Aug 2018 19:56:19 GMT
RUN fetchDeps="     gnupg     dirmngr   "  && apt-get update  && apt-get install -y --no-install-recommends $fetchDeps  && curl -o known.tgz -fSL http://assets.withknown.com/releases/known-${KNOWN_VERSION}.tgz  && curl -o known.tgz.sig -fSL http://assets.withknown.com/releases/known-${KNOWN_VERSION}.tgz.sig  && export GNUPGHOME="$(mktemp -d)"  && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "53DE 5B99 2244 9132 8B92 7516 052D B5AC 742E 3B47"  && gpg --batch --verify known.tgz.sig known.tgz  && mkdir /usr/src/known  && tar -xf known.tgz -C /usr/src/known  && rm -r "$GNUPGHOME" known.tgz*  && apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps  && rm -rf /var/lib/apt/lists/*
# Mon, 06 Aug 2018 19:56:38 GMT
COPY file:6d2bbeccad440fd875b308488484f3081838a6ed7c7f5ec2ad4488f753cd87e0 in /entrypoint.sh 
# Mon, 06 Aug 2018 19:56:38 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Mon, 06 Aug 2018 19:56:39 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:be8881be8156e4068e611fe956aba2b9593ebd953be14fb7feea6d0659aa3abe`  
		Last Modified: Tue, 17 Jul 2018 00:44:17 GMT  
		Size: 22.5 MB (22485906 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:69a25f7e493029f541fc3c7ac66fdffdd5f8c4b9b33346031523d053177bb365`  
		Last Modified: Tue, 17 Jul 2018 06:59:33 GMT  
		Size: 227.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65632e89c5f4ef102bcd13b6e86baf954e0b902f688a46961d5ff0a36dddfebe`  
		Last Modified: Tue, 17 Jul 2018 07:00:01 GMT  
		Size: 67.4 MB (67428909 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cd75fa32da8fd946b82c0447feac1f3c24330594492e3be74a516b18437d5306`  
		Last Modified: Tue, 17 Jul 2018 06:59:32 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ade3ea27a52ca624acc71651cdbe59438d5c43e3d3b4a456325420ecbf5d5b8`  
		Last Modified: Sat, 21 Jul 2018 11:59:07 GMT  
		Size: 12.8 MB (12795930 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:844e237a75b781c20de0fecb21d9f46fae890becba7fe496a496848bd7a16d2b`  
		Last Modified: Sat, 21 Jul 2018 11:59:03 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1201c61a79490df053de12d701b8dd7674d9cbde2e7a4178b99ffcd45489c7b9`  
		Last Modified: Sat, 21 Jul 2018 11:59:10 GMT  
		Size: 23.0 MB (22986790 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9f10158fd326c278be422e494abef53f6293afde514442c00d2b942e32e6ed2`  
		Last Modified: Sat, 21 Jul 2018 11:59:03 GMT  
		Size: 2.2 KB (2183 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab5ba301cd675889ec67b3ab46a2d20f22d39a4bf98733b077f732a6845b0461`  
		Last Modified: Sat, 21 Jul 2018 11:59:04 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0245cfebffbf542c8eedebf47aee19b3d27ba699196244628dd22c931a3b9f47`  
		Last Modified: Sat, 21 Jul 2018 11:59:03 GMT  
		Size: 7.7 KB (7711 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb9f55fef649659d719cda0135d56ce0eb01549c33d2a34e8fc2d33e9c00d2a5`  
		Last Modified: Mon, 06 Aug 2018 19:57:26 GMT  
		Size: 24.1 MB (24060683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f0859c665c5d871502a815dd1cf7442d60a6db6482ac36dd8a5c8f77a9494e7f`  
		Last Modified: Mon, 06 Aug 2018 19:57:17 GMT  
		Size: 355.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5957f4136b0943e9839bd78ae3667351660c05a044645d836437fe1953b428cf`  
		Last Modified: Mon, 06 Aug 2018 19:57:18 GMT  
		Size: 445.2 KB (445238 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a447c5f067ba3e31d92d53df1321184f7553701578df8572e12aa9b8c0f7ad6`  
		Last Modified: Mon, 06 Aug 2018 19:57:24 GMT  
		Size: 22.7 MB (22723972 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:939b18d871fe94eabc850f60551897a5b5d0eeee9d541dd10233f6a20d195a5c`  
		Last Modified: Mon, 06 Aug 2018 19:57:17 GMT  
		Size: 1.2 KB (1243 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `known:latest` - linux; arm64 variant v8

```console
$ docker pull known@sha256:355785bc9d922c2fd6f4649a15eda8d1aeba75c352a4b5fb86f92a28dc8f3773
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **158.6 MB (158611861 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bc2639326185fd3f14966a8d6f91b41dcfd14a6cac6ed2541b09f8aa5b8104ff`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Tue, 17 Jul 2018 08:48:06 GMT
ADD file:b6ea996ffd5aa4dade8cb1d721c2716614c03110d98683aca206c7ab52fcb9e5 in / 
# Tue, 17 Jul 2018 08:48:07 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 16:03:10 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Tue, 17 Jul 2018 16:03:11 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 17 Jul 2018 16:04:26 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 17 Jul 2018 16:04:28 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 17 Jul 2018 16:04:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 17 Jul 2018 16:27:23 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data --disable-cgi
# Tue, 17 Jul 2018 16:27:24 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 16:27:25 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 16:27:26 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 17 Jul 2018 18:33:52 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Sat, 21 Jul 2018 14:45:52 GMT
ENV PHP_VERSION=5.6.37
# Sat, 21 Jul 2018 14:45:53 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.37.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.37.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 14:45:54 GMT
ENV PHP_SHA256=5000d82610f9134aaedef28854ec3591f68dedf26a17b8935727dac2843bd256 PHP_MD5=
# Sat, 21 Jul 2018 14:46:32 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Sat, 21 Jul 2018 14:46:34 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 14:54:18 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl1.0-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 14:54:30 GMT
COPY multi:af8a06a5cfc82b17b169c6d1e48630a516582fa7ce00d8e59e5a378e100d064a in /usr/local/bin/ 
# Sat, 21 Jul 2018 14:54:30 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 14:54:44 GMT
WORKDIR /var/www/html
# Sat, 21 Jul 2018 14:54:46 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = 9000'; 	} | tee php-fpm.d/zz-docker.conf
# Sat, 21 Jul 2018 14:54:59 GMT
EXPOSE 9000/tcp
# Sat, 21 Jul 2018 14:55:00 GMT
CMD ["php-fpm"]
# Tue, 07 Aug 2018 08:46:59 GMT
LABEL maintainer=hello@withknown.com
# Tue, 07 Aug 2018 08:51:56 GMT
RUN apt-get update  && apt-get install -y --no-install-recommends mysql-client  && savedAptMark="$(apt-mark showmanual)"  && apt-get install -y --no-install-recommends       libfreetype6-dev       libicu-dev       libjpeg-dev       libmcrypt-dev       libpng-dev       libxml2-dev  && docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr  && docker-php-ext-install exif gd intl mcrypt opcache pdo_mysql zip json xmlrpc  && apt-mark auto '.*' > /dev/null  && apt-mark manual $savedAptMark  && ldd "$(php -r 'echo ini_get("extension_dir");')"/*.so     | awk '/=>/ { print $3 }'     | sort -u     | xargs -r dpkg-query -S     | cut -d: -f1     | sort -u     | xargs -rt apt-mark manual  && apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false  && rm -rf /var/lib/apt/lists/*
# Tue, 07 Aug 2018 08:51:58 GMT
RUN {   echo 'opcache.memory_consumption=128';   echo 'opcache.interned_strings_buffer=8';   echo 'opcache.max_accelerated_files=4000';   echo 'opcache.revalidate_freq=60';   echo 'opcache.fast_shutdown=1';   echo 'opcache.enable_cli=1'; } > /usr/local/etc/php/conf.d/opcache-recommended.ini
# Tue, 07 Aug 2018 08:52:19 GMT
RUN pecl install APCu-4.0.11  && docker-php-ext-enable apcu
# Tue, 07 Aug 2018 08:52:20 GMT
ENV KNOWN_VERSION=0.9.9
# Tue, 07 Aug 2018 08:52:21 GMT
VOLUME [/var/www/html]
# Thu, 09 Aug 2018 08:52:43 GMT
RUN fetchDeps="     gnupg     dirmngr   "  && apt-get update  && apt-get install -y --no-install-recommends $fetchDeps  && curl -o known.tgz -fSL http://assets.withknown.com/releases/known-${KNOWN_VERSION}.tgz  && curl -o known.tgz.sig -fSL http://assets.withknown.com/releases/known-${KNOWN_VERSION}.tgz.sig  && export GNUPGHOME="$(mktemp -d)"  && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "53DE 5B99 2244 9132 8B92 7516 052D B5AC 742E 3B47"  && gpg --batch --verify known.tgz.sig known.tgz  && mkdir /usr/src/known  && tar -xf known.tgz -C /usr/src/known  && rm -r "$GNUPGHOME" known.tgz*  && apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps  && rm -rf /var/lib/apt/lists/*
# Thu, 09 Aug 2018 08:52:45 GMT
COPY file:6d2bbeccad440fd875b308488484f3081838a6ed7c7f5ec2ad4488f753cd87e0 in /entrypoint.sh 
# Thu, 09 Aug 2018 08:52:45 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 09 Aug 2018 08:53:02 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:74a932489409d8d15db14c8a4a811fb46c7386bb06ea678ff27084d5657eeaaf`  
		Last Modified: Tue, 17 Jul 2018 08:57:35 GMT  
		Size: 20.3 MB (20331647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:873bd0f2b0da24bb481d8491665955d3176f41a8c3262572051e6fbfc2075c14`  
		Last Modified: Tue, 17 Jul 2018 18:53:34 GMT  
		Size: 228.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89e8001003dbe417b7882e436548f10e9fc4bfbfc45d9c22416657a3ab0ce20e`  
		Last Modified: Tue, 17 Jul 2018 18:53:57 GMT  
		Size: 57.6 MB (57595585 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e276d47e823964f5d049fdc2f13115ee09bb8044a6355809621253a1c52d2adb`  
		Last Modified: Tue, 17 Jul 2018 18:53:34 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:489f950d02c5d8bf032151a3108126c62e91dd50c6d63b193c3e92e60ab210ed`  
		Last Modified: Sat, 21 Jul 2018 16:32:29 GMT  
		Size: 12.8 MB (12793938 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:79f737e3796a14035d82cddf7959b22a38740e6afb11fafce45896632487aa83`  
		Last Modified: Sat, 21 Jul 2018 16:32:24 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:96fb4e798b4ee69d5e16e97bd38caecc5c30daad2121e31ac8b2bc20b5739c91`  
		Last Modified: Sat, 21 Jul 2018 16:32:31 GMT  
		Size: 22.2 MB (22213932 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c12076c5f6f5867b956edfba8569323ff3b6228f3ff37150c74eb08c1a8eabb`  
		Last Modified: Sat, 21 Jul 2018 16:32:24 GMT  
		Size: 2.2 KB (2182 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e51f2618bbd36b2dbf11c7971eeb67dc41bf362b5eff51fed8e80f1b674e805e`  
		Last Modified: Sat, 21 Jul 2018 16:32:23 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bc568434c6dd08704db9bed896390e6170369f84e670574b44f1abdc770ee018`  
		Last Modified: Sat, 21 Jul 2018 16:32:23 GMT  
		Size: 7.7 KB (7707 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61c87d367314c177d9e7158a9b21e4cb0dde528f49302514aa8fe6b8eb146c74`  
		Last Modified: Thu, 09 Aug 2018 08:53:48 GMT  
		Size: 22.5 MB (22503730 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2889f665fe1bc770929e461f2df24655754ec64c8c37b548b9e8990ec556942b`  
		Last Modified: Thu, 09 Aug 2018 08:53:39 GMT  
		Size: 353.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:97f70a7bd04a3547a5216c80100257a66f1c5ae4c912ffbae90c6ac5e2cef796`  
		Last Modified: Thu, 09 Aug 2018 08:53:39 GMT  
		Size: 438.1 KB (438064 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bfa84d997353d4115e08de18421ebac4697a82a3c51b357363751110bac3f25b`  
		Last Modified: Thu, 09 Aug 2018 08:53:47 GMT  
		Size: 22.7 MB (22722438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6eb1478fed2a9a575a09046e759f7d68855e6e12abd39a3a920b604b6488f807`  
		Last Modified: Thu, 09 Aug 2018 08:53:39 GMT  
		Size: 1.2 KB (1243 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
