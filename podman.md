# What is podman?

Podman is a daemonless, open source, Linux native tool designed to make it easy to find, run, build, share and deploy applications using Open Containers Initiative (OCI) Containers and Container Images. Podman provides a command line interface (CLI) familiar to anyone who has used the Docker Container Engine. Most users can simply alias Docker to Podman (alias docker=podman) without any problems. Similar to other common Container Engines (Docker, CRI-O, containerd), Podman relies on an OCI compliant Container Runtime (runc, crun, runv, etc) to interface with the operating system and create the running containers. This makes the running containers created by Podman nearly indistinguishable from those created by any other common container engine.

Containers under the control of Podman can either be run by root or by a non-privileged user. Podman manages the entire container ecosystem which includes pods, containers, container images, and container volumes using the libpod library. Podman specializes in all of the commands and functions that help you to maintain and modify OCI container images, such as pulling and tagging. It allows you to create, run, and maintain those containers and container images in a production environment.

There is a RESTFul API to manage containers. We also have a remote Podman client that can interact with the RESTFul service. We currently support clients on Linux, Mac, and Windows. The RESTFul service is only supported on Linux.

# install podman on Mac OS
```bash
brew install podman

Running `brew update --auto-update`...
==> Auto-updated Homebrew!
Updated 3 taps (homebrew/cask-versions, homebrew/core and homebrew/cask).
==> New Formulae
halp                                     hopscotch-map                            netsurf-buildsystem                      sugarjar
==> New Casks
openthesaurus-deutsch

==> Downloading https://ghcr.io/v2/homebrew/core/podman/manifests/4.8.2
############################################################################################################################################################# 100.0%
==> Fetching dependencies for podman: capstone, dtc, pcre2, gettext, glib, ca-certificates, gmp, libunistring, libidn2, libtasn1, nettle, p11-kit, openssl@3, libevent, libnghttp2, unbound, gnutls, jpeg-turbo, libpng, libslirp, libssh, libusb, lzo, ncurses, pixman, snappy, vde, lz4, xz, zstd and qemu
==> Downloading https://ghcr.io/v2/homebrew/core/capstone/manifests/5.0.1
############################################################################################################################################################# 100.0%
==> Fetching capstone
==> Downloading https://ghcr.io/v2/homebrew/core/capstone/blobs/sha256:1f30bfa8d92451f670c2952ebcb12ac1e44bde8ec15c5f9d420f82515ca31e9c
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/dtc/manifests/1.7.0
############################################################################################################################################################# 100.0%
==> Fetching dtc
==> Downloading https://ghcr.io/v2/homebrew/core/dtc/blobs/sha256:9ca326b92b46108692e2f27bf20e83877bf772650f0e6912be5ce3934df284a5
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/pcre2/manifests/10.42
############################################################################################################################################################# 100.0%
==> Fetching pcre2
==> Downloading https://ghcr.io/v2/homebrew/core/pcre2/blobs/sha256:8423a338c590ab1a6f265b39a9d1a67ab1361a586f0e494a8c9555cff2867536
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/gettext/manifests/0.22.4
############################################################################################################################################################# 100.0%
==> Fetching gettext
==> Downloading https://ghcr.io/v2/homebrew/core/gettext/blobs/sha256:c652190aa716f3ca57678562de9cef6380d124f45a799f1f6eb1506a9b05ab1a
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/glib/manifests/2.78.3
############################################################################################################################################################# 100.0%
==> Fetching glib
==> Downloading https://ghcr.io/v2/homebrew/core/glib/blobs/sha256:25043e7acd81017477a6125097802b9482026786037ef9ed40fcffca5ca3fcc9
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/ca-certificates/manifests/2023-12-12
############################################################################################################################################################# 100.0%
==> Fetching ca-certificates
==> Downloading https://ghcr.io/v2/homebrew/core/ca-certificates/blobs/sha256:5c99ffd0861f01adc19cab495027024f7d890e42a9e7b689706b85c8e2b9c9b3
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/gmp/manifests/6.3.0
############################################################################################################################################################# 100.0%
==> Fetching gmp
==> Downloading https://ghcr.io/v2/homebrew/core/gmp/blobs/sha256:98c163edfbe7bdc0c14f88d7d34fa2764ecb9cab9f749600b861012700603260
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libunistring/manifests/1.1
############################################################################################################################################################# 100.0%
==> Fetching libunistring
==> Downloading https://ghcr.io/v2/homebrew/core/libunistring/blobs/sha256:c78e7b0af88bef155ad7f12d63ad60f0c87e5a8cccb8f40ec5d9304f8fdfaee7
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libidn2/manifests/2.3.4_1-1
############################################################################################################################################################# 100.0%
==> Fetching libidn2
==> Downloading https://ghcr.io/v2/homebrew/core/libidn2/blobs/sha256:b044c66cc0f1feea87d229f3f4016c5ff29a0fb0f712d0d5219f05465247b10f
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libtasn1/manifests/4.19.0
############################################################################################################################################################# 100.0%
==> Fetching libtasn1
==> Downloading https://ghcr.io/v2/homebrew/core/libtasn1/blobs/sha256:9fcf93a7992888a29caf2bc3ad37fb27ee8ceef180367797f4a11040fa761eac
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/nettle/manifests/3.9.1
############################################################################################################################################################# 100.0%
==> Fetching nettle
==> Downloading https://ghcr.io/v2/homebrew/core/nettle/blobs/sha256:751e140ceac7711c462f1c05d74297c79f0abea26666f974370886c01d7bec83
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/p11-kit/manifests/0.25.3
############################################################################################################################################################# 100.0%
==> Fetching p11-kit
==> Downloading https://ghcr.io/v2/homebrew/core/p11-kit/blobs/sha256:f965f464d9c3b641003d924bcea428586ec8572dd0ed54f41b879ef727b4b4e9
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/openssl/3/manifests/3.2.0_1
############################################################################################################################################################# 100.0%
==> Fetching openssl@3
==> Downloading https://ghcr.io/v2/homebrew/core/openssl/3/blobs/sha256:4bf12955cbd2ef13c0ee3fd19c6d4b3f4b04c0023ede6348eb25d7a18298f828
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libevent/manifests/2.1.12_1
############################################################################################################################################################# 100.0%
==> Fetching libevent
==> Downloading https://ghcr.io/v2/homebrew/core/libevent/blobs/sha256:a75d453a7fe2aba1eaba334621b7bd9f0ff6f9e1f04aa400565f68711a9f6db4
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libnghttp2/manifests/1.58.0
############################################################################################################################################################# 100.0%
==> Fetching libnghttp2
==> Downloading https://ghcr.io/v2/homebrew/core/libnghttp2/blobs/sha256:73d3d70d47edc13dc862954d248fad4df7ca33e239dbe3ef09d3f16551bfe6bd
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/unbound/manifests/1.19.0
############################################################################################################################################################# 100.0%
==> Fetching unbound
==> Downloading https://ghcr.io/v2/homebrew/core/unbound/blobs/sha256:5c0001680762d8221915b96bcd56e33f5c63b951c713dc49f0154badd8e3b52e
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/gnutls/manifests/3.8.2
############################################################################################################################################################# 100.0%
==> Fetching gnutls
==> Downloading https://ghcr.io/v2/homebrew/core/gnutls/blobs/sha256:48cbe35994d3baa0f4fcaf1567c8143b63800c9f913c673d9ececf9a0be676f7
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/jpeg-turbo/manifests/3.0.0
############################################################################################################################################################# 100.0%
==> Fetching jpeg-turbo
==> Downloading https://ghcr.io/v2/homebrew/core/jpeg-turbo/blobs/sha256:1971c1fa66c2580fa0bfafe5350c6170bfe7395a4e503e7bfe0c69ec2e353010
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libpng/manifests/1.6.40
############################################################################################################################################################# 100.0%
==> Fetching libpng
==> Downloading https://ghcr.io/v2/homebrew/core/libpng/blobs/sha256:c309cf133ab08f4fd25210da897eaaff2603e9a7e1bdc178821c7e186fb9ee69
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libslirp/manifests/4.7.0
############################################################################################################################################################# 100.0%
==> Fetching libslirp
==> Downloading https://ghcr.io/v2/homebrew/core/libslirp/blobs/sha256:3e461de89cdcc48cd88ed8065700575cc3d4921213f2023cce1c1c56853c9117
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libssh/manifests/0.10.6
############################################################################################################################################################# 100.0%
==> Fetching libssh
==> Downloading https://ghcr.io/v2/homebrew/core/libssh/blobs/sha256:c6cfcd06891daf88f1995cb4165ffd113edfaed6ab3aedc73ffd93ded8f9f1c3
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libusb/manifests/1.0.26
############################################################################################################################################################# 100.0%
==> Fetching libusb
==> Downloading https://ghcr.io/v2/homebrew/core/libusb/blobs/sha256:ea8a4a04b5cc81eff38d0c5cdfe2fbac519ca2c7652c64371074f4abaf766a0b
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/lzo/manifests/2.10
############################################################################################################################################################# 100.0%
==> Fetching lzo
==> Downloading https://ghcr.io/v2/homebrew/core/lzo/blobs/sha256:a565c627b13f2dc7fc4550aa8290a4c3feb2f48fcaa45c9f7f4bc4fe4535aa66
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/ncurses/manifests/6.4-1
############################################################################################################################################################# 100.0%
==> Fetching ncurses
==> Downloading https://ghcr.io/v2/homebrew/core/ncurses/blobs/sha256:8afdd105a6b1d9ec6c567edfe5a08dd3eff5bece58fc29894ff64ae3851c4ddb
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/pixman/manifests/0.42.2-1
############################################################################################################################################################# 100.0%
==> Fetching pixman
==> Downloading https://ghcr.io/v2/homebrew/core/pixman/blobs/sha256:e27867c503bd9cf858159261e053184d19ae00357dc89426810f80734aaaefd0
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/snappy/manifests/1.1.10
############################################################################################################################################################# 100.0%
==> Fetching snappy
==> Downloading https://ghcr.io/v2/homebrew/core/snappy/blobs/sha256:ca95915a51bed09a5e70ebb6f253eabe4df5b00e87ebe49aea0124f8bb51bc3c
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/vde/manifests/2.3.3
############################################################################################################################################################# 100.0%
==> Fetching vde
==> Downloading https://ghcr.io/v2/homebrew/core/vde/blobs/sha256:982a56825cbd1bd374001330e3492e83a1d82825ed7228d33705ffad3b927e8e
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/lz4/manifests/1.9.4
############################################################################################################################################################# 100.0%
==> Fetching lz4
==> Downloading https://ghcr.io/v2/homebrew/core/lz4/blobs/sha256:cd29e40287b0a2d665a647acbea5512e8db4c371687147aab5c60bf9059b2cca
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/xz/manifests/5.4.5
############################################################################################################################################################# 100.0%
==> Fetching xz
==> Downloading https://ghcr.io/v2/homebrew/core/xz/blobs/sha256:05d853bc61d9bf9ed3ca2e5e54bc240f1924fb9085618387f7f6ce90b25b1d95
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/zstd/manifests/1.5.5-1
############################################################################################################################################################# 100.0%
==> Fetching zstd
==> Downloading https://ghcr.io/v2/homebrew/core/zstd/blobs/sha256:cd3a7447c6a18cae189c2366820113f7b23425643482f8af45d03c6e91417ff8
############################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/qemu/manifests/8.2.0
############################################################################################################################################################# 100.0%
==> Fetching qemu
==> Downloading https://ghcr.io/v2/homebrew/core/qemu/blobs/sha256:52c142865f7ce3dff12325649a332de1d90982cbb05d92c3626c6c281834dc91
############################################################################################################################################################# 100.0%
==> Fetching podman
==> Downloading https://ghcr.io/v2/homebrew/core/podman/blobs/sha256:4a5a42c246f036cd977607b4fd069a902b424539d488972c4ddea1e0f0d10181
############################################################################################################################################################# 100.0%
==> Installing dependencies for podman: capstone, dtc, pcre2, gettext, glib, ca-certificates, gmp, libunistring, libidn2, libtasn1, nettle, p11-kit, openssl@3, libevent, libnghttp2, unbound, gnutls, jpeg-turbo, libpng, libslirp, libssh, libusb, lzo, ncurses, pixman, snappy, vde, lz4, xz, zstd and qemu
==> Installing podman dependency: capstone
==> Downloading https://ghcr.io/v2/homebrew/core/capstone/manifests/5.0.1
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/eb17389103bcda1a9712be38238eb72e8056accea2c41fe32618aada1d7e1d79--capstone-5.0.1.bottle_manifest.json
==> Pouring capstone--5.0.1.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/capstone/5.0.1: 30 files, 22.3MB
==> Installing podman dependency: dtc
==> Downloading https://ghcr.io/v2/homebrew/core/dtc/manifests/1.7.0
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/00668efdbca5875f420621ff3011ae53448a6324636c2a27fe2323933c1ef3fa--dtc-1.7.0.bottle_manifest.json
==> Pouring dtc--1.7.0.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/dtc/1.7.0: 18 files, 619.2KB
==> Installing podman dependency: pcre2
==> Downloading https://ghcr.io/v2/homebrew/core/pcre2/manifests/10.42
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/6a53794fcaabc5cc5e05b19c02ca9c4c5f2cb9a4d65a5790a6841146465b040f--pcre2-10.42.bottle_manifest.json
==> Pouring pcre2--10.42.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/pcre2/10.42: 230 files, 6.2MB
==> Installing podman dependency: gettext
==> Downloading https://ghcr.io/v2/homebrew/core/gettext/manifests/0.22.4
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/3ceb9457127eaa7378dd80ed256098ffb391e2350069becb25cfe2a14f0b7d6d--gettext-0.22.4.bottle_manifest.json
==> Pouring gettext--0.22.4.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/gettext/0.22.4: 2,042 files, 24.3MB
==> Installing podman dependency: glib
==> Downloading https://ghcr.io/v2/homebrew/core/glib/manifests/2.78.3
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/33691fa3f0682c43459117cdc029ecef157fab4e7f1c8bdac19e861665ffc1db--glib-2.78.3.bottle_manifest.json
==> Pouring glib--2.78.3.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/glib/2.78.3: 456 files, 22.5MB
==> Installing podman dependency: ca-certificates
==> Downloading https://ghcr.io/v2/homebrew/core/ca-certificates/manifests/2023-12-12
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/13aa86e429e05d02a76005d1881eaf625091a5ac4dc7d7674c706d12ba48796a--ca-certificates-2023-12-12.bottle_manifest.json
==> Pouring ca-certificates--2023-12-12.all.bottle.tar.gz
==> Regenerating CA certificate bundle from keychain, this may take a while...
🍺  /opt/homebrew/Cellar/ca-certificates/2023-12-12: 3 files, 226.7KB
==> Installing podman dependency: gmp
==> Downloading https://ghcr.io/v2/homebrew/core/gmp/manifests/6.3.0
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/70a72a71216843d66a953c06ff6337445ce9bc94fae9f0e301e2f59005274a8e--gmp-6.3.0.bottle_manifest.json
==> Pouring gmp--6.3.0.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/gmp/6.3.0: 21 files, 3.3MB
==> Installing podman dependency: libunistring
==> Downloading https://ghcr.io/v2/homebrew/core/libunistring/manifests/1.1
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/a34801f1ad5800ba51b2b3951d82a913ccf0641982f86b02df2f0aa182535055--libunistring-1.1.bottle_manifest.json
==> Pouring libunistring--1.1.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libunistring/1.1: 56 files, 5.0MB
==> Installing podman dependency: libidn2
==> Downloading https://ghcr.io/v2/homebrew/core/libidn2/manifests/2.3.4_1-1
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/03ad193177f4e7d05ee2ed19a455028cb5fbf7ea1a812d88f18f5e9e8b4a4d43--libidn2-2.3.4_1-1.bottle_manifest.json
==> Pouring libidn2--2.3.4_1.arm64_ventura.bottle.1.tar.gz
🍺  /opt/homebrew/Cellar/libidn2/2.3.4_1: 79 files, 1MB
==> Installing podman dependency: libtasn1
==> Downloading https://ghcr.io/v2/homebrew/core/libtasn1/manifests/4.19.0
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/8abecce04f40738bc8a6921a6b96d847ea5c9759185d4bd9c7c9b5fb4922c375--libtasn1-4.19.0.bottle_manifest.json
==> Pouring libtasn1--4.19.0.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libtasn1/4.19.0: 61 files, 717.8KB
==> Installing podman dependency: nettle
==> Downloading https://ghcr.io/v2/homebrew/core/nettle/manifests/3.9.1
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/a02ae3a1ecc6cff56e632f6452fd57f3fa72be16cde0b69e5b47747283fd3f6b--nettle-3.9.1.bottle_manifest.json
==> Pouring nettle--3.9.1.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/nettle/3.9.1: 94 files, 2.7MB
==> Installing podman dependency: p11-kit
==> Downloading https://ghcr.io/v2/homebrew/core/p11-kit/manifests/0.25.3
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/cc547bf2f72da03680090015f5b720aff280ce33de9c33783a69c24fe97a4246--p11-kit-0.25.3.bottle_manifest.json
==> Pouring p11-kit--0.25.3.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/p11-kit/0.25.3: 28 files, 4.2MB
==> Installing podman dependency: openssl@3
==> Downloading https://ghcr.io/v2/homebrew/core/openssl/3/manifests/3.2.0_1
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/8e5415de690efd057f74775ab4b808fed9a50bf29c34ee9cb52118d189ef73a9--openssl@3-3.2.0_1.bottle_manifest.json
==> Pouring openssl@3--3.2.0_1.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/openssl@3/3.2.0_1: 6,805 files, 31.9MB
==> Installing podman dependency: libevent
==> Downloading https://ghcr.io/v2/homebrew/core/libevent/manifests/2.1.12_1
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/68b113f9ab63db45f4e1860de522ce2ca4fa081eb3c0d5c7d6005a35c3cf8d06--libevent-2.1.12_1.bottle_manifest.json
==> Pouring libevent--2.1.12_1.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libevent/2.1.12_1: 57 files, 2.2MB
==> Installing podman dependency: libnghttp2
==> Downloading https://ghcr.io/v2/homebrew/core/libnghttp2/manifests/1.58.0
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/9b2081d73959d4308c84740344d5f8169bbb9125dd76d20a71556a11a0171253--libnghttp2-1.58.0.bottle_manifest.json
==> Pouring libnghttp2--1.58.0.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libnghttp2/1.58.0: 13 files, 739.2KB
==> Installing podman dependency: unbound
==> Downloading https://ghcr.io/v2/homebrew/core/unbound/manifests/1.19.0
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/5ef4c435591de61234a87b911b8f2793a67aea99fa163a6c156bb9303f7fac11--unbound-1.19.0.bottle_manifest.json
==> Pouring unbound--1.19.0.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/unbound/1.19.0: 58 files, 5.9MB
==> Installing podman dependency: gnutls
==> Downloading https://ghcr.io/v2/homebrew/core/gnutls/manifests/3.8.2
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/451d8f1012df2b218c76390367beb96684e0899d24cb219dfe87eb047945fc14--gnutls-3.8.2.bottle_manifest.json
==> Pouring gnutls--3.8.2.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/gnutls/3.8.2: 1,290 files, 10.8MB
==> Installing podman dependency: jpeg-turbo
==> Downloading https://ghcr.io/v2/homebrew/core/jpeg-turbo/manifests/3.0.0
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/325e745bcb7840d6a83df7bfcafaa4dbc30b29140f252fb82b7714493df29d6d--jpeg-turbo-3.0.0.bottle_manifest.json
==> Pouring jpeg-turbo--3.0.0.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/jpeg-turbo/3.0.0: 44 files, 3.4MB
==> Installing podman dependency: libpng
==> Downloading https://ghcr.io/v2/homebrew/core/libpng/manifests/1.6.40
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/d2caacc64e32be045b902fa78d2bb4aea7fba8f088cef85cd34b1beab15b755a--libpng-1.6.40.bottle_manifest.json
==> Pouring libpng--1.6.40.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libpng/1.6.40: 27 files, 1.3MB
==> Installing podman dependency: libslirp
==> Downloading https://ghcr.io/v2/homebrew/core/libslirp/manifests/4.7.0
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/d8b5de971474690b01b484c84652c487b14a22eded9d5b91cecae2995692c598--libslirp-4.7.0.bottle_manifest.json
==> Pouring libslirp--4.7.0.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libslirp/4.7.0: 11 files, 385.2KB
==> Installing podman dependency: libssh
==> Downloading https://ghcr.io/v2/homebrew/core/libssh/manifests/0.10.6
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/a4ff6d890d834da2f865bf30651aa0ed1423be8e2684d4586895f1d9c887449b--libssh-0.10.6.bottle_manifest.json
==> Pouring libssh--0.10.6.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libssh/0.10.6: 23 files, 1.3MB
==> Installing podman dependency: libusb
==> Downloading https://ghcr.io/v2/homebrew/core/libusb/manifests/1.0.26
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/ce7ffd7c94deb7060c2cac56f1d68a97b9d4bdc039f9548c3df327bee3d20ae4--libusb-1.0.26.bottle_manifest.json
==> Pouring libusb--1.0.26.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libusb/1.0.26: 22 files, 595.0KB
==> Installing podman dependency: lzo
==> Downloading https://ghcr.io/v2/homebrew/core/lzo/manifests/2.10
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/d4aa5b0c239912c53bc857d1012c6b7feb4acb509618f5e100f95bf8521f08e7--lzo-2.10.bottle_manifest.json
==> Pouring lzo--2.10.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/lzo/2.10: 31 files, 566.2KB
==> Installing podman dependency: ncurses
==> Downloading https://ghcr.io/v2/homebrew/core/ncurses/manifests/6.4-1
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/548168356558130632a3202b3fc2f3069f554bd5c1010b30e61f1180cf1f6b09--ncurses-6.4-1.bottle_manifest.json
==> Pouring ncurses--6.4.arm64_ventura.bottle.1.tar.gz
🍺  /opt/homebrew/Cellar/ncurses/6.4: 4,001 files, 9.7MB
==> Installing podman dependency: pixman
==> Downloading https://ghcr.io/v2/homebrew/core/pixman/manifests/0.42.2-1
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/2b0d8f2c63712ce503fa54309b732051a7ca5cd31bd561aa4aaba331bf26bcef--pixman-0.42.2-1.bottle_manifest.json
==> Pouring pixman--0.42.2.arm64_ventura.bottle.1.tar.gz
🍺  /opt/homebrew/Cellar/pixman/0.42.2: 11 files, 1.2MB
==> Installing podman dependency: snappy
==> Downloading https://ghcr.io/v2/homebrew/core/snappy/manifests/1.1.10
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/66500196008160ff18d67179e002e417a71c59707d74a6706c2e89a8aa2411b8--snappy-1.1.10.bottle_manifest.json
==> Pouring snappy--1.1.10.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/snappy/1.1.10: 18 files, 164.2KB
==> Installing podman dependency: vde
==> Downloading https://ghcr.io/v2/homebrew/core/vde/manifests/2.3.3
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/4e9503141162571c2cd21e89a9e61f524a7403ffe5ffe269f4a39ce5aef9f210--vde-2.3.3.bottle_manifest.json
==> Pouring vde--2.3.3.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/vde/2.3.3: 66 files, 1.3MB
==> Installing podman dependency: lz4
==> Downloading https://ghcr.io/v2/homebrew/core/lz4/manifests/1.9.4
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/379e59b981667f9585b33a2ff318769d8edca3ce6fd2e9a67ed291ae3e0cc872--lz4-1.9.4.bottle_manifest.json
==> Pouring lz4--1.9.4.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/lz4/1.9.4: 22 files, 680KB
==> Installing podman dependency: xz
==> Downloading https://ghcr.io/v2/homebrew/core/xz/manifests/5.4.5
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/4e81fda476fb634a7e1ac650019bfe768a65d6c387015992df4cd75adf9b3fce--xz-5.4.5.bottle_manifest.json
==> Pouring xz--5.4.5.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/xz/5.4.5: 163 files, 2.6MB
==> Installing podman dependency: zstd
==> Downloading https://ghcr.io/v2/homebrew/core/zstd/manifests/1.5.5-1
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/fc13698599720a53800064b40cddd854399651cf8760d9b0e46092f2e8da701a--zstd-1.5.5-1.bottle_manifest.json
==> Pouring zstd--1.5.5.arm64_ventura.bottle.1.tar.gz
🍺  /opt/homebrew/Cellar/zstd/1.5.5: 31 files, 2.1MB
==> Installing podman dependency: qemu
==> Downloading https://ghcr.io/v2/homebrew/core/qemu/manifests/8.2.0
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/4f7b6196780e49f1b813021d9ad59917f982af54f2085ad032bd4c3ca57bd1b9--qemu-8.2.0.bottle_manifest.json
==> Pouring qemu--8.2.0.arm64_ventura.bottle.tar.gz
🍺  /opt/homebrew/Cellar/qemu/8.2.0: 162 files, 562.5MB
==> Installing podman
==> Pouring podman--4.8.2.arm64_ventura.bottle.tar.gz
==> Caveats
        In order to run containers locally, podman depends on a Linux kernel.
        One can be started manually using `podman machine` from this package.
        To start a podman VM automatically at login, also install the cask
        "podman-desktop".

zsh completions have been installed to:
  /opt/homebrew/share/zsh/site-functions
==> Summary
🍺  /opt/homebrew/Cellar/podman/4.8.2: 191 files, 56.7MB
==> Running `brew cleanup podman`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
==> Caveats
==> podman
        In order to run containers locally, podman depends on a Linux kernel.
        One can be started manually using `podman machine` from this package.
        To start a podman VM automatically at login, also install the cask
        "podman-desktop".

zsh completions have been installed to:
  /opt/homebrew/share/zsh/site-functions
```

