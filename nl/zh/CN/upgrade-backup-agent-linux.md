---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 升级 Linux 的备份软件代理程序
{: #UpgradeinLinux}

最新的备份代理程序可以从 {{site.data.keyword.backup_notm}} 门户网站仪表板快速链接部分进行下载。
{:tip}

按照升级过程步骤执行操作，这样可以确保升级 {{site.data.keyword.backup_notm}} 代理程序而又不会丢失注册

1. 以 root 级别的身份登录到主机。
2. 下载最新版本的代理程序。
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-x64-8.11.5251.tar.gz2
   ```
   {:pre}

3. 对已下载文件的内容进行解压缩。

   ```
   tar -xzvf Agent-Linux-x64-8.11.5251.tar.gz3
   ```
4. 转至最近的安装目录。
   ```
   cd Agent-Linux-x64-8.11.5251/4
   ```

5. 运行安装脚本。
   ```
   ./install.sh
   ```
   {:pre}

6. 通过选择您的语言回答提示，选择 `N` 表示不将计算机注册为新主机，选择 `A` 以使用集成加密方法加密数据。

7. 如果安装成功，那么信息将记录在 `/opt/BUAgent/Install.log` 中。
