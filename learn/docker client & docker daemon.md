# Client & Daemon

[toc]

## Client 与 Server交互方式

- -H
  - --host=[unix:///var/run/docker.sock]
  - tcp://[host]:[port][path] to bind
  - unix://[/path/to/socket]
  - 如果是tcp的方式进行连接，没有开启tls加密，则是2375号端口，如果开启了tls加密，则是2376号端口。

## Docker Client 

![architecture](/../main/pic/dk_architecture.png)

- ***Docker Client Options***

  | option                                           | description                                              |
  | ------------------------------------------------ | -------------------------------------------------------- |
  | --config=""                                      | 指定配置文件位置，默认为/.docker                         |
  | -D,--debug=true\|false                           | 是否开启诊断功能，默认关闭的，会产生大量的日志信息       |
  | -H                                               | 后面接socket 或者tcp的IP地址跟端口，指定连接到哪个Daemon |
  | -I,--log-level="debug\|info\|warn\|error\|fatal" | 指定日志级别，默认的日志级别为"info"                     |
  | --tls=true\|false                                | 默认关闭，是否开启tls认证                                |
  | --tlscacert=/.docker/ca.pem                      | 指定tls根证书位置                                        |
  | --tlscert=/.docker/cert.pem                      | 指定docker的证书位置                                     |
  | --tlskey=/.docker/key.pem                        | 指定密钥位置                                             |
  | --tlsverify=true\|false                          | 与tls一样，验证远端服务器的证书                          |
  | -v, --version=true\|false                        | 查看docker的版本信息                                     |

- ***Docker的语法构成***

  - docker [OPTIONS]  COMMAND [ARG...]

  - docker Management Commands ARG

    



## Docker Daemon

- man dockerd