# Author： lixm@lixm.cc
# Date: 2019-07-29
# Addr： NO.1 Huajing Road, Chian(Shanghai) Pilot Free Trade Zone

## WordPress+Apache+PHP+MariaDB Deployment

- Requires Ansible 1.2 or newer
- Expects CentOS/RHEL 7.x host/s

RHEL7 version reflects changes in Red Hat Enterprise Linux and CentOS 7:
1. Network device naming scheme has changed
2. iptables is replaced with firewalld
3. MySQL is replaced with MariaDB

These playbooks deploy a simple all-in-one configuration of the popular
WordPress blogging platform and CMS, frontend by the Nginx web server and the
PHP-FPM process manager. To use, copy the `hosts.example` file to `hosts` and 
edit the `hosts` inventory file to include the names or URLs of the servers
you want to deploy.

Then run the playbook, like this:

	ansible-playbook -i hosts site.yml

The playbooks will configure MariaDB, WordPress, Nginx, and PHP-FPM. When the run
is complete, you can hit access server to begin the WordPress configuration.

### Ideas for Improvement

Here are some ideas for ways that these playbooks could be extended:

- Parameterize the WordPress deployment to handle multi-site configurations.
- Separate the components (PHP, MySQL, ) onto separate hosts and 
handle the configuration appropriately.
- Handle WordPress upgrades automatically.

## LAMP + Wordpress安装步骤
1. 安装EPELyum源
2. 关闭SELinux
3. 安装Apache
4. 安装PHP7.2
5. 安装MariaDB数据库
6. 下载Wordpress安装包并解压缩
7. 生成Wordpress配置文件并部署
8. 重启httpd服务
9. 使用浏览器前端配置