## `open-liberty:springBoot1-java8-ibm`

```console
$ docker pull open-liberty@sha256:0a883854e024dbeb740e60e57f0147af485c97de2183f7c5440d864406545033
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `open-liberty:springBoot1-java8-ibm` - linux; amd64

```console
$ docker pull open-liberty@sha256:d3654bb1212a52448ff56de10f5602aee62ee967fe9b4e5a7a70ac36b2d7e030
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **303.2 MB (303249386 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:418eebec0b43d03ecf107ade70a334f2c4eef6d709778e02c2db183763e9e707`
-	Entrypoint: `["\/opt\/ol\/docker\/docker-server"]`
-	Default Command: `["\/opt\/ol\/wlp\/bin\/server","run","defaultServer"]`

```dockerfile
# Wed, 22 Aug 2018 17:31:28 GMT
ADD file:a83ab1826f43e88bc0d3ab6230f14cb9b2dacab70c762c3bfc555eda733b292c in / 
# Wed, 22 Aug 2018 17:31:29 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 22 Aug 2018 17:31:30 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 17:31:31 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 22 Aug 2018 17:31:32 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 22 Aug 2018 17:31:32 GMT
CMD ["/bin/bash"]
# Wed, 22 Aug 2018 18:57:37 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Wed, 22 Aug 2018 18:57:51 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 18:57:51 GMT
ENV JAVA_VERSION=1.8.0_sr5fp20
# Wed, 22 Aug 2018 18:58:42 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='b2dfbdac0fda3fd8ecea6d9d145da7d6f9fa79fe5cfc13dd3862fc331b8698de';          YML_FILE='jre/linux/x86_64/index.yml';          ;;        i386)          ESUM='b4f525b885ca369b1ab626d552e3ed74f5c6ccc674fcaf5340ecbd9aa046c1eb';          YML_FILE='jre/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='bf824a43250b64a85f86e43ee75543de235a4e768f5cc540d4e8b0f4fae2ff18';          YML_FILE='jre/linux/ppc64le/index.yml';          ;;        s390)          ESUM='f216bf12f094e48c3bf05a45d27669f047670e734d4be3f4015257d42a6b1990';          YML_FILE='jre/linux/s390/index.yml';          ;;        s390x)          ESUM='24acc20c2487f2e3a3246c86a10b90b0d7ce6121d923bd7405a1c53e119094ac';          YML_FILE='jre/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(sed -n '/^'${JAVA_VERSION}:'/{n;s/\s*uri:\s//p}'< /tmp/index.yml);     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Wed, 22 Aug 2018 18:58:42 GMT
ENV JAVA_HOME=/opt/ibm/java/jre PATH=/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin IBM_JAVA_OPTIONS=-XX:+UseContainerSupport
# Wed, 22 Aug 2018 21:44:33 GMT
LABEL maintainer=Alasdair Nottingham vendor=Open Liberty url=https://openliberty.io/ github=https://github.com/OpenLiberty/ci.docker
# Wed, 22 Aug 2018 21:44:33 GMT
COPY file:a6eac68a3be2db3229be20bb825e70a7a1e5f32d189da5168ed4f2fe9c9b96fc in /opt/ol/docker/ 
# Wed, 22 Aug 2018 21:47:02 GMT
ENV LIBERTY_VERSION=18.0.0.2 LIBERTY_SHA=4170e609e1e4189e75a57bcc0e65a972e9c9ef6e
# Wed, 22 Aug 2018 21:47:17 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends unzip     && rm -rf /var/lib/apt/lists/*     && wget https://repo1.maven.org/maven2/io/openliberty/openliberty-runtime/$LIBERTY_VERSION/openliberty-runtime-$LIBERTY_VERSION.zip -U UA-Open-Liberty-Docker -O /tmp/wlp.zip     && echo "$LIBERTY_SHA  /tmp/wlp.zip" > /tmp/wlp.zip.sha1     && sha1sum -c /tmp/wlp.zip.sha1     && unzip -q /tmp/wlp.zip -d /opt/ol     && rm /tmp/wlp.zip     && rm /tmp/wlp.zip.sha1     && apt-get remove -y unzip     && rm -rf /var/lib/apt/lists/*
# Wed, 22 Aug 2018 21:47:18 GMT
ENV PATH=/opt/ol/wlp/bin:/opt/ol/docker/:/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin LOG_DIR=/logs WLP_OUTPUT_DIR=/opt/ol/wlp/output WLP_SKIP_MAXPERMSIZE=true
# Wed, 22 Aug 2018 21:47:19 GMT
RUN mkdir /logs     && mkdir -p $WLP_OUTPUT_DIR/defaultServer     && ln -s $WLP_OUTPUT_DIR/defaultServer /output     && ln -s /opt/ol/wlp/usr/servers/defaultServer /config     && ln -s /logs $WLP_OUTPUT_DIR/defaultServer/logs     && ln -s /liberty /opt/ol/wlp
# Wed, 22 Aug 2018 21:47:21 GMT
RUN /opt/ol/wlp/bin/server create     && rm /config/server.env     && rm -rf $WLP_OUTPUT_DIR/.classCache /output/workarea     && mkdir /config/configDropins     && mkdir /config/configDropins/defaults     && echo "<server description=\"Default Server\"><httpEndpoint id=\"defaultHttpEndpoint\" host=\"*\" /></server>" > /config/configDropins/defaults/open-default-port.xml
# Wed, 22 Aug 2018 21:47:21 GMT
EXPOSE 9080/tcp 9443/tcp
# Wed, 22 Aug 2018 21:47:21 GMT
ENTRYPOINT ["/opt/ol/docker/docker-server"]
# Wed, 22 Aug 2018 21:47:22 GMT
CMD ["/opt/ol/wlp/bin/server" "run" "defaultServer"]
# Wed, 22 Aug 2018 21:49:00 GMT
RUN mkdir -p /opt/ol/wlp/usr/shared/resources/lib.index.cache   && ln -s /opt/ol/wlp/usr/shared/resources/lib.index.cache /lib.index.cache
# Wed, 22 Aug 2018 21:49:00 GMT
COPY file:01d87f11d05fde398ec003f0aeae67fd944b6f2f7ca7d69b7d29cac22e0318e7 in /config/ 
# Wed, 22 Aug 2018 21:49:10 GMT
RUN /opt/ol/wlp/bin/server start && /opt/ol/wlp/bin/server stop && rm -rf /output/resources/security/
```

-	Layers:
	-	`sha256:3b37166ec61459e76e33282dda08f2a9cd698ca7e3d6bc44e6a6e7580cdeff8e`  
		Last Modified: Fri, 10 Aug 2018 22:11:36 GMT  
		Size: 43.3 MB (43252507 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba077e1ddb3aa8b95b2ecc5e58830800af4f5c06a5a37a3b7d7e0a67e178fb65`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34c83d2bc656952f573cee825d42e58622909b4be524b653f4f3df7464e57aa2`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 616.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84b69b6e47437924b207458fe7fc8f66812622983ae5a5d84bfdd2d83a9581e1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f72e97e1f61face716660657e4df5f70c2008a0b8b89e35dc6a460124fe01d1`  
		Last Modified: Wed, 22 Aug 2018 17:37:07 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6bd364eda0c79e5d78fe6142f70cfad2fbe6b2bda2f638c58b17d696ae6a41a`  
		Last Modified: Wed, 22 Aug 2018 19:02:02 GMT  
		Size: 3.0 MB (3020696 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:afd16121031d9097441efa2f72a549cfa7d12ac262e3c60515f8b0dc6a900480`  
		Last Modified: Wed, 22 Aug 2018 19:02:25 GMT  
		Size: 127.7 MB (127680818 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee00c67dca7e88f085f88d9a3ef2e6bb17b379fe373d345921bcf706fd8df3e1`  
		Last Modified: Wed, 22 Aug 2018 21:51:01 GMT  
		Size: 403.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c355d73aac0c577a7de2a5bf589cc1f5d466e5e7ae37e1257c6a4ee607a57802`  
		Last Modified: Wed, 22 Aug 2018 21:53:33 GMT  
		Size: 121.1 MB (121067610 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eed806ceef6663883e8bb1308b4f6fcf0c0537fcd4f64f037221a4e8ce1ad9af`  
		Last Modified: Wed, 22 Aug 2018 21:53:18 GMT  
		Size: 299.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9e14d9130f1c69c4bfed0d274f4fe9b1821929f2152321b4208dc488797ecc2`  
		Last Modified: Wed, 22 Aug 2018 21:53:18 GMT  
		Size: 807.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c931768878ce89bc42a92b228d15af9de46e4cb54ac656e4dc7314ce0c22957`  
		Last Modified: Wed, 22 Aug 2018 21:55:48 GMT  
		Size: 254.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:16ad082e131177120bbf02ab3c540112b8941a665d86fd0877b47f7635625666`  
		Last Modified: Wed, 22 Aug 2018 21:55:48 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:884f2728062ec049199b9b2b22744f6fd7e7c65b8db56fcda90cd65b2494cd3e`  
		Last Modified: Wed, 22 Aug 2018 21:55:52 GMT  
		Size: 8.2 MB (8222972 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `open-liberty:springBoot1-java8-ibm` - linux; 386

```console
$ docker pull open-liberty@sha256:789753242eb0bee64cdfca6e4be616932683154fdbaf6fadeb125854cecc1438
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **291.8 MB (291822993 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:cc43e12a7eb14ebab7ea48dd68f227aed7d25dcc5df14434e9459db5411eeb36`
-	Entrypoint: `["\/opt\/ol\/docker\/docker-server"]`
-	Default Command: `["\/opt\/ol\/wlp\/bin\/server","run","defaultServer"]`

```dockerfile
# Thu, 23 Aug 2018 15:55:56 GMT
ADD file:34ab8be3f140b862a66eb9106c2481df8aea201a24262ef4b529cfe572f6097c in / 
# Thu, 23 Aug 2018 15:56:06 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 15:56:07 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 15:56:07 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 15:56:08 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 15:56:08 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 18:41:34 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Thu, 23 Aug 2018 18:42:01 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 18:42:08 GMT
ENV JAVA_VERSION=1.8.0_sr5fp20
# Thu, 23 Aug 2018 18:43:01 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='b2dfbdac0fda3fd8ecea6d9d145da7d6f9fa79fe5cfc13dd3862fc331b8698de';          YML_FILE='jre/linux/x86_64/index.yml';          ;;        i386)          ESUM='b4f525b885ca369b1ab626d552e3ed74f5c6ccc674fcaf5340ecbd9aa046c1eb';          YML_FILE='jre/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='bf824a43250b64a85f86e43ee75543de235a4e768f5cc540d4e8b0f4fae2ff18';          YML_FILE='jre/linux/ppc64le/index.yml';          ;;        s390)          ESUM='f216bf12f094e48c3bf05a45d27669f047670e734d4be3f4015257d42a6b1990';          YML_FILE='jre/linux/s390/index.yml';          ;;        s390x)          ESUM='24acc20c2487f2e3a3246c86a10b90b0d7ce6121d923bd7405a1c53e119094ac';          YML_FILE='jre/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(sed -n '/^'${JAVA_VERSION}:'/{n;s/\s*uri:\s//p}'< /tmp/index.yml);     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Thu, 23 Aug 2018 18:43:01 GMT
ENV JAVA_HOME=/opt/ibm/java/jre PATH=/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin IBM_JAVA_OPTIONS=-XX:+UseContainerSupport
# Thu, 23 Aug 2018 19:06:51 GMT
LABEL maintainer=Alasdair Nottingham vendor=Open Liberty url=https://openliberty.io/ github=https://github.com/OpenLiberty/ci.docker
# Thu, 23 Aug 2018 19:06:51 GMT
COPY file:a6eac68a3be2db3229be20bb825e70a7a1e5f32d189da5168ed4f2fe9c9b96fc in /opt/ol/docker/ 
# Thu, 23 Aug 2018 19:09:06 GMT
ENV LIBERTY_VERSION=18.0.0.2 LIBERTY_SHA=4170e609e1e4189e75a57bcc0e65a972e9c9ef6e
# Thu, 23 Aug 2018 19:09:33 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends unzip     && rm -rf /var/lib/apt/lists/*     && wget https://repo1.maven.org/maven2/io/openliberty/openliberty-runtime/$LIBERTY_VERSION/openliberty-runtime-$LIBERTY_VERSION.zip -U UA-Open-Liberty-Docker -O /tmp/wlp.zip     && echo "$LIBERTY_SHA  /tmp/wlp.zip" > /tmp/wlp.zip.sha1     && sha1sum -c /tmp/wlp.zip.sha1     && unzip -q /tmp/wlp.zip -d /opt/ol     && rm /tmp/wlp.zip     && rm /tmp/wlp.zip.sha1     && apt-get remove -y unzip     && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 19:09:33 GMT
ENV PATH=/opt/ol/wlp/bin:/opt/ol/docker/:/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin LOG_DIR=/logs WLP_OUTPUT_DIR=/opt/ol/wlp/output WLP_SKIP_MAXPERMSIZE=true
# Thu, 23 Aug 2018 19:09:34 GMT
RUN mkdir /logs     && mkdir -p $WLP_OUTPUT_DIR/defaultServer     && ln -s $WLP_OUTPUT_DIR/defaultServer /output     && ln -s /opt/ol/wlp/usr/servers/defaultServer /config     && ln -s /logs $WLP_OUTPUT_DIR/defaultServer/logs     && ln -s /liberty /opt/ol/wlp
# Thu, 23 Aug 2018 19:09:36 GMT
RUN /opt/ol/wlp/bin/server create     && rm /config/server.env     && rm -rf $WLP_OUTPUT_DIR/.classCache /output/workarea     && mkdir /config/configDropins     && mkdir /config/configDropins/defaults     && echo "<server description=\"Default Server\"><httpEndpoint id=\"defaultHttpEndpoint\" host=\"*\" /></server>" > /config/configDropins/defaults/open-default-port.xml
# Thu, 23 Aug 2018 19:09:36 GMT
EXPOSE 9080/tcp 9443/tcp
# Thu, 23 Aug 2018 19:09:37 GMT
ENTRYPOINT ["/opt/ol/docker/docker-server"]
# Thu, 23 Aug 2018 19:09:37 GMT
CMD ["/opt/ol/wlp/bin/server" "run" "defaultServer"]
# Thu, 23 Aug 2018 19:11:15 GMT
RUN mkdir -p /opt/ol/wlp/usr/shared/resources/lib.index.cache   && ln -s /opt/ol/wlp/usr/shared/resources/lib.index.cache /lib.index.cache
# Thu, 23 Aug 2018 19:11:16 GMT
COPY file:01d87f11d05fde398ec003f0aeae67fd944b6f2f7ca7d69b7d29cac22e0318e7 in /config/ 
# Thu, 23 Aug 2018 19:11:29 GMT
RUN /opt/ol/wlp/bin/server start && /opt/ol/wlp/bin/server stop && rm -rf /output/resources/security/
```

-	Layers:
	-	`sha256:bd73c3089e08f76ef90cd0566c48e478d1a546126ac8b4155a9eb771001e4a41`  
		Last Modified: Thu, 23 Aug 2018 16:04:02 GMT  
		Size: 43.5 MB (43519933 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:908456bb100430678c2f5d49c9c216260c4b5dfe745a94c1ed92fe97b1a01771`  
		Last Modified: Thu, 23 Aug 2018 16:03:45 GMT  
		Size: 850.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7186622ef44de7a2bec81893dfaf016b9b50afe37edabe298892670046190fec`  
		Last Modified: Thu, 23 Aug 2018 16:03:45 GMT  
		Size: 581.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71f510d815c12855dc5ea55f5d264ac661d788831749d8c17e18e556e3cf6096`  
		Last Modified: Thu, 23 Aug 2018 16:03:45 GMT  
		Size: 849.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:832e211bdcc20115eb5109160072716547977bdfedbe96cc7887a0d0c4b65551`  
		Last Modified: Thu, 23 Aug 2018 16:03:45 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4245881f6189f4db2e8226c189c225079595810cd8a0018f86acb80374c519a6`  
		Last Modified: Thu, 23 Aug 2018 18:46:37 GMT  
		Size: 2.9 MB (2875840 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd24cb338aea5df1fbe8e642fa03f9a544b9d16eb289fe7393d41922c3aa2372`  
		Last Modified: Thu, 23 Aug 2018 18:46:58 GMT  
		Size: 115.8 MB (115826032 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a51e13f49244533ebbcdf303720061024e2838f87304fa4aba2854a81551c33`  
		Last Modified: Thu, 23 Aug 2018 19:13:24 GMT  
		Size: 404.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c02b9539e77858b1f7358aa2e8b13b350706f3c5508957187242fedd55a32c48`  
		Last Modified: Thu, 23 Aug 2018 19:16:27 GMT  
		Size: 121.1 MB (121067499 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d10c96bed7c0f91451c758aedf2852d5a9293d8db9e059067960658c356056fa`  
		Last Modified: Thu, 23 Aug 2018 19:16:12 GMT  
		Size: 301.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a2c928d121c667e6f4fde780745fa1936368b3fa4947ea6e84fc7659d1b68891`  
		Last Modified: Thu, 23 Aug 2018 19:16:12 GMT  
		Size: 813.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5062ee6a2959168476a1cc4627a43b894d0323765b2d4e4adcc13d37f98282b4`  
		Last Modified: Thu, 23 Aug 2018 19:18:55 GMT  
		Size: 256.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dbc2bd330a3ebf29df8a0ffebdc3e9634ff1ef1e78a7ac7e47203ebe86f451a5`  
		Last Modified: Thu, 23 Aug 2018 19:18:56 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:791e20edc9b7d2ae64e3a545939a0b0a5fabca68ab9706f202e3a98a39455a56`  
		Last Modified: Thu, 23 Aug 2018 19:19:00 GMT  
		Size: 8.5 MB (8528930 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `open-liberty:springBoot1-java8-ibm` - linux; ppc64le

```console
$ docker pull open-liberty@sha256:e12be9fd6d0e97b149df33434c72c7f268d0879d080b4ed32af156397fa059cc
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **318.8 MB (318766624 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ae2b59f11a9b68f28e3f6a981c9921652f289eaed123b83249bd8f790ead6934`
-	Entrypoint: `["\/opt\/ol\/docker\/docker-server"]`
-	Default Command: `["\/opt\/ol\/wlp\/bin\/server","run","defaultServer"]`

```dockerfile
# Thu, 23 Aug 2018 12:50:13 GMT
ADD file:b09779db95ed098d4ff481c60f9070c9855d49079531c872f7f306766b31a320 in / 
# Thu, 23 Aug 2018 12:50:19 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 12:50:22 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 12:50:25 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 12:50:29 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 12:50:31 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 16:23:06 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Thu, 23 Aug 2018 16:23:41 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 16:23:43 GMT
ENV JAVA_VERSION=1.8.0_sr5fp20
# Thu, 23 Aug 2018 16:25:44 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='b2dfbdac0fda3fd8ecea6d9d145da7d6f9fa79fe5cfc13dd3862fc331b8698de';          YML_FILE='jre/linux/x86_64/index.yml';          ;;        i386)          ESUM='b4f525b885ca369b1ab626d552e3ed74f5c6ccc674fcaf5340ecbd9aa046c1eb';          YML_FILE='jre/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='bf824a43250b64a85f86e43ee75543de235a4e768f5cc540d4e8b0f4fae2ff18';          YML_FILE='jre/linux/ppc64le/index.yml';          ;;        s390)          ESUM='f216bf12f094e48c3bf05a45d27669f047670e734d4be3f4015257d42a6b1990';          YML_FILE='jre/linux/s390/index.yml';          ;;        s390x)          ESUM='24acc20c2487f2e3a3246c86a10b90b0d7ce6121d923bd7405a1c53e119094ac';          YML_FILE='jre/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(sed -n '/^'${JAVA_VERSION}:'/{n;s/\s*uri:\s//p}'< /tmp/index.yml);     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Thu, 23 Aug 2018 16:25:47 GMT
ENV JAVA_HOME=/opt/ibm/java/jre PATH=/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin IBM_JAVA_OPTIONS=-XX:+UseContainerSupport
# Thu, 23 Aug 2018 17:02:12 GMT
LABEL maintainer=Alasdair Nottingham vendor=Open Liberty url=https://openliberty.io/ github=https://github.com/OpenLiberty/ci.docker
# Thu, 23 Aug 2018 17:02:16 GMT
COPY file:a6eac68a3be2db3229be20bb825e70a7a1e5f32d189da5168ed4f2fe9c9b96fc in /opt/ol/docker/ 
# Thu, 23 Aug 2018 17:04:55 GMT
ENV LIBERTY_VERSION=18.0.0.2 LIBERTY_SHA=4170e609e1e4189e75a57bcc0e65a972e9c9ef6e
# Thu, 23 Aug 2018 17:06:11 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends unzip     && rm -rf /var/lib/apt/lists/*     && wget https://repo1.maven.org/maven2/io/openliberty/openliberty-runtime/$LIBERTY_VERSION/openliberty-runtime-$LIBERTY_VERSION.zip -U UA-Open-Liberty-Docker -O /tmp/wlp.zip     && echo "$LIBERTY_SHA  /tmp/wlp.zip" > /tmp/wlp.zip.sha1     && sha1sum -c /tmp/wlp.zip.sha1     && unzip -q /tmp/wlp.zip -d /opt/ol     && rm /tmp/wlp.zip     && rm /tmp/wlp.zip.sha1     && apt-get remove -y unzip     && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 17:06:12 GMT
ENV PATH=/opt/ol/wlp/bin:/opt/ol/docker/:/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin LOG_DIR=/logs WLP_OUTPUT_DIR=/opt/ol/wlp/output WLP_SKIP_MAXPERMSIZE=true
# Thu, 23 Aug 2018 17:06:14 GMT
RUN mkdir /logs     && mkdir -p $WLP_OUTPUT_DIR/defaultServer     && ln -s $WLP_OUTPUT_DIR/defaultServer /output     && ln -s /opt/ol/wlp/usr/servers/defaultServer /config     && ln -s /logs $WLP_OUTPUT_DIR/defaultServer/logs     && ln -s /liberty /opt/ol/wlp
# Thu, 23 Aug 2018 17:06:18 GMT
RUN /opt/ol/wlp/bin/server create     && rm /config/server.env     && rm -rf $WLP_OUTPUT_DIR/.classCache /output/workarea     && mkdir /config/configDropins     && mkdir /config/configDropins/defaults     && echo "<server description=\"Default Server\"><httpEndpoint id=\"defaultHttpEndpoint\" host=\"*\" /></server>" > /config/configDropins/defaults/open-default-port.xml
# Thu, 23 Aug 2018 17:06:19 GMT
EXPOSE 9080/tcp 9443/tcp
# Thu, 23 Aug 2018 17:06:20 GMT
ENTRYPOINT ["/opt/ol/docker/docker-server"]
# Thu, 23 Aug 2018 17:06:20 GMT
CMD ["/opt/ol/wlp/bin/server" "run" "defaultServer"]
# Thu, 23 Aug 2018 17:07:39 GMT
RUN mkdir -p /opt/ol/wlp/usr/shared/resources/lib.index.cache   && ln -s /opt/ol/wlp/usr/shared/resources/lib.index.cache /lib.index.cache
# Thu, 23 Aug 2018 17:07:40 GMT
COPY file:01d87f11d05fde398ec003f0aeae67fd944b6f2f7ca7d69b7d29cac22e0318e7 in /config/ 
# Thu, 23 Aug 2018 17:07:51 GMT
RUN /opt/ol/wlp/bin/server start && /opt/ol/wlp/bin/server stop && rm -rf /output/resources/security/
```

-	Layers:
	-	`sha256:0d0dbb9a021cbff2129dab2bc36f95d25c2bde53c72d61c87f45f4b14b810ebc`  
		Last Modified: Thu, 23 Aug 2018 12:53:07 GMT  
		Size: 45.6 MB (45595505 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5cb08b3a0bd0961e0ecbe16b6c544124a22f1beca9f3621f59e5cd5e2346d49`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10066c30deaec81ef942231f5f84b5782b7cf7bcf78c389453617b7265465be2`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 579.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d604dc40c1d1c57ec0ba6faed21bc3b4e8ea4fa54eb547fbc134e7c73d468203`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 857.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12b9507f41bb4395530111a162394310249dfe8f51e0682c9c17747c09ff12f6`  
		Last Modified: Thu, 23 Aug 2018 12:52:56 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d43d6ba84f2c24c33f5e348c88ba6b90a2263c4c410262a1f188d2ad151a9f9`  
		Last Modified: Thu, 23 Aug 2018 16:32:27 GMT  
		Size: 2.9 MB (2880557 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e92cd229a04d34b53bf69609e4a9bd55e0f4d47a4acc4537d5ba433790b943c7`  
		Last Modified: Thu, 23 Aug 2018 16:32:58 GMT  
		Size: 141.0 MB (141049753 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:914ccc0cc8019ff1c49f87c12034c901723d6203f4e4a5797da631218a627bdf`  
		Last Modified: Thu, 23 Aug 2018 17:09:13 GMT  
		Size: 436.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:459d2264a44d4f17ac1c0e547ff86e78fd072b340bc7d4a019ca06b9a18991ec`  
		Last Modified: Thu, 23 Aug 2018 17:10:44 GMT  
		Size: 121.1 MB (121067484 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9063a97d68e4b413828910c2e8b68c7e48398ef525b4618cb0e0e9ea9ba57f29`  
		Last Modified: Thu, 23 Aug 2018 17:10:29 GMT  
		Size: 345.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8be907b35aa8e9d0fd4ed7a4a37917ce49c950849104f83021ccab6753f3ff7c`  
		Last Modified: Thu, 23 Aug 2018 17:10:28 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cba4584a45217605011ff55701546373e27ce3b9c5761f2e6d390ce95d6a9720`  
		Last Modified: Thu, 23 Aug 2018 17:11:57 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e43623695e209918fa030e7dccd7bbe805e3088f3c3b6c12c6769801aedc6b5`  
		Last Modified: Thu, 23 Aug 2018 17:11:57 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ee0ebeaa2acae6316104700ec011c52a9d9937648240aa3bb4a89a99f9bb470`  
		Last Modified: Thu, 23 Aug 2018 17:12:00 GMT  
		Size: 8.2 MB (8168412 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `open-liberty:springBoot1-java8-ibm` - linux; s390x

```console
$ docker pull open-liberty@sha256:d2a0f2ef6c56ece51b7b3a2fe46990420ee2f4b230f0f09540372381dfc02958
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **301.3 MB (301263531 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:62c0bb3d5ada309fd77a2c889066003f9f005baf6d461ce462db55e63c95d0a4`
-	Entrypoint: `["\/opt\/ol\/docker\/docker-server"]`
-	Default Command: `["\/opt\/ol\/wlp\/bin\/server","run","defaultServer"]`

```dockerfile
# Thu, 23 Aug 2018 14:49:17 GMT
ADD file:94740559815ae2a4f5e95bd0d7fd560cc9a934cfd754a24cf0aadec470a78096 in / 
# Thu, 23 Aug 2018 14:49:18 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 23 Aug 2018 14:49:18 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 14:49:19 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 23 Aug 2018 14:49:19 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 23 Aug 2018 14:49:20 GMT
CMD ["/bin/bash"]
# Thu, 23 Aug 2018 15:34:34 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Thu, 23 Aug 2018 15:35:24 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 15:35:25 GMT
ENV JAVA_VERSION=1.8.0_sr5fp20
# Thu, 23 Aug 2018 15:36:06 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='b2dfbdac0fda3fd8ecea6d9d145da7d6f9fa79fe5cfc13dd3862fc331b8698de';          YML_FILE='jre/linux/x86_64/index.yml';          ;;        i386)          ESUM='b4f525b885ca369b1ab626d552e3ed74f5c6ccc674fcaf5340ecbd9aa046c1eb';          YML_FILE='jre/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='bf824a43250b64a85f86e43ee75543de235a4e768f5cc540d4e8b0f4fae2ff18';          YML_FILE='jre/linux/ppc64le/index.yml';          ;;        s390)          ESUM='f216bf12f094e48c3bf05a45d27669f047670e734d4be3f4015257d42a6b1990';          YML_FILE='jre/linux/s390/index.yml';          ;;        s390x)          ESUM='24acc20c2487f2e3a3246c86a10b90b0d7ce6121d923bd7405a1c53e119094ac';          YML_FILE='jre/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(sed -n '/^'${JAVA_VERSION}:'/{n;s/\s*uri:\s//p}'< /tmp/index.yml);     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Thu, 23 Aug 2018 15:36:06 GMT
ENV JAVA_HOME=/opt/ibm/java/jre PATH=/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin IBM_JAVA_OPTIONS=-XX:+UseContainerSupport
# Thu, 23 Aug 2018 16:05:48 GMT
LABEL maintainer=Alasdair Nottingham vendor=Open Liberty url=https://openliberty.io/ github=https://github.com/OpenLiberty/ci.docker
# Thu, 23 Aug 2018 16:05:48 GMT
COPY file:a6eac68a3be2db3229be20bb825e70a7a1e5f32d189da5168ed4f2fe9c9b96fc in /opt/ol/docker/ 
# Thu, 23 Aug 2018 16:07:48 GMT
ENV LIBERTY_VERSION=18.0.0.2 LIBERTY_SHA=4170e609e1e4189e75a57bcc0e65a972e9c9ef6e
# Thu, 23 Aug 2018 16:08:18 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends unzip     && rm -rf /var/lib/apt/lists/*     && wget https://repo1.maven.org/maven2/io/openliberty/openliberty-runtime/$LIBERTY_VERSION/openliberty-runtime-$LIBERTY_VERSION.zip -U UA-Open-Liberty-Docker -O /tmp/wlp.zip     && echo "$LIBERTY_SHA  /tmp/wlp.zip" > /tmp/wlp.zip.sha1     && sha1sum -c /tmp/wlp.zip.sha1     && unzip -q /tmp/wlp.zip -d /opt/ol     && rm /tmp/wlp.zip     && rm /tmp/wlp.zip.sha1     && apt-get remove -y unzip     && rm -rf /var/lib/apt/lists/*
# Thu, 23 Aug 2018 16:08:18 GMT
ENV PATH=/opt/ol/wlp/bin:/opt/ol/docker/:/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin LOG_DIR=/logs WLP_OUTPUT_DIR=/opt/ol/wlp/output WLP_SKIP_MAXPERMSIZE=true
# Thu, 23 Aug 2018 16:08:19 GMT
RUN mkdir /logs     && mkdir -p $WLP_OUTPUT_DIR/defaultServer     && ln -s $WLP_OUTPUT_DIR/defaultServer /output     && ln -s /opt/ol/wlp/usr/servers/defaultServer /config     && ln -s /logs $WLP_OUTPUT_DIR/defaultServer/logs     && ln -s /liberty /opt/ol/wlp
# Thu, 23 Aug 2018 16:08:20 GMT
RUN /opt/ol/wlp/bin/server create     && rm /config/server.env     && rm -rf $WLP_OUTPUT_DIR/.classCache /output/workarea     && mkdir /config/configDropins     && mkdir /config/configDropins/defaults     && echo "<server description=\"Default Server\"><httpEndpoint id=\"defaultHttpEndpoint\" host=\"*\" /></server>" > /config/configDropins/defaults/open-default-port.xml
# Thu, 23 Aug 2018 16:08:20 GMT
EXPOSE 9080/tcp 9443/tcp
# Thu, 23 Aug 2018 16:08:21 GMT
ENTRYPOINT ["/opt/ol/docker/docker-server"]
# Thu, 23 Aug 2018 16:08:21 GMT
CMD ["/opt/ol/wlp/bin/server" "run" "defaultServer"]
# Thu, 23 Aug 2018 16:09:19 GMT
RUN mkdir -p /opt/ol/wlp/usr/shared/resources/lib.index.cache   && ln -s /opt/ol/wlp/usr/shared/resources/lib.index.cache /lib.index.cache
# Thu, 23 Aug 2018 16:09:20 GMT
COPY file:01d87f11d05fde398ec003f0aeae67fd944b6f2f7ca7d69b7d29cac22e0318e7 in /config/ 
# Thu, 23 Aug 2018 16:09:27 GMT
RUN /opt/ol/wlp/bin/server start && /opt/ol/wlp/bin/server stop && rm -rf /output/resources/security/
```

-	Layers:
	-	`sha256:471a4c1f3afec0f7170a0ef60b95447c8ccfccdded51e3c29b28a96741a05c29`  
		Last Modified: Thu, 23 Aug 2018 14:51:33 GMT  
		Size: 42.3 MB (42253615 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3f1b921c0f85f239afe44fe32aec1484822dc0ecee5dae4144ef99df661928e`  
		Last Modified: Thu, 23 Aug 2018 14:51:11 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:026a9618114b42f3e98d2474b9bffcf0f3b394b837f4c531a60338e25e111112`  
		Last Modified: Thu, 23 Aug 2018 14:51:10 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:759772c425b56c1dc191c452852f0a201e52965b83e9d0e972ac43f6fba9ee56`  
		Last Modified: Thu, 23 Aug 2018 14:51:10 GMT  
		Size: 857.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed895562017a99eebcf1de58efac03ab7a73322a695cb83067ee480f0e563d0d`  
		Last Modified: Thu, 23 Aug 2018 14:51:10 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3eb6d3e4e20e448d04a38b8a82c151223f51d101a507ae30fad4706893514dda`  
		Last Modified: Thu, 23 Aug 2018 15:38:01 GMT  
		Size: 2.8 MB (2764946 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c7759a777a40e8afacf1766f63e4e65cc5977625de817b31c5ec472a92bc67a`  
		Last Modified: Thu, 23 Aug 2018 15:39:02 GMT  
		Size: 127.0 MB (126957375 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:edaf9a371606a7c37413bf954110234249103dbded05401f7ccec36654f03d6e`  
		Last Modified: Thu, 23 Aug 2018 16:10:19 GMT  
		Size: 402.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2efde62256e04058639f2f1ad2ebc798a1c359086df537a284be82c160990f5`  
		Last Modified: Thu, 23 Aug 2018 16:14:41 GMT  
		Size: 121.1 MB (121067338 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:416a691b5ed4ea94a4605bc0a908831edbaecbc1b0a1d03b27152a52c1675d96`  
		Last Modified: Thu, 23 Aug 2018 16:13:17 GMT  
		Size: 299.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ce1e123f02facbc45ef74461c7ed8392f09c725c103d7cd3b0395c802e344ae`  
		Last Modified: Thu, 23 Aug 2018 16:13:17 GMT  
		Size: 804.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:822403ab3562fab2a6ff8ddcbdd7a7f8aa26c631e8734110b3673b96d973efcd`  
		Last Modified: Thu, 23 Aug 2018 16:15:52 GMT  
		Size: 255.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a87732bf8d8e743306cc6a38be934b622fca9d3b42519a192c62ae0771fb538f`  
		Last Modified: Thu, 23 Aug 2018 16:15:52 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f73cf09d8fd761b482b2afe4915a0445c4f13c5cf483379ff9f662dc12843a70`  
		Last Modified: Thu, 23 Aug 2018 16:15:55 GMT  
		Size: 8.2 MB (8215552 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
