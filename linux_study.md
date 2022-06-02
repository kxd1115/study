# Linux学习笔记

## 1. 切换软件源

1. 切换之前先备份之前的配置文件

```
$ sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
```

2. 找到国内使用的源

```
-- 清华源为例
https://mirrors.tuna.tsinghua.edu.cn/help/ubuntu/
```

3. 替换掉原来的源

```
$ sudo vi /etc/apt/sources.list
```

4. 更新软件包缓存

```
$ sudo apt update
```

5. 更新本地软件

```
$ sudo apt-get upgrade
```

## 2. 安装常用软件

1. vim

```
$ sudo apt-get install vim
```

2. gcc/g++

```
$ sudo apt-get install gcc
$ sudo apt-get install g++
```



## 3. git地址

```
cd /mnt/hgfs/code_share/study
```



## 4. 打开hosts文件

```
sudo gedit /etc/hosts
```



### 5. 关于网络问题

**问题分析：如果只看到\**lo\**这个名字的数据，说明网卡还没驱动或者没有添加网卡**

**解决方法：安装无线网卡即可**

```
sudo lshw -numeric -class network
sudo route -nv
sudo dhclient -v**
```



