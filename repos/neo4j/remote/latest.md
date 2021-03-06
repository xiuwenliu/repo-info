## `neo4j:latest`

```console
$ docker pull neo4j@sha256:1a388cc0121d383dc142a330bb09ec43f7c4e2835274bf9eeb7c6ca85fd7937e
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `neo4j:latest` - linux; amd64

```console
$ docker pull neo4j@sha256:0bbca48920d5314dd8907b3bdac284df627a23b80cfddd4c1044bc0d6c282d1a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **150.5 MB (150546661 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b7c61144de42e323addaf2edaac2a5afe2d7ff603665bfdff5e8e33224a0e7bd`
-	Entrypoint: `["\/sbin\/tini","-g","--","\/docker-entrypoint.sh"]`
-	Default Command: `["neo4j"]`

```dockerfile
# Fri, 06 Jul 2018 14:14:06 GMT
ADD file:25f61d70254b9807a40cd3e8d820f6a5ec0e1e596de04e325f6a33810393e95a in / 
# Fri, 06 Jul 2018 14:14:06 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 00:34:53 GMT
ENV LANG=C.UTF-8
# Wed, 11 Jul 2018 00:34:54 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 11 Jul 2018 00:35:25 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk/jre
# Wed, 11 Jul 2018 00:35:25 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 11 Jul 2018 00:35:25 GMT
ENV JAVA_VERSION=8u171
# Wed, 11 Jul 2018 00:35:25 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 11 Jul 2018 00:35:30 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8-jre="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 11 Jul 2018 02:08:32 GMT
RUN addgroup -S neo4j && adduser -S -H -h /var/lib/neo4j -G neo4j neo4j
# Wed, 22 Aug 2018 20:03:36 GMT
ENV NEO4J_SHA256=8302c45ba4efa14ee5019120a6dd9f8cd1ff61c2b6b0012e7dfebe73b5207e2d NEO4J_TARBALL=neo4j-community-3.4.6-unix.tar.gz NEO4J_EDITION=community
# Wed, 22 Aug 2018 20:03:36 GMT
ARG NEO4J_URI=http://dist.neo4j.org/neo4j-community-3.4.6-unix.tar.gz
# Wed, 22 Aug 2018 20:03:36 GMT
COPY file:2e411d607fa15f91ae6f4b515dde6bf3e158d34c0036556e00553ed1c50cd63d in /tmp/ 
# Wed, 22 Aug 2018 20:09:11 GMT
# ARGS: NEO4J_URI=http://dist.neo4j.org/neo4j-community-3.4.6-unix.tar.gz
RUN apk add --no-cache --quiet     bash     curl     tini     su-exec     && curl --fail --silent --show-error --location --remote-name ${NEO4J_URI}     && echo "${NEO4J_SHA256}  ${NEO4J_TARBALL}" | sha256sum -csw -     && tar --extract --file ${NEO4J_TARBALL} --directory /var/lib     && mv /var/lib/neo4j-* /var/lib/neo4j     && rm ${NEO4J_TARBALL}     && mv /var/lib/neo4j/data /data     && chown -R neo4j:neo4j /data     && chmod -R 777 /data     && chown -R neo4j:neo4j /var/lib/neo4j     && chmod -R 777 /var/lib/neo4j     && ln -s /data /var/lib/neo4j/data     && apk del curl
# Wed, 22 Aug 2018 20:09:11 GMT
ENV PATH=/var/lib/neo4j/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 22 Aug 2018 20:09:12 GMT
WORKDIR /var/lib/neo4j
# Wed, 22 Aug 2018 20:09:12 GMT
VOLUME [/data]
# Wed, 22 Aug 2018 20:09:13 GMT
COPY file:603d5e7c50609263b4aac8c7285d2a3c8bfe2a39a24083aa5800e14bcc944c16 in /docker-entrypoint.sh 
# Wed, 22 Aug 2018 20:09:13 GMT
EXPOSE 7473/tcp 7474/tcp 7687/tcp
# Wed, 22 Aug 2018 20:09:14 GMT
ENTRYPOINT ["/sbin/tini" "-g" "--" "/docker-entrypoint.sh"]
# Wed, 22 Aug 2018 20:09:14 GMT
CMD ["neo4j"]
```

-	Layers:
	-	`sha256:8e3ba11ec2a2b39ab372c60c16b421536e50e5ce64a0bc81765c2e38381bcff6`  
		Last Modified: Fri, 06 Jul 2018 04:15:58 GMT  
		Size: 2.2 MB (2206542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:311ad0da45338842480bf25c6e6b7bb133b7b8cf709c3470db171ec370da5539`  
		Last Modified: Wed, 11 Jul 2018 00:37:45 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:391a6a6b36513d84d55cbbe7e13bca7e92fbf257d910a5255f2b7bc9fcff4edf`  
		Last Modified: Wed, 11 Jul 2018 00:41:21 GMT  
		Size: 54.8 MB (54798327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:20fac75f39cd3eb7e5ef0c61b4419d86b6403900ed89032041155a08ff846f0a`  
		Last Modified: Wed, 11 Jul 2018 02:59:41 GMT  
		Size: 1.2 KB (1205 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:58e742f66438314b82fd70e8ed3b5b2a522d9f754c26958d994410005df788db`  
		Last Modified: Wed, 22 Aug 2018 20:17:41 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1000930f4022339c10bf75df985c17ddc2301add23b0a8db8ff64b79318addb3`  
		Last Modified: Wed, 22 Aug 2018 20:17:56 GMT  
		Size: 93.5 MB (93537229 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0fb868efa8364e7370c46429c534702a188ea3c7d181c34e913caa632932dd7b`  
		Last Modified: Wed, 22 Aug 2018 20:17:41 GMT  
		Size: 3.0 KB (2988 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
