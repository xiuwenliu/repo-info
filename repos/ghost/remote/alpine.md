## `ghost:alpine`

```console
$ docker pull ghost@sha256:6c89a953a1d01b9af6c41fcff7cfe771589929d9d3b1d80e1e5cce38f75b861b
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; ppc64le

### `ghost:alpine` - linux; amd64

```console
$ docker pull ghost@sha256:60acd65c2bfedee78bf055c77aab38a510686c27d2a5875af6b7d4eb727ab838
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **144.4 MB (144374902 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:efe90b4923529b70bd886af45866be9e8949a4e4af75b23cdd81618e1d7472a4`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["node","current\/index.js"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:25 GMT
ADD file:eceadb32d029164d23db918d14c88df7186b6ee9645fa2f0c0a7e3e046a6a129 in / 
# Fri, 06 Jul 2018 14:13:25 GMT
CMD ["/bin/sh"]
# Thu, 16 Aug 2018 06:01:48 GMT
ENV NODE_VERSION=8.11.4
# Thu, 16 Aug 2018 06:10:05 GMT
RUN addgroup -g 1000 node     && adduser -u 1000 -G node -s /bin/sh -D node     && apk add --no-cache         libstdc++     && apk add --no-cache --virtual .build-deps         binutils-gold         curl         g++         gcc         gnupg         libgcc         linux-headers         make         python   && for key in     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     B9AE9905FFD7803F25714661B63B535A4C206CA9     56730D5401028683275BD23C23EFEFE93C4CFFFE     77984A986EBC2AA786BC0F66B01FBB92821C587A     8FCCA13FEF1D0C2E91008E09770F7A9A5AE15600   ; do     gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys "$key" ||     gpg --keyserver hkp://ipv4.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver hkp://pgp.mit.edu:80 --recv-keys "$key" ;   done     && curl -fsSLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION.tar.xz"     && curl -fsSLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xf "node-v$NODE_VERSION.tar.xz"     && cd "node-v$NODE_VERSION"     && ./configure     && make -j$(getconf _NPROCESSORS_ONLN)     && make install     && apk del .build-deps     && cd ..     && rm -Rf "node-v$NODE_VERSION"     && rm "node-v$NODE_VERSION.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt
# Thu, 16 Aug 2018 06:10:05 GMT
ENV YARN_VERSION=1.6.0
# Thu, 16 Aug 2018 06:10:12 GMT
RUN apk add --no-cache --virtual .build-deps-yarn curl gnupg tar   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys "$key" ||     gpg --keyserver hkp://ipv4.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver hkp://pgp.mit.edu:80 --recv-keys "$key" ;   done   && curl -fsSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz"   && curl -fsSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz.asc"   && gpg --batch --verify yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && mkdir -p /opt   && tar -xzf yarn-v$YARN_VERSION.tar.gz -C /opt/   && ln -s /opt/yarn-v$YARN_VERSION/bin/yarn /usr/local/bin/yarn   && ln -s /opt/yarn-v$YARN_VERSION/bin/yarnpkg /usr/local/bin/yarnpkg   && rm yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && apk del .build-deps-yarn
# Thu, 16 Aug 2018 06:10:12 GMT
CMD ["node"]
# Thu, 16 Aug 2018 07:24:59 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Thu, 16 Aug 2018 07:25:01 GMT
RUN apk add --no-cache 		bash
# Thu, 16 Aug 2018 07:25:17 GMT
ENV NODE_ENV=production
# Wed, 22 Aug 2018 22:39:28 GMT
ENV GHOST_CLI_VERSION=1.9.1
# Wed, 22 Aug 2018 22:39:49 GMT
RUN npm install -g "ghost-cli@$GHOST_CLI_VERSION"
# Wed, 22 Aug 2018 22:39:50 GMT
ENV GHOST_INSTALL=/var/lib/ghost
# Wed, 22 Aug 2018 22:39:50 GMT
ENV GHOST_CONTENT=/var/lib/ghost/content
# Wed, 22 Aug 2018 22:39:50 GMT
ENV GHOST_VERSION=2.0.3
# Wed, 22 Aug 2018 22:40:33 GMT
RUN set -ex; 	mkdir -p "$GHOST_INSTALL"; 	chown node:node "$GHOST_INSTALL"; 		su-exec node ghost install "$GHOST_VERSION" --db sqlite3 --no-prompt --no-stack --no-setup --dir "$GHOST_INSTALL"; 		cd "$GHOST_INSTALL"; 	su-exec node ghost config --ip 0.0.0.0 --port 2368 --no-prompt --db sqlite3 --url http://localhost:2368 --dbpath "$GHOST_CONTENT/data/ghost.db"; 	su-exec node ghost config paths.contentPath "$GHOST_CONTENT"; 		su-exec node ln -s config.production.json "$GHOST_INSTALL/config.development.json"; 	readlink -f "$GHOST_INSTALL/config.development.json"; 		mv "$GHOST_CONTENT" "$GHOST_INSTALL/content.orig"; 	mkdir -p "$GHOST_CONTENT"; 	chown node:node "$GHOST_CONTENT"
# Wed, 22 Aug 2018 22:40:38 GMT
WORKDIR /var/lib/ghost
# Wed, 22 Aug 2018 22:40:39 GMT
VOLUME [/var/lib/ghost/content]
# Wed, 22 Aug 2018 22:40:39 GMT
COPY file:984b6359fb5468bd755c750256f62662bb2d19b1b40771579aca645181832f7f in /usr/local/bin 
# Wed, 22 Aug 2018 22:40:40 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 22 Aug 2018 22:40:40 GMT
EXPOSE 2368/tcp
# Wed, 22 Aug 2018 22:40:40 GMT
CMD ["node" "current/index.js"]
```

-	Layers:
	-	`sha256:a073c86ecf9e0f29180e80e9638d4c741970695851ea48247276c32c57e40282`  
		Last Modified: Fri, 06 Jul 2018 14:16:26 GMT  
		Size: 2.0 MB (2014658 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ceac54409f6a264ea4cd419d42e64c8f7e1066d73ed1d248ecbda655681e764`  
		Last Modified: Thu, 16 Aug 2018 06:44:29 GMT  
		Size: 19.6 MB (19645919 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bbff16e8e4d524a69deb2ed73ab90bc946e74a249a1351fbc484b1a8c02f24d7`  
		Last Modified: Thu, 16 Aug 2018 06:44:21 GMT  
		Size: 1.1 MB (1079824 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:867ab723709984ad588917be73b0cb812455a6c0e09c471d5bb767c0e5230d75`  
		Last Modified: Thu, 16 Aug 2018 07:33:50 GMT  
		Size: 8.8 KB (8803 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84b5da2f9e2f48a6a0eee0c94a742adb326b0f8553eccae6cd33c5c673b2a953`  
		Last Modified: Thu, 16 Aug 2018 07:33:50 GMT  
		Size: 1.1 MB (1116785 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4072f80b60d0869dffccb3c256aa18bba841a43dcbc07d84346954b793b12a54`  
		Last Modified: Wed, 22 Aug 2018 22:46:38 GMT  
		Size: 17.9 MB (17867347 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:27e1a44f1529fbf5dcc42b0c6215ea0be8047b4773bfefc8ba13614096f32258`  
		Last Modified: Wed, 22 Aug 2018 22:47:04 GMT  
		Size: 102.6 MB (102641039 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:863c079ac1aaff26b7d257f2560f9741d8609e59829e065d10721e33cf41767a`  
		Last Modified: Wed, 22 Aug 2018 22:46:29 GMT  
		Size: 527.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ghost:alpine` - linux; ppc64le

```console
$ docker pull ghost@sha256:da2529e5259ee2c2fab397cf61fb7e4ec9f84ac7228a26ba59b4f451206b20b5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **136.8 MB (136845676 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dbf32613540dd9ec880d3d74d880f04b427fb9733b89ecdb9c4b30d1795e216f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["node","current\/index.js"]`

```dockerfile
# Wed, 25 Oct 2017 23:28:47 GMT
ADD file:e0be8616517d68cb80a2f9b74eb967cda22b9937bbcbe8b75b6153815a6f7761 in / 
# Wed, 25 Oct 2017 23:28:48 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Wed, 25 Oct 2017 23:28:50 GMT
CMD ["/bin/sh"]
# Thu, 16 Aug 2018 06:06:47 GMT
ENV NODE_VERSION=8.11.4
# Thu, 16 Aug 2018 06:16:46 GMT
RUN addgroup -g 1000 node     && adduser -u 1000 -G node -s /bin/sh -D node     && apk add --no-cache         libstdc++     && apk add --no-cache --virtual .build-deps         binutils-gold         curl         g++         gcc         gnupg         libgcc         linux-headers         make         python   && for key in     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     B9AE9905FFD7803F25714661B63B535A4C206CA9     56730D5401028683275BD23C23EFEFE93C4CFFFE     77984A986EBC2AA786BC0F66B01FBB92821C587A     8FCCA13FEF1D0C2E91008E09770F7A9A5AE15600   ; do     gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys "$key" ||     gpg --keyserver hkp://ipv4.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver hkp://pgp.mit.edu:80 --recv-keys "$key" ;   done     && curl -fsSLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION.tar.xz"     && curl -fsSLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xf "node-v$NODE_VERSION.tar.xz"     && cd "node-v$NODE_VERSION"     && ./configure     && make -j$(getconf _NPROCESSORS_ONLN)     && make install     && apk del .build-deps     && cd ..     && rm -Rf "node-v$NODE_VERSION"     && rm "node-v$NODE_VERSION.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt
# Thu, 16 Aug 2018 06:16:47 GMT
ENV YARN_VERSION=1.6.0
# Thu, 16 Aug 2018 06:17:04 GMT
RUN apk add --no-cache --virtual .build-deps-yarn curl gnupg tar   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys "$key" ||     gpg --keyserver hkp://ipv4.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver hkp://pgp.mit.edu:80 --recv-keys "$key" ;   done   && curl -fsSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz"   && curl -fsSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz.asc"   && gpg --batch --verify yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && mkdir -p /opt   && tar -xzf yarn-v$YARN_VERSION.tar.gz -C /opt/   && ln -s /opt/yarn-v$YARN_VERSION/bin/yarn /usr/local/bin/yarn   && ln -s /opt/yarn-v$YARN_VERSION/bin/yarnpkg /usr/local/bin/yarnpkg   && rm yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && apk del .build-deps-yarn
# Thu, 16 Aug 2018 06:17:06 GMT
CMD ["node"]
# Thu, 16 Aug 2018 07:20:58 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Thu, 16 Aug 2018 07:21:03 GMT
RUN apk add --no-cache 		bash
# Thu, 16 Aug 2018 07:21:03 GMT
ENV NODE_ENV=production
# Thu, 23 Aug 2018 08:22:55 GMT
ENV GHOST_CLI_VERSION=1.9.1
# Thu, 23 Aug 2018 08:23:38 GMT
RUN npm install -g "ghost-cli@$GHOST_CLI_VERSION"
# Thu, 23 Aug 2018 08:23:39 GMT
ENV GHOST_INSTALL=/var/lib/ghost
# Thu, 23 Aug 2018 08:23:40 GMT
ENV GHOST_CONTENT=/var/lib/ghost/content
# Thu, 23 Aug 2018 08:23:42 GMT
ENV GHOST_VERSION=2.0.3
# Thu, 23 Aug 2018 08:29:12 GMT
RUN set -ex; 	mkdir -p "$GHOST_INSTALL"; 	chown node:node "$GHOST_INSTALL"; 		su-exec node ghost install "$GHOST_VERSION" --db sqlite3 --no-prompt --no-stack --no-setup --dir "$GHOST_INSTALL"; 		cd "$GHOST_INSTALL"; 	su-exec node ghost config --ip 0.0.0.0 --port 2368 --no-prompt --db sqlite3 --url http://localhost:2368 --dbpath "$GHOST_CONTENT/data/ghost.db"; 	su-exec node ghost config paths.contentPath "$GHOST_CONTENT"; 		su-exec node ln -s config.production.json "$GHOST_INSTALL/config.development.json"; 	readlink -f "$GHOST_INSTALL/config.development.json"; 		mv "$GHOST_CONTENT" "$GHOST_INSTALL/content.orig"; 	mkdir -p "$GHOST_CONTENT"; 	chown node:node "$GHOST_CONTENT"
# Thu, 23 Aug 2018 08:29:41 GMT
WORKDIR /var/lib/ghost
# Thu, 23 Aug 2018 08:29:41 GMT
VOLUME [/var/lib/ghost/content]
# Thu, 23 Aug 2018 08:29:43 GMT
COPY file:984b6359fb5468bd755c750256f62662bb2d19b1b40771579aca645181832f7f in /usr/local/bin 
# Thu, 23 Aug 2018 08:29:43 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 23 Aug 2018 08:29:45 GMT
EXPOSE 2368/tcp
# Thu, 23 Aug 2018 08:29:46 GMT
CMD ["node" "current/index.js"]
```

-	Layers:
	-	`sha256:1e52418956f7d2a8ea35e8e6e3318fd08e005b27457d77868c225e7433bbfa02`  
		Last Modified: Thu, 20 Jul 2017 15:12:59 GMT  
		Size: 2.0 MB (2008578 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:acf472f4e5bb7956ac20bb343b304e1d3de1f79160c0d158cccbe25980022d50`  
		Last Modified: Wed, 25 Oct 2017 23:29:11 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ddad60f8be4d1b391a8252ccfe09e268a31d6a78487411c7b56fd2d6d28fc9c`  
		Last Modified: Thu, 16 Aug 2018 06:53:58 GMT  
		Size: 19.8 MB (19844929 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36ee5d60da1d0b595662ba544ab35d0d298c65d815b0b33ef6ae7eda1ebd4ead`  
		Last Modified: Thu, 16 Aug 2018 06:53:39 GMT  
		Size: 1.1 MB (1080151 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0e71acfa6e6d249db81dd662101ef85aca2c944d467928ebc10fc813d6cd435`  
		Last Modified: Thu, 16 Aug 2018 07:29:14 GMT  
		Size: 9.4 KB (9409 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f6630e2b0420249fbc17bb6ad75ba89ff5297921030f458489210fa52daf7cd`  
		Last Modified: Thu, 16 Aug 2018 07:29:21 GMT  
		Size: 1.1 MB (1106143 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:457f95aa82efeb1cc315d23d99d3c860e9707454de937b4ab98fd557a8a288f3`  
		Last Modified: Thu, 23 Aug 2018 08:40:48 GMT  
		Size: 17.9 MB (17868746 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85db63f0649843ca18f328a9faa5883671910674f4fcfab2cc485bfefe807208`  
		Last Modified: Thu, 23 Aug 2018 08:41:31 GMT  
		Size: 94.9 MB (94927018 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:137bbd5419b1b1e9f6bd8b6d45f3d00e881b205634140e96d09349e8ffb34c11`  
		Last Modified: Thu, 23 Aug 2018 08:40:11 GMT  
		Size: 526.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
