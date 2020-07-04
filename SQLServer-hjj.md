SQL Server2016
=================
任务名称：安装SQL Server2016
任务提交者：hujunjie
-----------------  

# 安装说明
## CentOS
## 下载sqlserver2016的源
  curl -o /etc/yum.repos.d/mssql-server.repo https://packages.microsoft.com/config/rhel/7/mssql-server-2017.repo
## 更新包并且下载
  yum update && yum install -y mssql-server
## 运行SQL Server选择版本设置密码
  /opt/mssql/bin/mssql-conf setup
### 从1-8选择版本，选择语言，设置sa密码
## 查看SQL Server是否成功启动
  systemctl status mssql-server
### 如果出现running，则启动成功.
### 至此SQL Server安装完毕

