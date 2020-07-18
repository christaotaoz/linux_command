useradd

用法：useradd [选项] 登录
      useradd -D
      useradd -D [选项]

选项：
  -b, --base-dir BASE_DIR       新账户的主目录的基目录
  -c, --comment COMMENT         新账户的 GECOS 字段
  -d, --home-dir HOME_DIR       新账户的主目录
  -D, --defaults                显示或更改默认的 useradd 配置
 -e, --expiredate EXPIRE_DATE  新账户的过期日期
  -f, --inactive INACTIVE       新账户的密码不活动期
  -g, --gid GROUP               新账户主组的名称或 ID
  -G, --groups GROUPS   新账户的附加组列表
  -h, --help                    显示此帮助信息并推出
  -k, --skel SKEL_DIR   使用此目录作为骨架目录
  -K, --key KEY=VALUE           不使用 /etc/login.defs 中的默认值
  -l, --no-log-init     不要将此用户添加到最近登录和登录失败数据库
  -m, --create-home     创建用户的主目录
  -M, --no-create-home          不创建用户的主目录
  -N, --no-user-group   不创建同名的组
  -o, --non-unique              允许使用重复的 UID 创建用户
  -p, --password PASSWORD               加密后的新账户密码
  -r, --system                  创建一个系统账户
  -R, --root CHROOT_DIR         chroot 到的目录
  -s, --shell SHELL             新账户的登录 shell
  -u, --uid UID                 新账户的用户 ID
  -U, --user-group              创建与用户同名的组
  -Z, --selinux-user SEUSER             为 SELinux 用户映射使用指定 SEUSER

passwd --help
用法: passwd [选项...] <帐号名称>
  -k, --keep-tokens       保持身份验证令牌不过期
  -d, --delete            删除已命名帐号的密码(只有根用户才能进行此操作)
  -l, --lock              锁定指名帐户的密码(仅限 root 用户)
  -u, --unlock            解锁指名账户的密码(仅限 root 用户)
  -e, --expire            终止指名帐户的密码(仅限 root 用户)
  -f, --force             强制执行操作
  -x, --maximum=DAYS      密码的最长有效时限(只有根用户才能进行此操作)
  -n, --minimum=DAYS      密码的最短有效时限(只有根用户才能进行此操作)
  -w, --warning=DAYS      在密码过期前多少天开始提醒用户(只有根用户才能进行此操作)
  -i, --inactive=DAYS     当密码过期后经过多少天该帐号会被禁用(只有根用户才能进行此操作)
  -S, --status            报告已命名帐号的密码状态(只有根用户才能进行此操作)
  --stdin                 从标准输入读取令牌(只有根用户才能进行此操作)

Help options:
  -?, --help              Show this help message
  --usage                 Display brief usage message