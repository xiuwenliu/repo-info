## `php:rc-apache`

```console
$ docker pull php@sha256:93c9983078a5b846402d08f40f688f9229449a708da4e16e884c819d8612d770
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `php:rc-apache` - linux; amd64

```console
$ docker pull php@sha256:a5fecd8ff3b33b89b5ac8017f96f82cccf843f55829889224164e59cd4fb8ea8
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **134.8 MB (134752755 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5da37e664990ab6ab70ded2543702bf752ab450961cf7dd96ae014d921ea5842`
-	Entrypoint: `["docker-php-entrypoint"]`
-	Default Command: `["apache2-foreground"]`

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
# Tue, 17 Jul 2018 04:55:09 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 04:55:10 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 17 Jul 2018 04:55:10 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 17 Jul 2018 04:55:11 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 17 Jul 2018 04:55:11 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 17 Jul 2018 04:55:12 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 17 Jul 2018 04:55:25 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 17 Jul 2018 04:55:25 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 17 Jul 2018 04:55:26 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2 --disable-cgi
# Tue, 17 Jul 2018 04:55:26 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 04:55:26 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 04:55:26 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Wed, 22 Aug 2018 23:29:46 GMT
ENV GPG_KEYS=CBAF69F173A0FEA4B537F470D66C9593118BCCB6 F38252826ACD957EF380D39F2F7956BC5DA04B5D
# Wed, 22 Aug 2018 23:29:46 GMT
ENV PHP_VERSION=7.3.0beta2
# Wed, 22 Aug 2018 23:29:46 GMT
ENV PHP_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz PHP_ASC_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz.asc
# Wed, 22 Aug 2018 23:29:46 GMT
ENV PHP_SHA256=28f040680ff517b6c3da403fd1048054de0e867246c47da36342f6a488661c70 PHP_MD5=
# Wed, 22 Aug 2018 23:29:59 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Wed, 22 Aug 2018 23:30:08 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Wed, 22 Aug 2018 23:33:09 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsodium-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	sed -e 's/stretch/buster/g' /etc/apt/sources.list > /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: -10'; 		echo; 		echo 'Package: libargon2*'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: 990'; 	} > /etc/apt/preferences.d/argon2-buster; 	apt-get update; 	apt-get install -y --no-install-recommends libargon2-dev; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-password-argon2 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Wed, 22 Aug 2018 23:33:17 GMT
COPY multi:c925dfb355ea16ba0238c8b6ca78d3cd7fe815932bf707b25bbf051070430157 in /usr/local/bin/ 
# Wed, 22 Aug 2018 23:33:18 GMT
RUN docker-php-ext-enable sodium
# Wed, 22 Aug 2018 23:33:18 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Wed, 22 Aug 2018 23:33:19 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Wed, 22 Aug 2018 23:33:19 GMT
WORKDIR /var/www/html
# Wed, 22 Aug 2018 23:33:38 GMT
EXPOSE 80/tcp
# Wed, 22 Aug 2018 23:33:38 GMT
CMD ["apache2-foreground"]
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
	-	`sha256:15bc7736db11de5eddd0f13bb1c28ebe5612a4fcf398c7c1077f446abbdfb935`  
		Last Modified: Tue, 17 Jul 2018 07:07:01 GMT  
		Size: 17.1 MB (17127402 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2c40cef4807e3464b2859ebb5e4ac179cfbc253a212ce725f3a5d27388f79fe`  
		Last Modified: Tue, 17 Jul 2018 07:06:54 GMT  
		Size: 1.2 KB (1241 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f3507e55e5eba49288cb3c8ff469e5a772b31fe8d0b5d2dae06faff4a4d34318`  
		Last Modified: Tue, 17 Jul 2018 07:06:54 GMT  
		Size: 428.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6006cdfa16b487a3a92269f59ecf33b936311fb9934fd4a5b7775b46933fdfe`  
		Last Modified: Tue, 17 Jul 2018 07:06:53 GMT  
		Size: 230.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3ed406e3c880fbafac0ae7ab1a889a46f9ef17e86e3efd898158a3241a0518b`  
		Last Modified: Tue, 17 Jul 2018 07:06:52 GMT  
		Size: 487.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:956b63cfc2b6542a3fa396f5c6b7e76390624a07df7015df7ef65a747231c3d4`  
		Last Modified: Thu, 23 Aug 2018 02:17:44 GMT  
		Size: 12.3 MB (12251633 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3772f16f69cd39d3bb13a5245db0f39df250383f182a95ae2548a59c45129506`  
		Last Modified: Thu, 23 Aug 2018 02:17:39 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:20b7c792f5f449d1821a2db787466e7ba1f3082d63c9d27d8e835bb74e5eba55`  
		Last Modified: Thu, 23 Aug 2018 02:17:45 GMT  
		Size: 15.5 MB (15452248 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f96296e01d18b76787317b75d4b0aaf7f52fa1da630d589293ec7ed2cdbc29f`  
		Last Modified: Thu, 23 Aug 2018 02:17:39 GMT  
		Size: 2.2 KB (2190 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60fdb18723f4a4e44416c96b2444ec030fd0d40578d1ee132920adb37769590a`  
		Last Modified: Thu, 23 Aug 2018 02:17:40 GMT  
		Size: 267.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a7d282ba663253e8ddaf9a94125b20d9abdae3b78e10735e385833d044e6fe78`  
		Last Modified: Thu, 23 Aug 2018 02:17:40 GMT  
		Size: 904.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `php:rc-apache` - linux; arm variant v5

```console
$ docker pull php@sha256:62c6cbec08684c0af4fe4b72c0200d6e8433204d8605d485e35f377f47162796
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **122.2 MB (122155053 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:86268e17ae032971a3bf596832779123f151b966a2488a9e14cb4b06e484605c`
-	Entrypoint: `["docker-php-entrypoint"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 17 Jul 2018 08:56:27 GMT
ADD file:60830ba735048c6cbecbc75b83364ad442e1e5ee691ef74dad4eb07f720f8919 in / 
# Tue, 17 Jul 2018 08:56:29 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 12:11:37 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Tue, 17 Jul 2018 12:11:37 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 17 Jul 2018 12:12:07 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 17 Jul 2018 12:12:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 17 Jul 2018 12:12:09 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 17 Jul 2018 12:16:32 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 12:16:32 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 17 Jul 2018 12:16:33 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 17 Jul 2018 12:16:33 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 17 Jul 2018 12:16:34 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 17 Jul 2018 12:16:35 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 17 Jul 2018 12:16:36 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 17 Jul 2018 12:16:36 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 17 Jul 2018 12:16:37 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2 --disable-cgi
# Tue, 17 Jul 2018 12:16:37 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 12:16:37 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 12:16:37 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 23 Aug 2018 08:52:55 GMT
ENV GPG_KEYS=CBAF69F173A0FEA4B537F470D66C9593118BCCB6 F38252826ACD957EF380D39F2F7956BC5DA04B5D
# Thu, 23 Aug 2018 08:52:55 GMT
ENV PHP_VERSION=7.3.0beta2
# Thu, 23 Aug 2018 08:52:55 GMT
ENV PHP_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz PHP_ASC_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz.asc
# Thu, 23 Aug 2018 08:52:56 GMT
ENV PHP_SHA256=28f040680ff517b6c3da403fd1048054de0e867246c47da36342f6a488661c70 PHP_MD5=
# Thu, 23 Aug 2018 08:53:09 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Thu, 23 Aug 2018 08:53:10 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Thu, 23 Aug 2018 08:56:07 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsodium-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	sed -e 's/stretch/buster/g' /etc/apt/sources.list > /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: -10'; 		echo; 		echo 'Package: libargon2*'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: 990'; 	} > /etc/apt/preferences.d/argon2-buster; 	apt-get update; 	apt-get install -y --no-install-recommends libargon2-dev; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-password-argon2 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Thu, 23 Aug 2018 08:56:08 GMT
COPY multi:c925dfb355ea16ba0238c8b6ca78d3cd7fe815932bf707b25bbf051070430157 in /usr/local/bin/ 
# Thu, 23 Aug 2018 08:56:09 GMT
RUN docker-php-ext-enable sodium
# Thu, 23 Aug 2018 08:56:10 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Thu, 23 Aug 2018 08:56:10 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Thu, 23 Aug 2018 08:56:10 GMT
WORKDIR /var/www/html
# Thu, 23 Aug 2018 08:56:10 GMT
EXPOSE 80/tcp
# Thu, 23 Aug 2018 08:56:11 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:235e2c34c6b727f2b00aae7eed907f84338b4002c487e0caaa123a50334c0810`  
		Last Modified: Tue, 17 Jul 2018 09:09:00 GMT  
		Size: 21.2 MB (21162647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cd628726115d1b85f5fa4da7cce482866282d8d413ca606ea4ceb6d5c78e4f4b`  
		Last Modified: Tue, 17 Jul 2018 14:10:16 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6d762076c20a075be84e128e3058c548c89794ff387f3398c1ffff670865359`  
		Last Modified: Tue, 17 Jul 2018 14:10:35 GMT  
		Size: 57.4 MB (57447364 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:285bc4dc2b6d84e706bd65098634e75f474fe61ef97464d1ef11e6fd51f5cda7`  
		Last Modified: Tue, 17 Jul 2018 14:10:16 GMT  
		Size: 212.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2fb9c15539d5a377f98f2a0f58ebb319c1c35ddc2e3f0441768a009d7ee5884c`  
		Last Modified: Tue, 17 Jul 2018 14:13:11 GMT  
		Size: 16.7 MB (16650925 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ffd19cc66fa8ebbc75a62e14647f88bbb78438490bbe70feb4963881f16257e6`  
		Last Modified: Tue, 17 Jul 2018 14:13:07 GMT  
		Size: 1.3 KB (1273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e786b3fdcaa4442d8c2ac91b6c5e811c9901b655f35f08e397c4b976dd3d5e8f`  
		Last Modified: Tue, 17 Jul 2018 14:13:06 GMT  
		Size: 468.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d8c514c1971732f6df9808b1078568ad98ca39d96142504057d10e976f1da1e7`  
		Last Modified: Tue, 17 Jul 2018 14:13:05 GMT  
		Size: 231.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14444c0ed248efe86528a5979e4e06bd62680bbdc60c71aa44601f631a747e98`  
		Last Modified: Tue, 17 Jul 2018 14:13:05 GMT  
		Size: 512.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cccfc0654ca60c2d314fc5073771ba79fe252bbfb53241ef9addcb079064b219`  
		Last Modified: Thu, 23 Aug 2018 09:56:14 GMT  
		Size: 12.2 MB (12249594 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bbbd4e9b3a5384c233c3857f4e6994030fa8e4bba3c1e21eed414c5313f8ee4f`  
		Last Modified: Thu, 23 Aug 2018 09:56:11 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c4910e051e218392a7b0c134f234071add8c0a2c0e0a842051e1a9d69298deb`  
		Last Modified: Thu, 23 Aug 2018 09:56:16 GMT  
		Size: 14.6 MB (14637747 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3eadfe3491b6f86ecb134b618b32256186891bab08444273e91af447f37745ea`  
		Last Modified: Thu, 23 Aug 2018 09:56:11 GMT  
		Size: 2.2 KB (2189 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b4bd3f11075285c60fdfaf92fb7d046ecf0e1ef5c3e9adbe1566673e7a7ee725`  
		Last Modified: Thu, 23 Aug 2018 09:56:11 GMT  
		Size: 266.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:82b5167c4e6a24f7450cde1b8ddb15b79ab174ece8ef1eb1defc09e379cf776c`  
		Last Modified: Thu, 23 Aug 2018 09:56:12 GMT  
		Size: 901.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `php:rc-apache` - linux; arm variant v7

```console
$ docker pull php@sha256:fadf8caf45a40e8ce4f1123c7881c1702e232cd708d5bafb47cdf4d243294b7e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **115.0 MB (115024775 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6ad927c2acf66279e15fae3ebddb579506e24dfe3cd26cbdf782f7b5ccc9ded6`
-	Entrypoint: `["docker-php-entrypoint"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 17 Jul 2018 12:06:02 GMT
ADD file:00cfe29a37b88b6eacba9ac7c46483798b55e0aaaa9a4a3cbbd097606fd23268 in / 
# Tue, 17 Jul 2018 12:06:03 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 15:15:13 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Tue, 17 Jul 2018 15:15:13 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 17 Jul 2018 15:15:41 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 17 Jul 2018 15:15:42 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 17 Jul 2018 15:15:43 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 17 Jul 2018 15:20:08 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 15:20:08 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 17 Jul 2018 15:20:09 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 17 Jul 2018 15:20:11 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 17 Jul 2018 15:20:13 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 17 Jul 2018 15:20:15 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 17 Jul 2018 15:20:18 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 17 Jul 2018 15:20:18 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 17 Jul 2018 15:20:19 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2 --disable-cgi
# Tue, 17 Jul 2018 15:20:19 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 15:20:19 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 15:20:20 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 23 Aug 2018 12:04:30 GMT
ENV GPG_KEYS=CBAF69F173A0FEA4B537F470D66C9593118BCCB6 F38252826ACD957EF380D39F2F7956BC5DA04B5D
# Thu, 23 Aug 2018 12:04:31 GMT
ENV PHP_VERSION=7.3.0beta2
# Thu, 23 Aug 2018 12:04:31 GMT
ENV PHP_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz PHP_ASC_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz.asc
# Thu, 23 Aug 2018 12:04:32 GMT
ENV PHP_SHA256=28f040680ff517b6c3da403fd1048054de0e867246c47da36342f6a488661c70 PHP_MD5=
# Thu, 23 Aug 2018 12:04:43 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Thu, 23 Aug 2018 12:04:43 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Thu, 23 Aug 2018 12:07:21 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsodium-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	sed -e 's/stretch/buster/g' /etc/apt/sources.list > /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: -10'; 		echo; 		echo 'Package: libargon2*'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: 990'; 	} > /etc/apt/preferences.d/argon2-buster; 	apt-get update; 	apt-get install -y --no-install-recommends libargon2-dev; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-password-argon2 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Thu, 23 Aug 2018 12:07:23 GMT
COPY multi:c925dfb355ea16ba0238c8b6ca78d3cd7fe815932bf707b25bbf051070430157 in /usr/local/bin/ 
# Thu, 23 Aug 2018 12:07:24 GMT
RUN docker-php-ext-enable sodium
# Thu, 23 Aug 2018 12:07:24 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Thu, 23 Aug 2018 12:07:25 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Thu, 23 Aug 2018 12:07:25 GMT
WORKDIR /var/www/html
# Thu, 23 Aug 2018 12:07:25 GMT
EXPOSE 80/tcp
# Thu, 23 Aug 2018 12:07:26 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:e07de503944f9c1ea958f38d01af058a6e01c94d6df8bf8af06ed73fcf57793e`  
		Last Modified: Tue, 17 Jul 2018 12:18:34 GMT  
		Size: 19.3 MB (19270183 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67d2a0c1d131c19625fceb8248dc96a847893d5f98f01da360c6b39e27bc3ca0`  
		Last Modified: Tue, 17 Jul 2018 17:14:09 GMT  
		Size: 228.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:271d58948a13adbffe09af81abcb95bcfc955a7c954392052af0f5e92bfdfa31`  
		Last Modified: Tue, 17 Jul 2018 17:14:26 GMT  
		Size: 53.6 MB (53562473 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34f3a80a747ed1051b60ee82a50901d727f7b6bf1adef7ee158199fefc295d04`  
		Last Modified: Tue, 17 Jul 2018 17:14:08 GMT  
		Size: 212.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c221881787fa76132ab07db82c818dee8cef992561e89d583f67261102744ff`  
		Last Modified: Tue, 17 Jul 2018 17:17:51 GMT  
		Size: 16.2 MB (16162679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2df8f21ec4a6711b1155f4f6029563c4576c4a4dde14b2aef40ec68c8fcd8a86`  
		Last Modified: Tue, 17 Jul 2018 17:17:47 GMT  
		Size: 1.3 KB (1278 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c93a133ff30152cb97261b3996742c9a229159ff53646d11a6462fe08f0e4cfb`  
		Last Modified: Tue, 17 Jul 2018 17:17:46 GMT  
		Size: 467.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b16498caf1d0af169cd46ef7f8c5c70bc4cc48f1f7d97bb769c137452fb1f652`  
		Last Modified: Tue, 17 Jul 2018 17:17:46 GMT  
		Size: 230.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:805fc306963caf25cb37f4fb1705eb38e801b44dba304afcfaa12caf5ab2bc3d`  
		Last Modified: Tue, 17 Jul 2018 17:17:45 GMT  
		Size: 509.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:238fc83fe80cec322651ae156de80e6df0aef5aaef503e4b63da40a225c5e3c9`  
		Last Modified: Thu, 23 Aug 2018 13:03:13 GMT  
		Size: 12.2 MB (12249518 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:620496b477ce5b637304fd205f73c097f727385279da7e5b7d0e78094693fea7`  
		Last Modified: Thu, 23 Aug 2018 13:03:10 GMT  
		Size: 497.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0848b8fc014002d194bb78ddd9fb34798570a207c67f63dc8e7148d32d70bc44`  
		Last Modified: Thu, 23 Aug 2018 13:03:14 GMT  
		Size: 13.8 MB (13773142 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19be985667c9dc34881afb89c983fd1e6df09aff18f40e688c62743175432476`  
		Last Modified: Thu, 23 Aug 2018 13:03:10 GMT  
		Size: 2.2 KB (2191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a343d57ea7f14687f5b211161c1e5aa7361ecbd5702ca6518f49a586e9fa77f`  
		Last Modified: Thu, 23 Aug 2018 13:03:10 GMT  
		Size: 265.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee7789b9d30bd3a03889dd4c5afc689788cdf9cfb3edf7f53d731cce2fdc1bad`  
		Last Modified: Thu, 23 Aug 2018 13:03:10 GMT  
		Size: 903.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `php:rc-apache` - linux; arm64 variant v8

```console
$ docker pull php@sha256:0c3db7d0576edf5418c42b389e0bdcd79789d024355285606e801153c3038adf
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **121.3 MB (121283454 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:aa51ddb71fac3eb37b8a9c5f69dc38216af1111647deb5bc4dd925bdd6f404c0`
-	Entrypoint: `["docker-php-entrypoint"]`
-	Default Command: `["apache2-foreground"]`

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
# Tue, 17 Jul 2018 16:19:04 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 16:19:05 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 17 Jul 2018 16:19:06 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 17 Jul 2018 16:19:09 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 17 Jul 2018 16:19:12 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 17 Jul 2018 16:19:14 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 17 Jul 2018 16:19:16 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 17 Jul 2018 16:19:16 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 17 Jul 2018 16:19:17 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2 --disable-cgi
# Tue, 17 Jul 2018 16:19:18 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 16:19:19 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 16:19:20 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 23 Aug 2018 09:48:25 GMT
ENV GPG_KEYS=CBAF69F173A0FEA4B537F470D66C9593118BCCB6 F38252826ACD957EF380D39F2F7956BC5DA04B5D
# Thu, 23 Aug 2018 09:48:27 GMT
ENV PHP_VERSION=7.3.0beta2
# Thu, 23 Aug 2018 09:48:30 GMT
ENV PHP_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz PHP_ASC_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz.asc
# Thu, 23 Aug 2018 09:48:33 GMT
ENV PHP_SHA256=28f040680ff517b6c3da403fd1048054de0e867246c47da36342f6a488661c70 PHP_MD5=
# Thu, 23 Aug 2018 09:50:28 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Thu, 23 Aug 2018 09:50:31 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Thu, 23 Aug 2018 09:57:42 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsodium-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	sed -e 's/stretch/buster/g' /etc/apt/sources.list > /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: -10'; 		echo; 		echo 'Package: libargon2*'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: 990'; 	} > /etc/apt/preferences.d/argon2-buster; 	apt-get update; 	apt-get install -y --no-install-recommends libargon2-dev; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-password-argon2 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Thu, 23 Aug 2018 09:57:44 GMT
COPY multi:c925dfb355ea16ba0238c8b6ca78d3cd7fe815932bf707b25bbf051070430157 in /usr/local/bin/ 
# Thu, 23 Aug 2018 09:57:46 GMT
RUN docker-php-ext-enable sodium
# Thu, 23 Aug 2018 09:57:46 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Thu, 23 Aug 2018 09:57:47 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Thu, 23 Aug 2018 09:57:48 GMT
WORKDIR /var/www/html
# Thu, 23 Aug 2018 09:57:49 GMT
EXPOSE 80/tcp
# Thu, 23 Aug 2018 09:57:49 GMT
CMD ["apache2-foreground"]
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
	-	`sha256:2a1a190657e4474f8e52fed5ea4fc0a3252219e1c93c140782014917cbcb4d13`  
		Last Modified: Tue, 17 Jul 2018 18:57:55 GMT  
		Size: 16.7 MB (16709705 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:459567a3ab2fa017d0e8fb3192fb91ae0250877292699041921d538ebf421f18`  
		Last Modified: Tue, 17 Jul 2018 18:57:45 GMT  
		Size: 1.3 KB (1251 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a39800acd3e1366edf89216dc2c8b72c8aaf5cbada14cba024b533caf0d77c0`  
		Last Modified: Tue, 17 Jul 2018 18:57:44 GMT  
		Size: 437.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6bb43a3302b186c43a1b99a9281cd132a04b94c56b07207d4d2710c3d83339f`  
		Last Modified: Tue, 17 Jul 2018 18:57:43 GMT  
		Size: 231.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:be3a541b3e01e7e20a1dd4652487490845b524c5d486c63e812ee8b7307141b6`  
		Last Modified: Tue, 17 Jul 2018 18:57:44 GMT  
		Size: 490.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c71d6435ab49566779f6e03d04942706f4ae271df23af87496e4a425873f9efe`  
		Last Modified: Thu, 23 Aug 2018 14:47:15 GMT  
		Size: 12.3 MB (12250108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b19a9cf023d5314cdeb60589bbcc6e8cea81a7f784aebdb98ec9f4754c84e6d`  
		Last Modified: Thu, 23 Aug 2018 14:47:10 GMT  
		Size: 501.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87212ff6796978efc9747c188b1ae0561c9a5871e4b60f6d56da263bf41a4b7c`  
		Last Modified: Thu, 23 Aug 2018 14:47:23 GMT  
		Size: 14.4 MB (14389724 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:891d62e87ae34edb9250646edc46e8637ddb6e8d2bce1c652b109dd0ac7b690e`  
		Last Modified: Thu, 23 Aug 2018 14:47:10 GMT  
		Size: 2.2 KB (2193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:168a288cc045cb7abc857c9b1fd7c81159e3c6af82a368ed64000ab07842e1ec`  
		Last Modified: Thu, 23 Aug 2018 14:47:10 GMT  
		Size: 267.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:382db6cbf11d97c65fdc1341943fd672412f2b536e0d2e27daf68c2223394a3d`  
		Last Modified: Thu, 23 Aug 2018 14:47:10 GMT  
		Size: 903.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `php:rc-apache` - linux; 386

```console
$ docker pull php@sha256:d7c8f1b19dc9fe574f319f7b0ba56bc427878257e4b276d1e3b7aeebab93124c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **140.3 MB (140313127 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3448b1e6fa4a401fc84cff6dc1cc6f468d091fd34d9ba846a06d335ca70e3f50`
-	Entrypoint: `["docker-php-entrypoint"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 17 Jul 2018 10:50:00 GMT
ADD file:14cbcb91de201f648f46b04170dcae29163968a641f94d6ad7c3d77fc707a890 in / 
# Tue, 17 Jul 2018 10:50:03 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 15:47:26 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Tue, 17 Jul 2018 15:47:26 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 17 Jul 2018 15:48:13 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 17 Jul 2018 15:48:16 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 17 Jul 2018 15:48:17 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 17 Jul 2018 15:55:25 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 15:55:26 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 17 Jul 2018 15:55:26 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 17 Jul 2018 15:55:27 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 17 Jul 2018 15:55:28 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 17 Jul 2018 15:55:29 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 17 Jul 2018 15:55:30 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 17 Jul 2018 15:55:30 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 17 Jul 2018 15:55:30 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2 --disable-cgi
# Tue, 17 Jul 2018 15:55:31 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 15:55:31 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 15:55:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 23 Aug 2018 11:17:46 GMT
ENV GPG_KEYS=CBAF69F173A0FEA4B537F470D66C9593118BCCB6 F38252826ACD957EF380D39F2F7956BC5DA04B5D
# Thu, 23 Aug 2018 11:17:46 GMT
ENV PHP_VERSION=7.3.0beta2
# Thu, 23 Aug 2018 11:17:46 GMT
ENV PHP_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz PHP_ASC_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz.asc
# Thu, 23 Aug 2018 11:17:47 GMT
ENV PHP_SHA256=28f040680ff517b6c3da403fd1048054de0e867246c47da36342f6a488661c70 PHP_MD5=
# Thu, 23 Aug 2018 11:18:03 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Thu, 23 Aug 2018 11:18:03 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Thu, 23 Aug 2018 11:21:41 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsodium-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	sed -e 's/stretch/buster/g' /etc/apt/sources.list > /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: -10'; 		echo; 		echo 'Package: libargon2*'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: 990'; 	} > /etc/apt/preferences.d/argon2-buster; 	apt-get update; 	apt-get install -y --no-install-recommends libargon2-dev; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-password-argon2 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Thu, 23 Aug 2018 11:21:48 GMT
COPY multi:c925dfb355ea16ba0238c8b6ca78d3cd7fe815932bf707b25bbf051070430157 in /usr/local/bin/ 
# Thu, 23 Aug 2018 11:21:49 GMT
RUN docker-php-ext-enable sodium
# Thu, 23 Aug 2018 11:21:49 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Thu, 23 Aug 2018 11:21:49 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Thu, 23 Aug 2018 11:21:50 GMT
WORKDIR /var/www/html
# Thu, 23 Aug 2018 11:21:50 GMT
EXPOSE 80/tcp
# Thu, 23 Aug 2018 11:21:50 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:9f3675ed6653666b64ffa6c3dc93755d10c6f906a1cab9f061cdbe09c65323f4`  
		Last Modified: Tue, 17 Jul 2018 11:09:22 GMT  
		Size: 23.1 MB (23126377 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:373dbc1260a05667efc80f8be05f86f2c8e1ffd318e78ef63c8e46f89a458c23`  
		Last Modified: Tue, 17 Jul 2018 18:23:10 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d5043b9e8c05fba62c02a7922de92abc9897582c1d42ef5b54fadd7729ed6724`  
		Last Modified: Tue, 17 Jul 2018 18:23:45 GMT  
		Size: 71.5 MB (71484260 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7656a960ed9b5048a41ee9f4e43ba5a1be7cbf598652ea796b7e53d1f8d18c27`  
		Last Modified: Tue, 17 Jul 2018 18:23:09 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d9d55c28699d0ce3a61c5c0f364d0799467086dd003d195eb97ca63c366b8966`  
		Last Modified: Tue, 17 Jul 2018 18:28:04 GMT  
		Size: 17.6 MB (17562616 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f4b133748d2cd4318f3ec6ea0f1998cd8f77a218613390cf7943002bcaef79cc`  
		Last Modified: Tue, 17 Jul 2018 18:27:56 GMT  
		Size: 1.2 KB (1241 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:325bf5bf5aad0a669c355051eb4445912c81c9c9549bbdcd4b3a02f87a99f310`  
		Last Modified: Tue, 17 Jul 2018 18:27:54 GMT  
		Size: 440.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1d60b473c0a464669f20241289f33594fc59d89e9a5ea002c20e9b6d85803afe`  
		Last Modified: Tue, 17 Jul 2018 18:27:53 GMT  
		Size: 229.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f6870b5466e5e98dfb297ef40e21bbd2caf49384eee79fe8e5b62b9cd14bbcf`  
		Last Modified: Tue, 17 Jul 2018 18:27:52 GMT  
		Size: 486.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f4ec48ba386b6a9b283c7c74292ea5d38ae4afc5d19e2c104dd531c99af0d789`  
		Last Modified: Thu, 23 Aug 2018 14:12:13 GMT  
		Size: 12.3 MB (12251162 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3552114fa161d21471b937f224d55820e2e9c90eb9684406d5e7e58d9dda7d81`  
		Last Modified: Thu, 23 Aug 2018 14:12:08 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5f2a208f6c21b9f182eaab3542e2f7756d11021695d21c817dcefc6b34c51de`  
		Last Modified: Thu, 23 Aug 2018 14:12:17 GMT  
		Size: 15.9 MB (15882050 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c46a431acefeb582e3efc8a07afe9b51811b31717f5cf99cacfc7d00bda8b9a`  
		Last Modified: Thu, 23 Aug 2018 14:12:08 GMT  
		Size: 2.2 KB (2191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb6305c3fc32ae7efe035db050443af8e99025a05249ee8a41d8af0b5ae54c97`  
		Last Modified: Thu, 23 Aug 2018 14:12:08 GMT  
		Size: 267.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0fa92bcc39fb699b9c0ca67ce9a4f5b639e9e80364b4e75db951dffe8857517`  
		Last Modified: Thu, 23 Aug 2018 14:12:08 GMT  
		Size: 902.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `php:rc-apache` - linux; ppc64le

```console
$ docker pull php@sha256:388c53cd42b7f6e6f8dc90a07f5486cda02cd0531a21e4d0184800a596b80411
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **129.4 MB (129385515 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:885598cba862656409554a85485f2b3519cd55aaf7ceafc6959653342400c394`
-	Entrypoint: `["docker-php-entrypoint"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 17 Jul 2018 08:20:29 GMT
ADD file:d8fd3ee34d99a5bb7abafecc4f8991a3de0ad779e8fd8f3ebb33a4811ecfd5a5 in / 
# Tue, 17 Jul 2018 08:20:30 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 15:54:19 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Tue, 17 Jul 2018 15:54:21 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 17 Jul 2018 15:56:04 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 17 Jul 2018 15:56:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 17 Jul 2018 15:56:15 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 17 Jul 2018 16:04:30 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 16:04:31 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 17 Jul 2018 16:04:32 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 17 Jul 2018 16:04:34 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 17 Jul 2018 16:04:38 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 17 Jul 2018 16:04:46 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 17 Jul 2018 16:04:50 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 17 Jul 2018 16:04:50 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 17 Jul 2018 16:04:53 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2 --disable-cgi
# Tue, 17 Jul 2018 16:04:54 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 16:04:55 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jul 2018 16:04:59 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 23 Aug 2018 09:12:24 GMT
ENV GPG_KEYS=CBAF69F173A0FEA4B537F470D66C9593118BCCB6 F38252826ACD957EF380D39F2F7956BC5DA04B5D
# Thu, 23 Aug 2018 09:12:25 GMT
ENV PHP_VERSION=7.3.0beta2
# Thu, 23 Aug 2018 09:12:26 GMT
ENV PHP_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz PHP_ASC_URL=https://downloads.php.net/~cmb/php-7.3.0beta2.tar.xz.asc
# Thu, 23 Aug 2018 09:12:28 GMT
ENV PHP_SHA256=28f040680ff517b6c3da403fd1048054de0e867246c47da36342f6a488661c70 PHP_MD5=
# Thu, 23 Aug 2018 09:13:19 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Thu, 23 Aug 2018 09:13:20 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Thu, 23 Aug 2018 09:19:32 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsodium-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	sed -e 's/stretch/buster/g' /etc/apt/sources.list > /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: -10'; 		echo; 		echo 'Package: libargon2*'; 		echo 'Pin: release n=buster'; 		echo 'Pin-Priority: 990'; 	} > /etc/apt/preferences.d/argon2-buster; 	apt-get update; 	apt-get install -y --no-install-recommends libargon2-dev; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-password-argon2 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Thu, 23 Aug 2018 09:19:35 GMT
COPY multi:c925dfb355ea16ba0238c8b6ca78d3cd7fe815932bf707b25bbf051070430157 in /usr/local/bin/ 
# Thu, 23 Aug 2018 09:19:42 GMT
RUN docker-php-ext-enable sodium
# Thu, 23 Aug 2018 09:19:43 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Thu, 23 Aug 2018 09:19:45 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Thu, 23 Aug 2018 09:19:46 GMT
WORKDIR /var/www/html
# Thu, 23 Aug 2018 09:19:47 GMT
EXPOSE 80/tcp
# Thu, 23 Aug 2018 09:19:48 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:6dc0c10e32a730b4a6b92aaa59148a751864a834dc8ac1b0032717f378efc701`  
		Last Modified: Tue, 17 Jul 2018 08:26:26 GMT  
		Size: 22.7 MB (22740445 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6406e7e7e0e209551d2fc5932b81081b7ee5b53d00110a25a43cd6e5cd522c5d`  
		Last Modified: Tue, 17 Jul 2018 18:34:46 GMT  
		Size: 227.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2e6d2e43cf207ce92c12a360170e3c178401d97fa3bf53b8caaff1a77cd9319b`  
		Last Modified: Tue, 17 Jul 2018 18:35:15 GMT  
		Size: 61.8 MB (61810031 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1d64e6ea2df855f8cef3825a61c8350f67bc9c7c2b9bf22708698e3dcae919fc`  
		Last Modified: Tue, 17 Jul 2018 18:34:43 GMT  
		Size: 212.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70bf10867575d96c0b481a187216561a91e276db1d5c38dca841ac4ed2900489`  
		Last Modified: Tue, 17 Jul 2018 18:37:32 GMT  
		Size: 17.3 MB (17348331 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cf9456c6196ef547186fb17a52d895f0ba57aa6be88ca128703730f4abe36ece`  
		Last Modified: Tue, 17 Jul 2018 18:37:22 GMT  
		Size: 1.3 KB (1280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d39ccfba093918882764f89d1e024831191044c9f56daca67a966ad8b238945e`  
		Last Modified: Tue, 17 Jul 2018 18:37:21 GMT  
		Size: 474.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d5ef7a7cc6b22430131a48003ab45a89ec57af6fa78ee7e9b1ac8beec618b38`  
		Last Modified: Tue, 17 Jul 2018 18:37:18 GMT  
		Size: 230.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8de5878d75dfa279a26be7cebb298bd4b1c2d510030c3eff4e670a44431d78d`  
		Last Modified: Tue, 17 Jul 2018 18:37:17 GMT  
		Size: 516.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c511da225a402d1339598c687b027f2c54a7ea7a6b73a5df2669352ef97509e7`  
		Last Modified: Thu, 23 Aug 2018 12:07:33 GMT  
		Size: 12.3 MB (12250245 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f57e1372c71e5aa1d77872ea4f81512540bd8757d4d45ae96c85f524e4fa1920`  
		Last Modified: Thu, 23 Aug 2018 12:06:51 GMT  
		Size: 501.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:211d24d7af3205a0fa9fd20d59cee52835ecb42ada1f0002150894294bfc1a0b`  
		Last Modified: Thu, 23 Aug 2018 12:07:00 GMT  
		Size: 15.2 MB (15229659 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ca33a144a1d76abdb709a3e91c208f6a7c200adcde0ba83b5b083a702fcf5d9`  
		Last Modified: Thu, 23 Aug 2018 12:06:51 GMT  
		Size: 2.2 KB (2192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9c96db0cdccd074fdc280dac035581439449631f7792c924a65a98ee789b9c7`  
		Last Modified: Thu, 23 Aug 2018 12:06:51 GMT  
		Size: 267.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fef77caa7c4710841a3589239b5f7ded4537715dc79dcd51941ca91bdcef0e6c`  
		Last Modified: Thu, 23 Aug 2018 12:06:51 GMT  
		Size: 905.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
