# go-telnet

[![Build Status](https://travis-ci.org/mtojek/go-telnet.svg?branch=master)](https://travis-ci.org/mtojek/go-telnet)

Status: **Work in progress**

Read bytes from stdin and pass them to the remote host. The application works similarly to the well known telnet application, but it lets you read an input from standard input and wait for response.

### Problem Description 

Old telnet does not work in that manner and it requires a script based on _expect_ command. Trying an intuitive solution would end like that:

~~~
$ cat resources/input-data/wp.pl_1.bin | telnet www.wp.pl 80
Trying 212.77.100.101...
Connected to www.wp.pl.
Escape character is '^]'.
Connection closed by foreign host.
~~~

The same execution of _go-telnet_ ends with a received server response.
~~~
cat resources/input-data/wp.pl_1.bin | go-telnet www.wp.pl 80
~~~

