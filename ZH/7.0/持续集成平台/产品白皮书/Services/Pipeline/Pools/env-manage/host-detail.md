# 构建机详情查看

将你的构建机托管至 bk-ci 后，你可以在这个页面查看到构建机列表和每一台构建机的详情信息。

## 构建机列表

![png](../../../../assets/service_env_list.png)

- 在列表中，可以查阅构建机的基本信息，点击别名进入构建机详情。

## 构建机详情

![png](../../../../assets/service_env_detail.png)

构建机详情页共有 6 个功能区，对应功能如下：

1. 构建机 CPU 使用率趋势图
2. 构建机内存使用率趋势图
3. 构建机网络 IO 趋势图
4. 构建机磁盘 IO 趋势图
5. 复制安装命令：当构建机重装系统、Agent 目录被删除的场景下重新安装 Agent 时使用
6. 提供了与本构建机有关的 4 个重要信息：
   1. 基本信息：包含启动用户、安装目录、Agent 版本、最大构建任务并发数（默认为 4，防止当构建机负载过高时）等基本信息。
   2. 环境变量（即将删除）
   3. 构建任务：所有分配到本构建机的流水线 Job 都会出现在这里，在遇到任务排队时可以到这里查看具体的任务分配信息。
   4. 机器上下线记录：构建机 Agent 离线上线，都会产生一条记录在这里。
