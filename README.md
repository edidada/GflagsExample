# gflags例子
apt search libgflags-dev
libgflags-dev/focal 2.2.2-1build1 amd64

## xmake
xmake -v -y
[gflags例子 CSDN](https://blog.csdn.net/jcjc918/article/details/50876613)

### 使用命令行参数

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


### 使用文件

```shell

g++ gflags_test1.cpp -o gflags_test -lgflags -lpthread

```

`./gflags_test --flagfile server.flags`

```shell

The server host is: 10.123.14.11, the server port is: 23333
Invalid value for --port: -2
The server host is: 10.123.14.11, the server port is: 23333

```

`--flagfile server.flags`
