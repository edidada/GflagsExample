# 

```shell

g++ gflags_test.cc -o gflags_test -lgflags -lpthread

```

`./gflags_test`

`./gflags_test -host 10.123.78.90`

`./gflags_test -port 8008`

`./gflags_test -host 10.123.78.90 -port 8008`

`./gflags_test --host 10.123.78.90 --port 8008`

`./gflags_test --host=10.123.78.90 --port=8008`

`./gflags_test --help`

``



```shell

g++ gflags_test1.cpp -o gflags_test -lgflags -lpthread

```

`./gflags_test --flagfile server.flags`

```shell

The server host is: 10.123.14.11, the server port is: 23333
Invalid value for --port: -2
The server host is: 10.123.14.11, the server port is: 23333

```