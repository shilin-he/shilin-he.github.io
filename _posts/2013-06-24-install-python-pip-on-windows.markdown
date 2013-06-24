---
layout: post
title:  "Install Python pip on Windows"
date:   2013-06-24 14:31:00
categories: Python Pip
---

1. Download [setuptools][st] and extract it into a folder, then run the 
following command:

    > setup.py install

2. Download [pip][pip] and extract it into a folder, then run the following
command:

    > setup.py install 

3. Add "C:\Python27\Scripts" into the PATH environment variable

If you installed Perl for windows, the pip in Perl might conflict with the
Python pip. 

[st]: https://pypi.python.org/pypi/setuptools/0.7.4
[pip]: https://pypi.python.org/pypi/pip/1.3.1

