---
title: "Python 解决 InsecurePlatformWarning: A true SSLContext object is not available."
cover: /images/article/python.jpg
excerpt: 在安装Python库的时候，遇到一些问题。虽然，还是遇到问题了 Collecting PyMySQL /Users/fdhuang/py27/lib/python2.7/site-packages/pip/_vendor/requests/packages/urllib3/util/ssl_.py:79 InsecurePlatformWarning A true SSLContext object is not
categories:
  - Python
---
### 在安装Python库的时候，遇到一些问题。虽然，还是遇到问题了:

``` code
Collecting PyMySQL
/Users/fdhuang/py27/lib/python2.7/site-packages/pip/_vendor/requests/packages/urllib3/util/ssl_.py:79: InsecurePlatformWarning: A true SSLContext object is not available. This prevents urllib3 from configuring SSL appropriately and may cause certain SSL connections to fail. For more information, see https://urllib3.readthedocs.org/en/latest/security.html#insecureplatformwarning.
  InsecurePlatformWarning
  Downloading PyMySQL-0.6.6-py2.py3-none-any.whl (66kB)
    100% |████████████████████████████████| 69kB 225kB/s
Installing collected packages: PyMySQL
Successfully installed PyMySQL-0.6.6
```
### 因为SSL的问题，urllib3需要pyopenssl。
最简单的方法是
``` bash
$ pip install pyopenssl ndg-httpsclient pyasn1
```
还需要安装libffi-dev，libssl-dev

### Ubuntu下安装

``` bash
$ sudo apt-get install libffi-dev libssl-dev
```
