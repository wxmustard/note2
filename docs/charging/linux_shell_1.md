# linux_shell

##小试牛刀

### shell脚本

- `#!/bin/bash` (称为`shebang`，用于告知系统使用什么方式执行)
- `#`注释直至末尾

运行方式

- 没有`shebang`, 执行 bash test.sh
- 有`shebang`,添加执行权限
  - chmod 755 test.sh
  - chmod a+x test.sh
  - 执行
    - ./test.sh
    - /home/test.sh

> echo 自动会在末尾添加换行符，-n 去除换行， -e 包含转意序列的字符串如“1\t2\t\3”
>
> 彩色打印： echo -e "\e[1;31m This is red text \e[0m"  `\e[1;31m`换成红色
>
> 文本：重置=0，黑色=30，红色=31，绿色=32，黄色=33，蓝色=34，洋红=35，青色=36，白色=37
>
> 背景：重置=0，黑色=40，红色=41，绿色=42，黄色=43，蓝色=44，洋红=45，青色=46，白色=47

