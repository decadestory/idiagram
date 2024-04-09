---
toc:
  depth_from: 1
  depth_to: 6
---

# 仓库源等国内代理地址

## 一、GOPROXY
```shell
# 七牛
go env -w GOPROXY=https://goproxy.cn,direct
# 阿里云
go env -w GOPROXY=https://mirrors.aliyun.com/goproxy/,direct
# 官方
go env -w  GOPROXY=https://goproxy.io,direct
```

## 二、NPM
```shell
npm config set registry https://registry.npm.taobao.org
```

## 三、Android SDK Manager
```shell
# 中国科学院开源协会镜像站
http://mirrors.opencas.cn
# 上海GDG镜像服务器
http://sdk.gdgshanghai.com
# 北京化工大学镜像服务器
http://ubuntu.buct.edu.cn
# 大连东软信息学院镜像服务器
http://mirrors.neusoft.edu.cn
# 腾讯Bugly
http://android-mirror.bugly.qq.com
```

## 四、maven国内源
```shell
# 阿里云
http://maven.aliyun.com/
# 中央仓库
https://repo1.maven.org/maven2/
# 网易
http://maven.netease.com/repository/public/
# 华为云
https://repo.huaweicloud.com/repository/maven/
# tencent
https://mirrors.cloud.tencent.com/repository/maven/
```

## 五、pip国内源
```shell
# 清华大学
https://pypi.tuna.tsinghua.edu.cn/simple
# 阿里云
http://mirrors.aliyun.com/pypi/simple
# 豆瓣
http://pypi.douban.com/simple/
```

## 六、yum国内源
```shell
# 阿里的yum源
curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
# mysql8
rpm -Uvh https://dev.mysql.com/get/mysql80-community-release-el7-7.noarch.rpm
```