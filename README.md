# OpenWrt-Builder

OpenWrt-Docker Image Builder
确保网络科学，并开启全局！
确保docker空间充足，否则可能空间不足无法构建（至少1G以上）

创建普通用户：

BASHCopy
opkg update                                            # 更新软件包列表
opkg install sudo shadow-useradd                       # 安装必要软件
useradd -m -s /bin/ash qcy                             # 创建用户
passwd qcy                                             # 设置密码
echo "qcy ALL=(ALL) ALL" >> /etc/sudoers               # 添加sudo权限
退出root 用普通用户登录（su命令在这不生效，直接退出重进）

编辑好构建脚本
构建脚本放入用户目录home/name下

用户目录递归777权限

进入脚本目录开始构建

cd /home/…..

sudo ./docker-build.sh

输入普通用户密码

Linux-Docker Image Builder
安装好Linux，登录root账号、网络科学环境

安装sudo、curl、docker

BASHCopy
apt update
 
sudo apt install sudo curl
 
curl -fsSL https://get.docker.com | bash -s docker
普通用户给sudo权限（name修改为实际用户名）

BASHCopy
echo "name ALL=(ALL) ALL" | sudo EDITOR='tee -a' visudo
切换到普通用户（name修改为实际用户名）

UNDEFINEDCopy
su name
编辑好构建脚本
构建脚本放入用户目录home/name下

用户目录递归777权限

进入脚本目录开始构建

cd /home/…..

sudo ./docker-build.sh

输入普通用户密码
