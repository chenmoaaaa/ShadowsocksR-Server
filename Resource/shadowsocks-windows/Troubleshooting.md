# Troubleshooting/问题解决方法

* Although it is an old topic, please double check your configurations./老调重弹，请仔细检查你的配置文件。

* Upgrade your .NET Framework to latest release and install all patches against it./升级系统的 .NET Framework 为最新版本，并且打全相关补丁。

* Upgrade to latest operating system and IE if possible. If you are using Windows Insider Preview, please consider report bugs to Microsoft first./尽可能升级操作系统和 IE 到最新版。如果使用预览版Windows，考虑先给微软汇报bug。

* If you put executable file in C: drive, please grant Administrative permission in case of privilege issues./如果在 C 盘运行本程序，请授予管理员权限以防引发权限问题。

* When the format of configuration file has changed, it may cause some issues, please delete all config files and restart to generate new config files, you have to reset from scratch./当配置文件格式发生变化时，可能引发问题，这时删掉所有相关配置文件让程序重新生成，然后手动重新配置。

* Shadowsocks places files in `ss_win_temp/` folder, if you encountered issues, you can delete the corresponding folder and try again. Please note that some 'security' software will clean up them without notice./Shadowsocks 在可执行文件同目录的 `ss_win_temp/` 文件夹放置程序需要的文件，如果遇到问题，可以尝试删除对应文件夹然后重试。请注意，有些“安全”软件会静默清理那些目录。

* Firewall may block traffic made by Shadowsocks, check it./防火墙可能屏蔽 Shadowsocks 的流量，检查防火墙规则。

* Some game accelerator and software works on the underlying layer (e.g. LSP) may interfere Shadowsocks, please report issues to them./有些游戏加速器和运行在网络底层（比如LSP）的软件可能会干扰 Shadowsocks，请将问题汇报给他们。

* You can also get bleeding edge version from Continuous Integration(e.g. AppVeyor), and test your issue again. Please note that do NOT use builds belong to Pull Requests./你也可以从CI处获取最新版本（比如 AppVeyor）测试你遇到的问题，请注意**不要**使用属于Pull Request的自动编译版本。
