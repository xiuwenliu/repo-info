## `kong:latest`

```console
$ docker pull kong@sha256:7663f791a32ba82713632d0d058ee90c671c1227e176213c2b0367d347a33e0f
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `kong:latest` - linux; amd64

```console
$ docker pull kong@sha256:3694a1a8cbf4ecd63a94a601688c4fab9826dada2e71a0008b1b10b695d87878
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **33.6 MB (33588648 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5d01475aa05df76a7ddbf9540ab034c4910ae782d006100c5241878d0c9380b0`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["kong","docker-start"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:25 GMT
ADD file:eceadb32d029164d23db918d14c88df7186b6ee9645fa2f0c0a7e3e046a6a129 in / 
# Fri, 06 Jul 2018 14:13:25 GMT
CMD ["/bin/sh"]
# Sat, 07 Jul 2018 03:44:49 GMT
LABEL maintainer=Marco Palladino, marco@mashape.com
# Wed, 22 Aug 2018 17:24:37 GMT
ENV KONG_VERSION=0.14.1
# Wed, 22 Aug 2018 17:24:38 GMT
ENV KONG_SHA256=e29937c5117ac2debcffe0d0016996dd5f0c516ef628f1edc029138715981387
# Wed, 22 Aug 2018 17:24:50 GMT
RUN apk add --no-cache --virtual .build-deps wget tar ca-certificates 	&& apk add --no-cache libgcc openssl pcre perl tzdata curl 	&& wget -O kong.tar.gz "https://bintray.com/kong/kong-community-edition-alpine-tar/download_file?file_path=kong-community-edition-$KONG_VERSION.apk.tar.gz" 	&& echo "$KONG_SHA256 *kong.tar.gz" | sha256sum -c - 	&& tar -xzf kong.tar.gz -C /tmp 	&& rm -f kong.tar.gz 	&& cp -R /tmp/usr / 	&& rm -rf /tmp/usr 	&& cp -R /tmp/etc / 	&& rm -rf /tmp/etc 	&& apk del .build-deps
# Wed, 22 Aug 2018 17:24:50 GMT
COPY file:e1ac3f3f858d8725b7a4bbe2a68d491ba6f524d0d6384516d5f0ce50d28b9fda in /docker-entrypoint.sh 
# Wed, 22 Aug 2018 17:24:51 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 22 Aug 2018 17:24:51 GMT
EXPOSE 8000/tcp 8001/tcp 8443/tcp 8444/tcp
# Wed, 22 Aug 2018 17:24:51 GMT
STOPSIGNAL [SIGTERM]
# Wed, 22 Aug 2018 17:24:51 GMT
CMD ["kong" "docker-start"]
```

-	Layers:
	-	`sha256:a073c86ecf9e0f29180e80e9638d4c741970695851ea48247276c32c57e40282`  
		Last Modified: Fri, 06 Jul 2018 14:16:26 GMT  
		Size: 2.0 MB (2014658 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23d58a465fc1aeee376a141d583da24569ea4d9cdb365fd60536c8f2c3bd4a7b`  
		Last Modified: Wed, 22 Aug 2018 17:26:48 GMT  
		Size: 31.6 MB (31573678 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ea073b984ed55a8ae611d1ad9c337ddb8ff1c029c5bc6d63ab50700d5507f2`  
		Last Modified: Wed, 22 Aug 2018 17:26:35 GMT  
		Size: 312.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
