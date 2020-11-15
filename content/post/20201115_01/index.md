---
title: CentOS7에서 Python3.7 설치
description:  
date: 2020-09-09
categories:
    - linux
---
CentOS7에서는 기본으로 Python3.7이 없다. yum을 통해 설치하려해도 Python 3.6뿐이다.
아래는 직접 다운로드 하여 컴파일 설치하는 방법이다.

> Root 권한으로 진행합니다.

#### 1. 설치전 필요한 패키지 설치

```bash
yum install gcc openssl-devel bzip2-devel libffi-devel zlib-devel -y
```

#### 2. 다운로드 & 설치

```bash
# Download & Decompress
cd /usr/src
wget https://www.python.org/ftp/python/3.7.9/Python-3.7.9.tgz
tar xzf Python-3.7.9.tgz

# Create makefile & make
cd Python-3.7.9
./configure --enable-optimizations
make altinstall

# remove installation file
rm /usr/src/Python-3.7.9.tgz
```

#### 3. 버전 확인

설치된 Python3.7.9의 버전을 확인한다.

```bash
python3.7 -v

[root@localhost src]# python3.7
Python 3.7.9 (default, Nov 15 2020, 00:09:28)
[GCC 4.8.5 20150623 (Red Hat 4.8.5-44)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()
```

