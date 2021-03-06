## `rabbitmq:3-management`

```console
$ docker pull rabbitmq@sha256:0b36ea1a8df9e53228aaeee277680de2cc97c7d675bc2d5dbe1cc9e3836a9d9f
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

### `rabbitmq:3-management` - linux; amd64

```console
$ docker pull rabbitmq@sha256:62df1593c38a2fb518895c0e9402230be77e4249f08c91e2acc73f68a6fdcbbe
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **73.4 MB (73385816 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:df80af9ca0c9dfba0a267a707f6f517929a3c49679390e70b66c32d23f48b76a`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Tue, 17 Jul 2018 00:28:04 GMT
ADD file:919939fa022472751b717443eea9f1d7ab5c0723f1f3a6b776d3b83d22bde818 in / 
# Tue, 17 Jul 2018 00:28:04 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 05:08:55 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 05:08:56 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Tue, 17 Jul 2018 05:08:56 GMT
ENV GOSU_VERSION=1.10
# Tue, 31 Jul 2018 17:26:50 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 31 Jul 2018 17:26:57 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Tue, 31 Jul 2018 17:27:25 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 31 Jul 2018 17:27:33 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Tue, 31 Jul 2018 17:27:34 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 31 Jul 2018 17:27:34 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Tue, 31 Jul 2018 17:27:34 GMT
ENV RABBITMQ_VERSION=3.7.7
# Tue, 31 Jul 2018 17:27:34 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.7
# Tue, 31 Jul 2018 17:27:35 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.7-1
# Tue, 31 Jul 2018 17:28:06 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Tue, 31 Jul 2018 17:28:06 GMT
ENV LANG=C.UTF-8
# Tue, 31 Jul 2018 17:28:06 GMT
ENV HOME=/var/lib/rabbitmq
# Tue, 31 Jul 2018 17:28:22 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Tue, 31 Jul 2018 17:28:22 GMT
VOLUME [/var/lib/rabbitmq]
# Tue, 31 Jul 2018 17:28:23 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Tue, 31 Jul 2018 17:28:24 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Tue, 31 Jul 2018 17:28:25 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Tue, 31 Jul 2018 17:28:26 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Tue, 31 Jul 2018 17:28:27 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 31 Jul 2018 17:28:27 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Tue, 31 Jul 2018 17:28:28 GMT
CMD ["rabbitmq-server"]
# Tue, 31 Jul 2018 17:29:07 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Tue, 31 Jul 2018 17:29:25 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Tue, 31 Jul 2018 17:29:26 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:be8881be8156e4068e611fe956aba2b9593ebd953be14fb7feea6d0659aa3abe`  
		Last Modified: Tue, 17 Jul 2018 00:44:17 GMT  
		Size: 22.5 MB (22485906 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab96a756674d6fbcb8befe799edf35b35baf3b4f710da17d04c231913ae4ddeb`  
		Last Modified: Tue, 17 Jul 2018 05:13:27 GMT  
		Size: 4.5 MB (4498548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1afa3c8b1ac8d1dca40c1f11cac5ed8bf1634214b2af876a49e147c201a6a010`  
		Last Modified: Tue, 17 Jul 2018 05:13:23 GMT  
		Size: 4.1 KB (4069 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d6ac301ca22000615fcd45abffcce2fa47cfdc917adea570192ed92188241b1`  
		Last Modified: Tue, 31 Jul 2018 17:34:46 GMT  
		Size: 951.9 KB (951890 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:665d14f5b3ec3d1362c7d7d68816aefeb9e0ae750d6dd82cd0b6d494b0438d32`  
		Last Modified: Tue, 31 Jul 2018 17:34:46 GMT  
		Size: 357.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8c7fea479bc6c4f555b0111251fd980052c087ddad8e81069ddbb7fd8542c4e`  
		Last Modified: Tue, 31 Jul 2018 17:34:51 GMT  
		Size: 27.5 MB (27499898 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f57b98898fc80113a2ffdd7c6d09a27e0711e18ab5eb2e387f57a0c70fb2f50`  
		Last Modified: Tue, 31 Jul 2018 17:34:47 GMT  
		Size: 10.3 MB (10315414 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c57de6ff1fdaef9550d687bb3ac4665ab2ffb539f222c7b31c6930690c8fd35b`  
		Last Modified: Tue, 31 Jul 2018 17:34:43 GMT  
		Size: 2.3 KB (2264 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb20b6079db39cec90138165d6ee3f8f2220957b10c552460fdb657d6bfb96dc`  
		Last Modified: Tue, 31 Jul 2018 17:34:43 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bfcd2c7011de9eea737d037fbb7393b59a4d6a64bec60441781d2aa5d4a672e5`  
		Last Modified: Tue, 31 Jul 2018 17:34:43 GMT  
		Size: 125.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71a3874699ee66d3bba45babb25bb20ddfd96ca81f12387663f47c1a2aa7ea8a`  
		Last Modified: Tue, 31 Jul 2018 17:34:43 GMT  
		Size: 4.2 KB (4180 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b914bcc4a84d54fae2c673dd46520cf0b3baea54786220a9b2ff1a98715e372`  
		Last Modified: Tue, 31 Jul 2018 17:34:43 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f63e1b988a2ddd87003891f4260289d438c19270fb5177b3cd0dadef56b877b5`  
		Last Modified: Tue, 31 Jul 2018 17:36:20 GMT  
		Size: 191.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e39cb8f0eaed2861797ee71f21380d4a7a41a1620cf1cd45bf38e39e26850eec`  
		Last Modified: Tue, 31 Jul 2018 17:36:23 GMT  
		Size: 7.6 MB (7622708 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; arm variant v5

```console
$ docker pull rabbitmq@sha256:f180a001e76a2446ebea54d44268e665b715e79eb3bd70e7a9b293dd6f34bb38
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **69.1 MB (69094921 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a5066bec309443b2449c50068498eab1b566980fa30ab93d90cccde8a7ac7b37`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Tue, 17 Jul 2018 08:56:27 GMT
ADD file:60830ba735048c6cbecbc75b83364ad442e1e5ee691ef74dad4eb07f720f8919 in / 
# Tue, 17 Jul 2018 08:56:29 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 11:49:47 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 11:49:48 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Tue, 17 Jul 2018 11:49:48 GMT
ENV GOSU_VERSION=1.10
# Wed, 01 Aug 2018 09:25:10 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 01 Aug 2018 09:25:11 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 01 Aug 2018 09:25:52 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 09:25:52 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 01 Aug 2018 09:25:53 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 01 Aug 2018 09:25:53 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Wed, 01 Aug 2018 09:25:53 GMT
ENV RABBITMQ_VERSION=3.7.7
# Wed, 01 Aug 2018 09:25:53 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.7
# Wed, 01 Aug 2018 09:25:54 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.7-1
# Wed, 01 Aug 2018 09:26:29 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 09:26:29 GMT
ENV LANG=C.UTF-8
# Wed, 01 Aug 2018 09:26:29 GMT
ENV HOME=/var/lib/rabbitmq
# Wed, 01 Aug 2018 09:26:30 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Wed, 01 Aug 2018 09:26:30 GMT
VOLUME [/var/lib/rabbitmq]
# Wed, 01 Aug 2018 09:26:31 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Wed, 01 Aug 2018 09:26:32 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Wed, 01 Aug 2018 09:26:32 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Wed, 01 Aug 2018 09:26:33 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 01 Aug 2018 09:26:34 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 01 Aug 2018 09:26:34 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Wed, 01 Aug 2018 09:26:34 GMT
CMD ["rabbitmq-server"]
# Wed, 01 Aug 2018 09:26:57 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Wed, 01 Aug 2018 09:27:17 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Wed, 01 Aug 2018 09:27:18 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:235e2c34c6b727f2b00aae7eed907f84338b4002c487e0caaa123a50334c0810`  
		Last Modified: Tue, 17 Jul 2018 09:09:00 GMT  
		Size: 21.2 MB (21162647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8540b795e8a7c6c38d50f1474874abda462d019ab396c11bdf7090dd4f9e7f9a`  
		Last Modified: Tue, 17 Jul 2018 11:54:32 GMT  
		Size: 4.2 MB (4231655 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:998bdb1e59dc31e37e201a8e04826f4e6997a840c7c858f00ffd223751749940`  
		Last Modified: Tue, 17 Jul 2018 11:54:30 GMT  
		Size: 4.1 KB (4086 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e0c872e70fe5123eb7400d1589332284a056cd0e3edceb81c7ecf5b89d11ab1`  
		Last Modified: Wed, 01 Aug 2018 09:29:14 GMT  
		Size: 942.4 KB (942395 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f7b259fccee7091bea15261f56ac8139ce346331133979f64da91e0e02bcc11`  
		Last Modified: Wed, 01 Aug 2018 09:29:12 GMT  
		Size: 358.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c80c75f0c94cbe72ab20b20beb091fdd4c9f97b70742ddd549b549986ce747ab`  
		Last Modified: Wed, 01 Aug 2018 09:29:17 GMT  
		Size: 25.0 MB (24988459 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3161b273a0d8e422311b022cb5d8ba787bd688a7072a732394f75cc3996a83af`  
		Last Modified: Wed, 01 Aug 2018 09:29:14 GMT  
		Size: 10.3 MB (10285203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d4ae5c5ea13f1a4f6768e7706ff05662852ff7c00182e6e0b61d530c80ec4da`  
		Last Modified: Wed, 01 Aug 2018 09:29:12 GMT  
		Size: 2.3 KB (2264 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:af8321df0b137fe402792f1186f5b9c88a019e256e2ec4c485463d72e9f5b54b`  
		Last Modified: Wed, 01 Aug 2018 09:29:11 GMT  
		Size: 146.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df98681172352860cc533d703765f0679b0bdb2e6e21fe515bc3c547b8bb76ef`  
		Last Modified: Wed, 01 Aug 2018 09:29:11 GMT  
		Size: 124.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f583dca8e9d551609038b1b197b49f34ed7f9ebb582679831886c76c1bc08c88`  
		Last Modified: Wed, 01 Aug 2018 09:29:11 GMT  
		Size: 4.2 KB (4181 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fa9e193924d424c7736edc0dfdda51366aa993ac276a90dfdbfcb3d1276d902`  
		Last Modified: Wed, 01 Aug 2018 09:29:11 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a5cb51aa184e5dcffc7e7859af3fd9e6532364cf3fd4fca2a591a6d845fc76b`  
		Last Modified: Wed, 01 Aug 2018 09:29:39 GMT  
		Size: 191.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:be3484aa1465d1bfe51dae6630b15ba237fb0664de4b468567984c6730d2fb57`  
		Last Modified: Wed, 01 Aug 2018 09:29:42 GMT  
		Size: 7.5 MB (7473091 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; arm variant v7

```console
$ docker pull rabbitmq@sha256:9d216a956f772500a4579d6b5a0332d44d5ccda9b4efebde60f044f0070b7f98
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **66.2 MB (66192800 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6c88714d820001ba13d065311e33bb78bba50c271a2d47d062e611a02a080195`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Tue, 17 Jul 2018 12:06:02 GMT
ADD file:00cfe29a37b88b6eacba9ac7c46483798b55e0aaaa9a4a3cbbd097606fd23268 in / 
# Tue, 17 Jul 2018 12:06:03 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 15:47:04 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 15:47:05 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Tue, 17 Jul 2018 15:47:06 GMT
ENV GOSU_VERSION=1.10
# Wed, 01 Aug 2018 12:29:11 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 01 Aug 2018 12:29:12 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 01 Aug 2018 12:29:45 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 12:29:45 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 01 Aug 2018 12:29:46 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 01 Aug 2018 12:29:46 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Wed, 01 Aug 2018 12:29:46 GMT
ENV RABBITMQ_VERSION=3.7.7
# Wed, 01 Aug 2018 12:29:47 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.7
# Wed, 01 Aug 2018 12:29:47 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.7-1
# Wed, 01 Aug 2018 12:30:14 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 12:30:14 GMT
ENV LANG=C.UTF-8
# Wed, 01 Aug 2018 12:30:15 GMT
ENV HOME=/var/lib/rabbitmq
# Wed, 01 Aug 2018 12:30:16 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Wed, 01 Aug 2018 12:30:16 GMT
VOLUME [/var/lib/rabbitmq]
# Wed, 01 Aug 2018 12:30:17 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Wed, 01 Aug 2018 12:30:18 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Wed, 01 Aug 2018 12:30:19 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Wed, 01 Aug 2018 12:30:20 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 01 Aug 2018 12:30:20 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 01 Aug 2018 12:30:21 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Wed, 01 Aug 2018 12:30:21 GMT
CMD ["rabbitmq-server"]
# Wed, 01 Aug 2018 12:30:33 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Wed, 01 Aug 2018 12:30:49 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Wed, 01 Aug 2018 12:30:50 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:e07de503944f9c1ea958f38d01af058a6e01c94d6df8bf8af06ed73fcf57793e`  
		Last Modified: Tue, 17 Jul 2018 12:18:34 GMT  
		Size: 19.3 MB (19270183 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6b93eccf0393bb25da8d04c712dac608c0a8df8b76ed7af505ba855e4ed02869`  
		Last Modified: Tue, 17 Jul 2018 15:51:27 GMT  
		Size: 3.9 MB (3868688 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14978e5687ef96cbb16fbce9b5cb431b934c25bd4ca2236fbee5b34d75cfe6c7`  
		Last Modified: Tue, 17 Jul 2018 15:51:25 GMT  
		Size: 4.1 KB (4084 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e119944036d90b5506976760570d399bd4c6f10db229d7422b07a4b28781443`  
		Last Modified: Wed, 01 Aug 2018 12:32:32 GMT  
		Size: 926.1 KB (926055 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce61db5df3923df2d1c62dbe8d0f843d9065a704d5d5d4e8b6a34d9ca67751e4`  
		Last Modified: Wed, 01 Aug 2018 12:32:32 GMT  
		Size: 360.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5eaf456190bd6427bcead44e1554faff1ad423c980d711d8f512ad3cb18691e`  
		Last Modified: Wed, 01 Aug 2018 12:32:36 GMT  
		Size: 24.7 MB (24675107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6f53ceffa31c1ad9b50f28f9894668f8c22b8c54f6a7d88850727e1270fb5c3`  
		Last Modified: Wed, 01 Aug 2018 12:32:33 GMT  
		Size: 10.3 MB (10258372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4d56e7bd6b65b0843f658f0f78935c6e536ba0599a1040a69bd853ac68659e73`  
		Last Modified: Wed, 01 Aug 2018 12:32:30 GMT  
		Size: 2.3 KB (2260 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:478f7f66b6b1c1b0958accbb6c9a461f5250baad44b6523ef8bb3ca4660966ec`  
		Last Modified: Wed, 01 Aug 2018 12:32:31 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25546b4e0b1d95bf0ad2b198e339f83717d4f77817c0989530165093b7eaefc1`  
		Last Modified: Wed, 01 Aug 2018 12:32:30 GMT  
		Size: 123.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3fbc5c2394954d58dafc7834f0ce794343265e2c1468bdb5cc86985399448e90`  
		Last Modified: Wed, 01 Aug 2018 12:32:30 GMT  
		Size: 4.2 KB (4180 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67aad8d371563276d3117e1da649509a8070db95113c15053d76fa27cc408a53`  
		Last Modified: Wed, 01 Aug 2018 12:32:30 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecafc416ad917fbdb9492228548682479f4494018391d28366729a56f6bf1a76`  
		Last Modified: Wed, 01 Aug 2018 12:32:56 GMT  
		Size: 191.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c9d39f8e89e6230ca6eb0f1be5a4d8621610877fd2f1a419ab32876de951ea5`  
		Last Modified: Wed, 01 Aug 2018 12:32:59 GMT  
		Size: 7.2 MB (7182931 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; arm64 variant v8

```console
$ docker pull rabbitmq@sha256:370f22c0d4ed02c557833527700c401e4470c8e352ef0629a199305dbf2f053d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **68.1 MB (68134817 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0b827409c0ba394b6b2539093a84a63013e469df7d5da8ef359f98446b0b023d`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Tue, 17 Jul 2018 08:48:06 GMT
ADD file:b6ea996ffd5aa4dade8cb1d721c2716614c03110d98683aca206c7ab52fcb9e5 in / 
# Tue, 17 Jul 2018 08:48:07 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 16:29:18 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 16:29:21 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Tue, 17 Jul 2018 16:29:22 GMT
ENV GOSU_VERSION=1.10
# Wed, 01 Aug 2018 10:23:00 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 01 Aug 2018 10:23:03 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 01 Aug 2018 10:24:09 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 10:24:10 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 01 Aug 2018 10:24:11 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 01 Aug 2018 10:24:12 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Wed, 01 Aug 2018 10:24:13 GMT
ENV RABBITMQ_VERSION=3.7.7
# Wed, 01 Aug 2018 10:24:14 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.7
# Wed, 01 Aug 2018 10:24:18 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.7-1
# Wed, 01 Aug 2018 10:25:53 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 10:26:07 GMT
ENV LANG=C.UTF-8
# Wed, 01 Aug 2018 10:26:08 GMT
ENV HOME=/var/lib/rabbitmq
# Wed, 01 Aug 2018 10:26:10 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Wed, 01 Aug 2018 10:26:25 GMT
VOLUME [/var/lib/rabbitmq]
# Wed, 01 Aug 2018 10:26:28 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Wed, 01 Aug 2018 10:26:30 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Wed, 01 Aug 2018 10:26:31 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Wed, 01 Aug 2018 10:26:33 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 01 Aug 2018 10:26:50 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 01 Aug 2018 10:26:51 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Wed, 01 Aug 2018 10:26:52 GMT
CMD ["rabbitmq-server"]
# Wed, 01 Aug 2018 10:27:23 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Wed, 01 Aug 2018 10:28:33 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Wed, 01 Aug 2018 10:28:35 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:74a932489409d8d15db14c8a4a811fb46c7386bb06ea678ff27084d5657eeaaf`  
		Last Modified: Tue, 17 Jul 2018 08:57:35 GMT  
		Size: 20.3 MB (20331647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5a59efad40e5fb26d41e7a913c5b2f4e49489de7c23c8fdbdcb3a4f46ea7999`  
		Last Modified: Tue, 17 Jul 2018 16:38:20 GMT  
		Size: 4.1 MB (4073273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cc7107facb5e3c5ae6928aa3c4b8d48369a2b1572299f4bb82a5cab6c19cc85`  
		Last Modified: Tue, 17 Jul 2018 16:38:18 GMT  
		Size: 4.1 KB (4084 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d64e5fdd554727e68c89bfe4aedd0da7bb9db982315c9ea9d74d124db2c086c`  
		Last Modified: Wed, 01 Aug 2018 10:37:11 GMT  
		Size: 919.3 KB (919312 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61704bc43869851ec52c2c4dbb151746dd96070c19265992519d93515fd0e0e4`  
		Last Modified: Wed, 01 Aug 2018 10:37:10 GMT  
		Size: 358.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:959d9207857217fa68a0a4228e28f49f0c0e09e269f244ea7a1344951aaafbf1`  
		Last Modified: Wed, 01 Aug 2018 10:37:16 GMT  
		Size: 25.0 MB (25043545 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:06d183d723f430adf2906ad143e929067d32aef7f6e0d79a31e3b0e9d6f17350`  
		Last Modified: Wed, 01 Aug 2018 10:37:12 GMT  
		Size: 10.3 MB (10279829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dfa912c34633b00a1669845935c1f16e05cbd499d58566117f2c0b9532017825`  
		Last Modified: Wed, 01 Aug 2018 10:37:08 GMT  
		Size: 2.3 KB (2263 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9f54bafc80c30be3364ccc4213f761343ef2dff8d712284533ca5e4324229f1`  
		Last Modified: Wed, 01 Aug 2018 10:37:08 GMT  
		Size: 146.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c0f37291f4df73a669c371200746d271f4e4f07c375cdadc4860d1cffb366ba`  
		Last Modified: Wed, 01 Aug 2018 10:37:09 GMT  
		Size: 125.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23f400b01eac91b3e0f51fabc8d84977470dbd1c47e4b7111517dcd2dd0743d1`  
		Last Modified: Wed, 01 Aug 2018 10:37:08 GMT  
		Size: 4.2 KB (4181 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3fc6b73b7f4bacf2d45350a34afa2e101a06cb8546adafcb428d8d42b0175c21`  
		Last Modified: Wed, 01 Aug 2018 10:37:08 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4171639ec5bb2ac37ab6ce068b5b945aec0af4a8a83e2bab249d4fbd8151f943`  
		Last Modified: Wed, 01 Aug 2018 10:38:32 GMT  
		Size: 191.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:166ccb9044f7bb089861343e409d4584bbb0e11dfa2dedc15fcaf102147d1e05`  
		Last Modified: Wed, 01 Aug 2018 10:38:36 GMT  
		Size: 7.5 MB (7475743 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; 386

```console
$ docker pull rabbitmq@sha256:e7dec558fa707b35be250c43d48bf4d4e18686afff2cc756574cecbd4c21c250
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **74.6 MB (74630556 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3d43225b7c54d9ec9a861e04867dd2f47483f169ddb2ed01167b24536adfdf86`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Tue, 17 Jul 2018 10:50:00 GMT
ADD file:14cbcb91de201f648f46b04170dcae29163968a641f94d6ad7c3d77fc707a890 in / 
# Tue, 17 Jul 2018 10:50:03 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 17:34:30 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 17:34:31 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Tue, 17 Jul 2018 17:34:31 GMT
ENV GOSU_VERSION=1.10
# Wed, 01 Aug 2018 11:43:39 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 01 Aug 2018 11:43:40 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 01 Aug 2018 11:44:20 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 11:44:21 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 01 Aug 2018 11:44:21 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 01 Aug 2018 11:44:21 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Wed, 01 Aug 2018 11:44:22 GMT
ENV RABBITMQ_VERSION=3.7.7
# Wed, 01 Aug 2018 11:44:22 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.7
# Wed, 01 Aug 2018 11:44:22 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.7-1
# Wed, 01 Aug 2018 11:44:55 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 11:44:55 GMT
ENV LANG=C.UTF-8
# Wed, 01 Aug 2018 11:44:56 GMT
ENV HOME=/var/lib/rabbitmq
# Wed, 01 Aug 2018 11:44:56 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Wed, 01 Aug 2018 11:44:57 GMT
VOLUME [/var/lib/rabbitmq]
# Wed, 01 Aug 2018 11:44:58 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Wed, 01 Aug 2018 11:44:59 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Wed, 01 Aug 2018 11:45:00 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Wed, 01 Aug 2018 11:45:01 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 01 Aug 2018 11:45:01 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 01 Aug 2018 11:45:01 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Wed, 01 Aug 2018 11:45:02 GMT
CMD ["rabbitmq-server"]
# Wed, 01 Aug 2018 11:45:33 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Wed, 01 Aug 2018 11:45:50 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Wed, 01 Aug 2018 11:45:50 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:9f3675ed6653666b64ffa6c3dc93755d10c6f906a1cab9f061cdbe09c65323f4`  
		Last Modified: Tue, 17 Jul 2018 11:09:22 GMT  
		Size: 23.1 MB (23126377 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f89642160d4fbf6e009f008e93db36c6ebbedd62743e4739524fd730674ed748`  
		Last Modified: Tue, 17 Jul 2018 17:39:17 GMT  
		Size: 4.8 MB (4803941 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10a1fb1d11cf627fc3f4906f1d529ee97654f71a0c569881f5072d36b93a6f07`  
		Last Modified: Tue, 17 Jul 2018 17:39:13 GMT  
		Size: 4.1 KB (4060 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed3c4e62b8d0e5e203b24d83cd93f9e52a9f3a61e05b3b74e0cb98e2ee97278a`  
		Last Modified: Wed, 01 Aug 2018 11:50:34 GMT  
		Size: 931.4 KB (931431 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2a73734ee78f140d9eee365a25f0a9c502546c34d3cc6130ae2a47b099473e5`  
		Last Modified: Wed, 01 Aug 2018 11:50:34 GMT  
		Size: 358.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8728ad601e74e292756bd7e3282a3832d7fab1d52fd798b0f5b61f21d7f4365d`  
		Last Modified: Wed, 01 Aug 2018 11:50:40 GMT  
		Size: 27.7 MB (27706220 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e6b563b16d9738dd8165852b3f9db7ac8f3ff35e6ea42051edcfb04aadd0551`  
		Last Modified: Wed, 01 Aug 2018 11:50:36 GMT  
		Size: 10.3 MB (10336583 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7113728f7e45432b45c7e911fbc4437b440378f426b7d22ea7c0cf59b7a3b181`  
		Last Modified: Wed, 01 Aug 2018 11:50:32 GMT  
		Size: 2.3 KB (2263 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80d1d8e9f394a1bf1d913f854d1cd332ce666936d93628a757ca6c771a57b537`  
		Last Modified: Wed, 01 Aug 2018 11:50:31 GMT  
		Size: 146.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c0b40f99c7da38edcf51dc607b0a004aa45e5d836e904a99b17c22a4f55bb5e9`  
		Last Modified: Wed, 01 Aug 2018 11:50:31 GMT  
		Size: 125.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b76bac74cfd7314df8ba851a3ff70096d1614d2ef7d1cb87d9c6999544c2c950`  
		Last Modified: Wed, 01 Aug 2018 11:50:32 GMT  
		Size: 4.2 KB (4181 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d946c9546c8527f840d70daf3ecd8dbab5b814f9bc816e2cb15574d869602445`  
		Last Modified: Wed, 01 Aug 2018 11:50:31 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:59d4da7941439b0ca92c16de9c83d677db6af8bb8668e8724b63d3cf46cedb58`  
		Last Modified: Wed, 01 Aug 2018 11:51:42 GMT  
		Size: 191.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:64929343ed95712c80a11ab6cf87dfb8e71e917ed2e03c358771b5e5a7514fa0`  
		Last Modified: Wed, 01 Aug 2018 11:51:47 GMT  
		Size: 7.7 MB (7714559 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; ppc64le

```console
$ docker pull rabbitmq@sha256:bfdc638080ebee1dcc2f9c5b4ad70ead369e2261ff9c377aae541588beb08384
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **71.5 MB (71539662 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3c73b4d1ee2b58dd668a69c55b55c66f29f33a7b82119a4c94c663655a2de45d`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Tue, 17 Jul 2018 08:20:29 GMT
ADD file:d8fd3ee34d99a5bb7abafecc4f8991a3de0ad779e8fd8f3ebb33a4811ecfd5a5 in / 
# Tue, 17 Jul 2018 08:20:30 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 14:34:27 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 14:34:33 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Tue, 17 Jul 2018 14:34:34 GMT
ENV GOSU_VERSION=1.10
# Wed, 01 Aug 2018 14:02:11 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 01 Aug 2018 14:02:36 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 01 Aug 2018 14:07:00 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 14:07:08 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 01 Aug 2018 14:07:16 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 01 Aug 2018 14:07:25 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Wed, 01 Aug 2018 14:07:32 GMT
ENV RABBITMQ_VERSION=3.7.7
# Wed, 01 Aug 2018 14:07:40 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.7
# Wed, 01 Aug 2018 14:07:48 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.7-1
# Wed, 01 Aug 2018 14:12:37 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 14:12:44 GMT
ENV LANG=C.UTF-8
# Wed, 01 Aug 2018 14:12:54 GMT
ENV HOME=/var/lib/rabbitmq
# Wed, 01 Aug 2018 14:13:16 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Wed, 01 Aug 2018 14:13:25 GMT
VOLUME [/var/lib/rabbitmq]
# Wed, 01 Aug 2018 14:13:42 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Wed, 01 Aug 2018 14:14:03 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Wed, 01 Aug 2018 14:14:14 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Wed, 01 Aug 2018 14:14:38 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 01 Aug 2018 14:14:46 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 01 Aug 2018 14:14:55 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Wed, 01 Aug 2018 14:15:06 GMT
CMD ["rabbitmq-server"]
# Wed, 01 Aug 2018 14:16:00 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Wed, 01 Aug 2018 14:18:32 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Wed, 01 Aug 2018 14:18:43 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:6dc0c10e32a730b4a6b92aaa59148a751864a834dc8ac1b0032717f378efc701`  
		Last Modified: Tue, 17 Jul 2018 08:26:26 GMT  
		Size: 22.7 MB (22740445 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9aac2948a99284b0ce44c011069b2b7e92e94faa37cfd97636f33eec41ab762b`  
		Last Modified: Tue, 17 Jul 2018 14:45:45 GMT  
		Size: 4.4 MB (4360653 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:239075cb9f3b9e43a7ccea9b473ebca4bef7f45fd0bc42f70d142ffee15fd447`  
		Last Modified: Tue, 17 Jul 2018 14:45:43 GMT  
		Size: 4.1 KB (4108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49678ae83f77d026416e93bee9652f10189ec7ebf43eb338149c19cc25414139`  
		Last Modified: Wed, 01 Aug 2018 14:47:31 GMT  
		Size: 920.9 KB (920872 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d00edda311ffbb19c9a457bf19334ba1b6f99b5379a8cdc33899af09f0b12ce`  
		Last Modified: Wed, 01 Aug 2018 14:47:31 GMT  
		Size: 359.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5936c233eb94f4a9150290db4df1b2da7ae782ba677246a9d29a8cccfe0f099`  
		Last Modified: Wed, 01 Aug 2018 14:47:42 GMT  
		Size: 25.4 MB (25379876 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7c2a05622eac370ba640b47473813543ac9933a9d50b4ac269ed22dce7c57be6`  
		Last Modified: Wed, 01 Aug 2018 14:47:35 GMT  
		Size: 10.3 MB (10299942 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc1510e214f1319675065950b11caa5ccc186492feceed854ec861e1080f178a`  
		Last Modified: Wed, 01 Aug 2018 14:47:27 GMT  
		Size: 2.3 KB (2266 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:06d1aa7e00f40a337fd121e5f344b3af557217f46500aa63e3ddca3a3495ca57`  
		Last Modified: Wed, 01 Aug 2018 14:47:27 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebcb65b6226071d55316b16e336c64faffedd3a94a9cda8df1cd4c7e0fd774e6`  
		Last Modified: Wed, 01 Aug 2018 14:47:27 GMT  
		Size: 125.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf35aa51f237b9094c191bac9731348e93ae650097cff545076733d97ee807fe`  
		Last Modified: Wed, 01 Aug 2018 14:47:27 GMT  
		Size: 4.2 KB (4180 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa52143a69285739aa9765a7f9b824a523eedb83b038a4e5a3eaef33e8f77bbe`  
		Last Modified: Wed, 01 Aug 2018 14:47:27 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9478af3178b5b12813495d76699ec21d1fd88545c4593a47448972af42c9db78`  
		Last Modified: Wed, 01 Aug 2018 14:49:08 GMT  
		Size: 192.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1b23ce859bf3af9a69183c3ee137c072c05f26eaa3f29b074ab49523304477f`  
		Last Modified: Wed, 01 Aug 2018 14:49:24 GMT  
		Size: 7.8 MB (7826378 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `rabbitmq:3-management` - linux; s390x

```console
$ docker pull rabbitmq@sha256:64b2e8b12ba8c67237966379d1d5f85b3b3675a4fd8a78bac9c5ea25b4dc655a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **70.8 MB (70800505 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3c989c94949bf9b52207c449f20213f7e182cfaa2e870c51b1961f63cb39f244`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Tue, 17 Jul 2018 11:43:35 GMT
ADD file:32e6375c708c1a29a33eef651992d744ae278ef980cfb74086bc899cb8fffdfb in / 
# Tue, 17 Jul 2018 11:43:36 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 14:08:00 GMT
RUN set -eux; 	apt-get update; 	apt-get install -y --no-install-recommends 		gnupg 		dirmngr 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 14:08:01 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Tue, 17 Jul 2018 14:08:01 GMT
ENV GOSU_VERSION=1.10
# Wed, 01 Aug 2018 12:12:01 GMT
RUN set -eux; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 01 Aug 2018 12:12:01 GMT
RUN set -eux; 	sed 's/stretch/buster/g' /etc/apt/sources.list 		| tee /etc/apt/sources.list.d/buster.list; 	{ 		echo 'Package: *'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 1'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=buster*'; 		echo 'Pin-Priority: 999'; 		echo; 		echo 'Package: erlang*'; 		echo 'Pin: release n=stretch*'; 		echo 'Pin-Priority: -10'; 	} | tee /etc/apt/preferences.d/buster-erlang
# Wed, 01 Aug 2018 12:12:30 GMT
RUN set -eux; 	apt-get update; 	if apt-cache show erlang-base-hipe 2>/dev/null | grep -q 'Package: erlang-base-hipe'; then 		apt-get install -y --no-install-recommends 			erlang-base-hipe 		; 	fi; 	apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 12:12:30 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 01 Aug 2018 12:12:31 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 01 Aug 2018 12:12:31 GMT
ENV RABBITMQ_GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Wed, 01 Aug 2018 12:12:31 GMT
ENV RABBITMQ_VERSION=3.7.7
# Wed, 01 Aug 2018 12:12:31 GMT
ENV RABBITMQ_GITHUB_TAG=v3.7.7
# Wed, 01 Aug 2018 12:12:31 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.7.7-1
# Wed, 01 Aug 2018 12:12:47 GMT
RUN set -eux; 		apt-get update; 	apt-get install -y --no-install-recommends ca-certificates wget; 		wget -O rabbitmq-server.deb.asc "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb.asc"; 	wget -O rabbitmq-server.deb     "https://github.com/rabbitmq/rabbitmq-server/releases/download/$RABBITMQ_GITHUB_TAG/rabbitmq-server_${RABBITMQ_DEBIAN_VERSION}_all.deb"; 		apt-get purge -y --auto-remove ca-certificates wget; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$RABBITMQ_GPG_KEY"; 	gpg --batch --verify rabbitmq-server.deb.asc rabbitmq-server.deb; 	command -v gpgconf && gpgconf --kill all || :; 	rm -rf "$GNUPGHOME"; 		apt install -y --no-install-recommends ./rabbitmq-server.deb; 	dpkg -l | grep rabbitmq-server; 	rm -f rabbitmq-server.deb*; 		rm -rf /var/lib/apt/lists/*
# Wed, 01 Aug 2018 12:12:47 GMT
ENV LANG=C.UTF-8
# Wed, 01 Aug 2018 12:12:48 GMT
ENV HOME=/var/lib/rabbitmq
# Wed, 01 Aug 2018 12:12:48 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Wed, 01 Aug 2018 12:12:48 GMT
VOLUME [/var/lib/rabbitmq]
# Wed, 01 Aug 2018 12:12:49 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Wed, 01 Aug 2018 12:12:50 GMT
RUN ln -sf "/usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins" /plugins
# Wed, 01 Aug 2018 12:12:50 GMT
COPY file:4bd60cf2ba400c856bf3545d7f3e6b35c2df72b1f75e92caa21f75db37a7b574 in /usr/local/bin/ 
# Wed, 01 Aug 2018 12:12:51 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 01 Aug 2018 12:12:51 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 01 Aug 2018 12:12:51 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Wed, 01 Aug 2018 12:12:51 GMT
CMD ["rabbitmq-server"]
# Wed, 01 Aug 2018 12:12:59 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Wed, 01 Aug 2018 12:13:09 GMT
RUN set -eux; 	erl -noinput -eval ' 		{ ok, AdminBin } = zip:foldl(fun(FileInArchive, GetInfo, GetBin, Acc) -> 			case Acc of 				"" -> 					case lists:suffix("/rabbitmqadmin", FileInArchive) of 						true -> GetBin(); 						false -> Acc 					end; 				_ -> Acc 			end 		end, "", init:get_plain_arguments()), 		io:format("~s", [ AdminBin ]), 		init:stop(). 	' -- /plugins/rabbitmq_management-*.ez > /usr/local/bin/rabbitmqadmin; 	[ -s /usr/local/bin/rabbitmqadmin ]; 	chmod +x /usr/local/bin/rabbitmqadmin; 	apt-get update; 	apt-get install -y --no-install-recommends python; 	rm -rf /var/lib/apt/lists/*; 	rabbitmqadmin --version
# Wed, 01 Aug 2018 12:13:09 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:f27811d943553766d4449683ea06b6eac1147fe5de5663e94d39150eb2180735`  
		Last Modified: Tue, 17 Jul 2018 11:47:07 GMT  
		Size: 22.3 MB (22334517 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5fae6e372959464811b89164f9e8284f82a340c01d8efd4049bda9e28c38e662`  
		Last Modified: Tue, 17 Jul 2018 14:11:00 GMT  
		Size: 4.5 MB (4529974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eba72b34616c6f4ecf2f9d329b440ee84e8f0e35a360d9f36889986f606848a6`  
		Last Modified: Tue, 17 Jul 2018 14:10:58 GMT  
		Size: 4.1 KB (4074 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3f560719f3f368e7b9e6ce741800c6729189a3a330fad1ff957de908aa06e29`  
		Last Modified: Wed, 01 Aug 2018 12:15:53 GMT  
		Size: 937.9 KB (937911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67ee19f41cc3c56907d237e02c409a75047148a329262b48f7736eaf8596a514`  
		Last Modified: Wed, 01 Aug 2018 12:15:52 GMT  
		Size: 357.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ded37da555017b9185893e264bbd46adec94e8dce57ae4564ed33ea4eeeb8b4`  
		Last Modified: Wed, 01 Aug 2018 12:15:55 GMT  
		Size: 25.1 MB (25078759 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f9d5a8a50d50bb0f4d6788da48e1f8b7e6313023c4d179108b64dc7af4d6170`  
		Last Modified: Wed, 01 Aug 2018 12:15:53 GMT  
		Size: 10.3 MB (10312552 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aeb963a94d17a03e8015c4be51c6bdc99b7cfdd334a496972571563464b24466`  
		Last Modified: Wed, 01 Aug 2018 12:15:51 GMT  
		Size: 2.3 KB (2260 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50cc4d0657750bde395075a4cf0c5b87a2551a2d7df1d54870fe2f274e7d9eaa`  
		Last Modified: Wed, 01 Aug 2018 12:15:51 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a89e772da15f0a56210e360d75693ef2d675b398f433e2ddf06fa8baf3147b38`  
		Last Modified: Wed, 01 Aug 2018 12:15:51 GMT  
		Size: 124.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3e1b9d4a2a838fe11556ee4534991f69ae6e4d669812892770f0e58a0c52ce9`  
		Last Modified: Wed, 01 Aug 2018 12:15:51 GMT  
		Size: 4.2 KB (4181 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ca742728747d1cc4e4c246fdb12893deed20cdfdb2e2afc5a1296f36cc9b4f`  
		Last Modified: Wed, 01 Aug 2018 12:15:51 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:095e85b23cb20a34eb42c51447190d051c60c536bc33d5ed8de7b2555e7816ae`  
		Last Modified: Wed, 01 Aug 2018 12:16:22 GMT  
		Size: 192.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f2c6152040bd8d37b75b7674f26170e0216ec9dbc165f1f16fd8c9c1837c273`  
		Last Modified: Wed, 01 Aug 2018 12:16:24 GMT  
		Size: 7.6 MB (7595338 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
