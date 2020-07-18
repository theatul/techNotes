---
title: "How to install python 3.8 on Amazon linux."
date: 2020-05-25T00:05:40+05:30
draft: false

tags: [
    "python 3.8",
    "Amazon Linux",
    "Install Python 3.8",
]

---

Steps to install Python 3.8 on amazon linux.
<!--more-->

Install dependencies first.

```
# yum install gcc openssl-devel bzip2-devel libffi-devel
```

Download Python source from:

```
# wget https://www.python.org/ftp/python/3.8.3/Python-3.8.3.tgz
```

Extract the tarball:
```
# tar -xzvf Python-3.8.3.tgz
```

Installl python:

```
# cd Python-3.8.3
# sudo ./configure --enable-optimizations
# sudo make altinstall
```

And you are done, now you can delete python tarball.

```
# rm  -f Python-3.8.3.tgz
```
