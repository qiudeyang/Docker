# 3-安装
   这里以Centos6.7为例安装`Docker`。系统要求是64	位操作系统,内核版本至少为	3.10。如果你的内核版本低了，可参照这篇[博文](http://blog.csdn.net/u012449486/article/details/52138547)解决。

   首先添加yum软件源，在`/etc/yum.repos.d/`目录下新建一个repo文件，比如：docker.repo。添加以下内容：

[dockerrepo]

name=Docker	Repository

baseurl=https://yum.dockerproject.org/repo/main/centos/$releasever/

enabled=1

gpgcheck=1

gpgkey=https://yum.dockerproject.org/gpg

这里需注意两点：（1）你的服务器必须能连外网；（2）把$releasever改成你对应的版本，这里我设置为6，如果是Centos7.x版本，则需要改成7。

接下来是更新yum软件源缓存,并安装docker-engine。

yum update

yum -y install docker-engine

注：如果没有特殊说明，此文档所出现的命令均以`root`用户执行。

上述步骤完成后，可输入`docker`检查是否安装成功，同时设置让Docker服务开机自启动

`chkconfig docker on`

同时需要执行命令`service docker start`启动Docker服务，至此安装部分全部完成。
