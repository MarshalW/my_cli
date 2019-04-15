# my cli

用于存放我自己常用的macOS命令行脚本。

我总是忘记一些命令的参数。将它们写成脚本，直接调用即可。

## 安装

下载repository：

```
git clone https://github.com/MarshalW/my_cli.git
```

可能有用到ssh配置的地方，需要配置`~/.ssh/config`等。

将clone下来的目录加入到环境变量中

## 主要功能

### 科学上网

见 [让服务器快速科学上网](https://marshal.ohtly.com/2016/11/09/using-sshutle-on-ubuntu-server/)

执行：

```
./sshuttle_run
```

需要做配置：

- 需要有一个服务器，可以ssh登陆
- 使用ssh签名，在执行脚本的终端上设置免密码登录
- ssh设置配置文件，见下面


ssh设置配置文件，`~/.ssh/config`:

```
Host *
 AddKeysToAgent yes
 UseKeychain yes
 IdentityFile ~/.ssh/id_rsa
 UseKeychain yes
 

# ssr
host ssr
HostName ${your server ip or domain}
Port ${part number}
User ${user name}
```

### 当前目录总的大小

执行：

```
./du_all_size your_path
```

### 列出当前使用的tcp端口


执行：

```
./ports
```

### 杀掉指定端口的进程

执行，杀掉`4000`端口的进程:

```
./kill_port 4000
```

## 版本历史