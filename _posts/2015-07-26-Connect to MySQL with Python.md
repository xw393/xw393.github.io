---
layout: post
title: Connect to MySQL with Python
date: 2015-07-25
categories: resources how-to
tags: [Mac, R, MySQL]
---

##Connect to MySQL with Python in MAC

  **Installation environment: OS X Yosemite, Python 2.7.9**


  
  The official API MySQLdb is contained in the package `MySQL-python`. Therefore, when using `pip` to install the `MySQLdb`, just simply execute the command in Terminal:`pip install MySQL-python`.

  
### Solve an error `Reason: image not found`

  
  After installing the `MySQL-python` successfully, let's import this package in the Python to connect to MySQL database. However, an error as follows may occur:
  
 {% highlight python %}
 >>> import MySQLdb
 /Library/Python/2.7/site-packages/MySQL_python-1.2.3-py2.7-macosx-10.7-intel.egg/_mysql.py:3: UserWarning: Module _mysql was already imported from /Library/Python/2.7/site-packages/MySQL_python-1.2.3-py2.7-macosx-10.7-intel.egg/_mysql.pyc, but /Users/***/Downloads/MySQL-python-1.2.3
 is being added to sys.path
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "MySQLdb/__init__.py", line 19, in <module>
    import _mysql
  File "build/bdist.macosx-10.7-intel/egg/_mysql.py", line 7, in <module>
  File "build/bdist.macosx-10.7-intel/egg/_mysql.py", line 6, in __bootstrap__
ImportError: dlopen(/Users/***/.python-eggs/MySQL_python-1.2.3-py2.7-macosx-10.7-intel.egg-tmp/_mysql.so, 2): Library not loaded: libmysqlclient.18.dylib
  Referenced from: /Users/***/.python-eggs/MySQL_python-1.2.3-py2.7-macosx-10.7-intel.egg-tmp/_mysql.so
  Reason: image not found
 {% endhighlight %}
  
  
Don't worry. The solution is easy. Just open the terminal and execute command:  

{% highlight bash %}   
> sudo ln -s /usr/local/mysql/lib/libmysqlclient.18.dylib /usr/lib/libmysqlclient.18.dylib

> sudo ln -s /usr/local/mysql/lib /usr/local/mysql/lib/mysql
{% endhighlight %}

Then re-open your Python and import the package again, I think the problem will probably be solved. Yeah! :)
