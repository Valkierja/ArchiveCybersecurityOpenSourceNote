需要吧Arch wiki上面的内容改改
https://wiki.archlinux.org/title/Metasploit_Framework

首先直接安装PostgreSQL
然后进PostgreSQL的用户(所有postgres的操作都要在postgres用户下进行),设置一下/var/lib/postgres 的权限(个人用的电脑建议设成0777)
此外还需要修改一下加锁的路径 建议改成/tmp (https://blog.csdn.net/banzhuangjushi/article/details/111247037)

```
# /var/lib/pgsql/9.6/data/postgresql.conf
#版本可能会变

#最下面添加
unix_socket_directories = '/tmp'
```
然后 ```initdb -D /var/lib/postgres/data```

```    pg_ctl -D /var/lib/postgres/data -l logfile start```启动数据库

此外

```
Warning:
If the database resides on a Btrfs file system, you should consider disabling Copy-on-Write for the directory before creating any database.
If the database resides on a ZFS file system, you should consult ZFS#Databases before creating any database.
```

然后安装ruby

```
#下载安装脚本并执行
curl -L get.rvm.io > rvm-install
bash < ./rvm-install
source ~/.bashrc
source ~/.zshrc
#source这两行笔者不确定,建议就都试试,或者有测试过的兄弟发起PR修改

#列出可安装版本
rvm list known
#建议安装3.0.2或者3.0.0 (本行更新于2022.4.22)
rvm install 3.0.2
#设置默认版本
rvm use 3.0.2 --default
```

然后yay安装msf
```
#在刚刚安装ruby的用户目录下(因为ruby不是全局安装的)
source ~/.rvm/scripts/rvm
gem install bundler
#注意上面这行有没有报错"未找到ruby,安装失败"之类的东西

yay -S metasploit
msfdb init --connection-string=postgresql://postgres@localhost:5432/postgres

```

然后初始化数据库

```
$ msfconsole
msf >
msf > msfdb init --connection-string=postgresql://postgres@localhost:5432/postgres

#提示需不需要初始化website,选择需要初始化('yes')
#如果没报错说明ruby环境正常
```

完成
