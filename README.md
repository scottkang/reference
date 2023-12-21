# Mac JDK installation
## Mac Homebrew installation
$>/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

- Run these two commands in your terminal to add Homebrew to your PATH:
    (echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/scott/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"

## Mac Open JDK 8 installation
$>brew tap AdoptOpenJDk/openjdk
Failed 

$>brew tap homebrew/cask-versions
==> Tapping homebrew/cask-versions
Cloning into '/opt/homebrew/Library/Taps/homebrew/homebrew-cask-versions'...
remote: Enumerating objects: 270592, done.
remote: Counting objects: 100% (10129/10129), done.
remote: Compressing objects: 100% (268/268), done.
remote: Total 270592 (delta 9897), reused 10001 (delta 9861), pack-reused 260463
Receiving objects: 100% (270592/270592), 67.43 MiB | 10.30 MiB/s, done.
Resolving deltas: 100% (188121/188121), done.
Tapped 249 casks (283 files, 75MB).
$>brew install --cask adoptopenjdk8
==> Downloading https://formulae.brew.sh/api/cask.jws.json
########################################################################################################################################### 100.0%
Error: Cask adoptopenjdk8 exists in multiple taps:
  homebrew/cask-versions/adoptopenjdk8
  adoptopenjdk/openjdk/adoptopenjdk8
$>brew untap adoptopenjdk/openjdk
Untapping adoptopenjdk/openjdk...
Untapped 47 casks (69 files, 526.7KB).

Warning: adoptopenjdk8 has been deprecated because it is discontinued upstream!
==> Caveats
Temurin is the official successor to this software:

  brew install --cask temurin8

==> Downloading https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/download/jdk8u292-b10/OpenJDK8U-jdk_x64_mac_hotspot_8u292b10.pkg
==> Downloading from https://objects.githubusercontent.com/github-production-release-asset-2e65be/140418865/bbad4180-a2e0-11eb-8274-f16f6a90729c?X
########################################################################################################################################### 100.0%
==> Installing Cask adoptopenjdk8
==> Running installer for adoptopenjdk8 with sudo; the password may be necessary.
Password:
installer: This package requires Rosetta 2 to be installed.
                Please install Rosetta 2 and then try again.
                    `sudo softwareupdate --install-rosetta`

installer: Error - AdoptOpenJDK을(를) 이 컴퓨터에 설치할 수 없습니다.
==> Purging files for version 8,292,b10 of Cask adoptopenjdk8
Error: Failure while executing; `/usr/bin/sudo -u root -E LOGNAME=scott USER=scott USERNAME=scott -- /usr/sbin/installer -pkg /opt/homebrew/Caskroom/adoptopenjdk8/8,292,b10/OpenJDK8U-jdk_x64_mac_hotspot_8u292b10.pkg -target /` exited with 1. Here's the output:
installer: This package requires Rosetta 2 to be installed.
                Please install Rosetta 2 and then try again.
                    `sudo softwareupdate --install-rosetta`

installer: Error - AdoptOpenJDK을(를) 이 컴퓨터에 설치할 수 없습니다.

$>sudo softwareupdate --install-rosetta
I have read and agree to the terms of the software license agreement. A list of Apple SLAs may be found here: https://www.apple.com/legal/sla/
Type A and press return to agree: A
2023-12-21 14:06:12.882 softwareupdate[4739:48405] Package Authoring Error: 032-84877: Package reference com.apple.pkg.RosettaUpdateAuto is missing installKBytes attribute
Install of Rosetta 2 finished successfully

$>brew install --cask adoptopenjdk8    
Warning: adoptopenjdk8 has been deprecated because it is discontinued upstream!
==> Caveats
Temurin is the official successor to this software:

  brew install --cask temurin8

==> Downloading https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/download/jdk8u292-b10/OpenJDK8U-jdk_x64_mac_hotspot_8u292b10.pkg
Already downloaded: /Users/scott/Library/Caches/Homebrew/downloads/336d2dd4a6fc8c2c5a16f65fa9ff991ba34439ba280ae82088610af35ddfcbf6--OpenJDK8U-jdk_x64_mac_hotspot_8u292b10.pkg
==> Installing Cask adoptopenjdk8
==> Running installer for adoptopenjdk8 with sudo; the password may be necessary.
installer: Package name is AdoptOpenJDK
installer: Installing at base path /
installer: The install was successful.
🍺  adoptopenjdk8 was successfully installed!

## Mac JDK 17 installation

$>brew install --cask oracle-jdk17
==> Downloading https://formulae.brew.sh/api/cask.jws.json

==> Caveats
Installing oracle-jdk17 means you have AGREED to the license at:
  https://www.oracle.com/downloads/licenses/no-fee-license.html

==> Downloading https://download.oracle.com/java/17/archive/jdk-17.0.9_macos-aarch64_bin.dmg
########################################################################################################################################### 100.0%
==> Installing Cask oracle-jdk17
==> Running installer for oracle-jdk17 with sudo; the password may be necessary.
Password:
installer: Package name is JDK 17.0.9
installer: Installing at base path /
installer: The install was successful.
🍺  oracle-jdk17 was successfully installed!
$>java -version
java version "17.0.9" 2023-10-17 LTS
Java(TM) SE Runtime Environment (build 17.0.9+11-LTS-201)
Java HotSpot(TM) 64-Bit Server VM (build 17.0.9+11-LTS-201, mixed mode, sharing)

# GITHUB new machine add
ssh-keygen -t ed25519 -C "scott.kang.kr@gmail.com"

# Mysql Docker run with cases insensitive option
docker pull mysql
docker run -d --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password -e TZ=Asia/Seoul mysql --character-set-server=utf8 --collation-server=utf8_general_ci --lower_case_table_names=1

# Mysql Errors
## Public Key retrieval is not allowed( since 8.0)
Add these options to the connection string
useSSL=false&allowPublicKeyRetrieval=true
