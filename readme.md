#                              Docker

[toc]

## 容器的组成

- 一个容器是由3个组件组成

1.  一个能够运行docker的image
2. 一个可执行的环境
3. 一套标准指令集

- Docker将OS操作系统及docker的应用程序当作运输集装箱的船只。而将一个一个的container，做为运送货物的集装箱。

## Linux Namespace

- LCX 所实现的隔离性主要是来自kernel的namespace，其中pid,net,ipc,mnt,uts等namespace将container的进程，网络，消息，文件系统和hostname隔离开。

  | Namespace | 系统调用参数  | 隔离内容                   |
  | --------- | ------------- | -------------------------- |
  | UTS       | clone_newuts  | 主机名与域名               |
  | IPC       | clone_newipc  | 信号量、消息队列和共享内存 |
  | PID       | clone_newpid  | 进程编号                   |
  | Network   | clone_newnet  | 网络设备、网络栈、端口     |
  | Mount     | clone_newns   | 挂载点（文件系统）         |
  | User      | clone_newuser | 用户和用户组               |

- NAT转换

  真正意义上节约IP地址，实际中应用最多的NAT方式

- PAT转换端口地址转换

  如果不同主机的数据包端口号相同，则一定发生端口转换

