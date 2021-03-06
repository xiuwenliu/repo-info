## `nats:nanoserver`

```console
$ docker pull nats@sha256:d3c9de107149d1e96feefeb4e444042cc58a519c538fa4898e087a084d714217
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2430; amd64

### `nats:nanoserver` - windows version 10.0.14393.2430; amd64

```console
$ docker pull nats@sha256:ba953f2c9136fd73a3d16107b440731fc8da23c36cc1fe6f3d4bac047228b10f
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **423.5 MB (423498165 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:303b2431c3bf3ffbbf4af27d6e2ceee0e8ba25ce18fe26e53c9c6e829ba10de9`
-	Entrypoint: `["gnatsd"]`
-	Default Command: `["-c","gnatsd.conf"]`

```dockerfile
# Tue, 13 Dec 2016 10:47:17 GMT
RUN Apply image 10.0.14393.0
# Mon, 13 Aug 2018 17:51:52 GMT
RUN Install update 10.0.14393.2430
# Sat, 01 Sep 2018 09:16:32 GMT
RUN cmd /S /C #(nop)  ENV NATS_DOCKERIZED=1
# Sat, 01 Sep 2018 09:16:33 GMT
RUN cmd /S /C #(nop) WORKDIR C:\gnatsd
# Sat, 01 Sep 2018 09:16:36 GMT
RUN cmd /S /C #(nop) COPY file:90ca2563d6c9eedc40d34c00debbb7645b3b7e24610045e812635873dead38c0 in gnatsd.exe 
# Sat, 01 Sep 2018 09:16:38 GMT
RUN cmd /S /C #(nop) COPY file:8fad70d15db71db30b9945fba2b3d29035a631ee4fe410e797aef6981c2a1879 in gnatsd.conf 
# Sat, 01 Sep 2018 09:16:39 GMT
RUN cmd /S /C #(nop)  EXPOSE 4222/tcp 6222/tcp 8222/tcp
# Sat, 01 Sep 2018 09:16:40 GMT
RUN cmd /S /C #(nop)  ENTRYPOINT ["gnatsd"]
# Sat, 01 Sep 2018 09:16:41 GMT
RUN cmd /S /C #(nop)  CMD ["-c" "gnatsd.conf"]
```

-	Layers:
	-	`sha256:bce2fbc256ea437a87dadac2f69aabd25bed4f56255549090056c1131fad0277`  
		Last Modified: Tue, 13 Dec 2016 10:47:17 GMT  
		Size: 252.7 MB (252691002 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:4a14bdf6da80603aa5007acea8d5ea659958b0bd1b31d31078023ca0d1c8ee05`  
		Last Modified: Mon, 13 Aug 2018 17:51:52 GMT  
		Size: 167.8 MB (167784035 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:a7c6c5ea540b6fa9c311ada0aa79e1d6a539cefffe98b603b8c7fe79ed75c84b`  
		Last Modified: Sat, 01 Sep 2018 09:17:08 GMT  
		Size: 948.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:088960eff50fe41a26f35af1603c8a47c4ac67c782901d737426c167c45c7d05`  
		Last Modified: Sat, 01 Sep 2018 09:17:08 GMT  
		Size: 1.2 KB (1155 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:04bbb442fa342fb1e354f498b9686f4fd3ee376a9a721d9474fbe5c1c40436a1`  
		Last Modified: Sat, 01 Sep 2018 09:17:07 GMT  
		Size: 3.0 MB (3016486 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1a34f4485adcf80f1d2d562c6c5a167a447c7f1b05ed2e99c9a69630cec627ae`  
		Last Modified: Sat, 01 Sep 2018 09:17:06 GMT  
		Size: 1.7 KB (1693 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0ebbfd93cb309fd92985818a3b177d28acf5d38fedb048e1886ca94348e389f`  
		Last Modified: Sat, 01 Sep 2018 09:17:07 GMT  
		Size: 947.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eadd6e2f5f216c8bb3e3ad0ea313a103d89a22fc58c4abbd15f729e6620d9aca`  
		Last Modified: Sat, 01 Sep 2018 09:17:06 GMT  
		Size: 950.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb077ff75ce74d583b11f963488ecdca0c1a2dbe877e24a9f4d05eeba7e3781b`  
		Last Modified: Sat, 01 Sep 2018 09:17:06 GMT  
		Size: 949.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
