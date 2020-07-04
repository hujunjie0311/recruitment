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
    /opt/mssql/bin/mssql-conf setup 从1-8选择版本，选择语言，设置sa密码
## 查看SQL Server是否成功启动
    systemctl status mssql-server
### 如果出现running，则启动成功.至此SQL Server安装完毕  

## 下载SQL Server命令行工具
### 下载sqlcmd源
    curl -o /etc/yum.repos.d/msprod.repo https://packages.microsoft.com/config/rhel/7/prod.repo  
## 更新包并且下载工具
     yum update && yum install -y mssql-tools unixODBC-devel
## 添加环境变量
    echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bash_profile  
    echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bashrc  
    source ~/.bashrc  
## 使用sqlcmd工具本地连接，输入之前设置的密码即可
    sqlcmd -S localhost -U SA  
## 如果显示出了1>，则可以使用了
