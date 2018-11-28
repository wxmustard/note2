# mkdocs + github

- 安装mkdocs
> 首先安装Python
```bash
sudo pip install mkdocs
```

- 配置github 仓库
> 在github上创建仓库，note2
```bash
git clone git@github.com:wxmustard/note2.git
```
- 设置mkdocs项目
```bash
cd note2
mkdocs new .
# 自动生成 docs（文档主目录）  mkdocs.yml（配置文件）
```
- 创建笔记md文件
```bash
# docs
#├── help
#│   └── start.md
#├── index.md
#└── python
#    └── Chapter7.md
```
- 建立索引
```bash
vim mkdocs.yml
site_name: Mustard's docs
theme:
    name: 'material'
nav:
    - 'help':
        - '快速开始': 'help/start.md'
    - 'python notes':
        - '数据结构': 'python/Chapter7.md'

- 本地浏览（/调试）
​```bash
mkdocs serve
# 打开浏览器输入http://127.0.0.1:8000
```

- 发布
```bash
mkdocs gh-deploy --clean
#　--clean　清理不存在的文件
```

- 更新远程仓库并浏览docs文档
> push.sh    
>
> !/bin/bash
>
> git status
> git add -A
> git commit -m  $1
> git push origin master
```bash
./push docs
# 访问：　https://wxmustard.github.io/note2/
# https://（github用户名）.github.io/（远程仓库名）/
```