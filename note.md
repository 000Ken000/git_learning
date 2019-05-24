# Git 学习笔记
### 安装及配置
**安装**
官网下载安装，终端输入`git --version`检查是否安装成功及版本号
**最小配置**
` git config --global user.name "Your Name"`
` git config --global user.email"email@example.com`
`git config`命令和`--global`参数，表示对本机所有git仓库都会使用此配置。
### mac终端命令
**mac当前位置打开终端** 终端-服务-新建位于文件夹窗口的终端窗口`cmd+0`(标签页`cmd+9`)
`ls` #列出文件，list segment
`ls -ah`#显示`.git`默认隐藏目录
`cd` #进入用户主目录
`cd ~` #进入用户主目录
`cd ..` #返回上级目录
`cd ../..` #返回上两级目录
`cd learngit` #进入learngit目录(文件夹),或`cd learngit/`
`clear` # 清除终端界面所有代码
`cp`# 复制文件
`cp -R /User/用户名/Desktop/Natit.kext  /System/Library/Extensions` #把桌面的Natit.kext 拷贝到驱动目录中，参数R表示对目录进行递归操作，kext在图形界面下看起来是个文件，实际上是个文件夹
  `cp -R /System/Library/Extensions/*   /User/用户名/Desktop/backup `#把驱动目录下的所有文件备份到桌面backup
`cp ../0-material/styles/style.css.01 styles/style.css`# 把路径为/0-material/styles/目录下的styles.css文件复制到styles/目录，并命名为stylesl.css
`cat` #catenate, `$ cat foo.txt`#显示文件全部内容；
`cat > filename`#创建文件并进入编辑模式；
`cat >> filename`#对文件追加内容；
`cat foo.txt bar.txt > foobar.txt`#合并文件内容
`clear`#清空当前命令行
`echo 'xxxx'>filename`#生成文件，文件内容为xxxx
`mkdir learngit` #新建目录，make directions
`mv aaaa bbbb`#重命名，把aaaa改成bbbb(在git中，如果用mv重命名，相当于把新建新文件名的文件，同时删除旧文件名的文件，要分别再进行添加到暂存区(或删除)`git add/rm`,然后再`git commit`，比较复杂，git自带重命名`git mv`，运行后只要`git commit`就行。
`pwd` #显示当前工作目录的绝对路径,print working directory

###git 命令
`git add` # 把工作区内容提交到暂存区，add后面可以加多个文件，包括文件夹
`git add index.html images/`#把index.html文件和images文件夹提交暂存区
`git add -u` #所有工作区中被git管理的文件一起提交到暂存区
`git commit -m "xxxx"` #`git commit`是提交命令，`-m`后面输入本次提交的说明xxxxx(备注信息）单引号也行
`git commit -am"xxx"`#把工作区的修改直接提交到版本库，不经过添加到暂存区环节
`git checkout -- file`#丢弃工作区的修改全部撤销，让这个文件回到最近一次`git commit`或`git add`
`git checkout -b xxx aaa`# 创建版本号为aaa的分支，命名为xxx
 `git diff HEAD -- readme.txt`#对比工作区和版本库里最新版本的区别
`git init` #把这个目录变成git可以管理的仓库，`.git` 用户跟踪管理版本，在本地新建一个repo,进入一个项目目录,执行git init,会初始化一个repo,并在当前文件夹下创建一个.git文件夹.
`git  log` # 查看git commit历史
**git log查看版本历史**
`git log`#查看当前分支版本历史
`git log --all`#查看所有分支版本历史
`git log --all --graph`
`git log --oneline`#简洁版
`git log -n4`#查看最近4次
`git log -n4 --oneline`#查看最近4次简洁版
`git log --oneline --all`#所有版本历史简洁版
`git log --oneline --xxx`#xx分支的版本历史简洁版
`git log --oneline --all --n4`#所有版本最近4次历史简洁版
`git log --oneline --all --n4 --graph`#最近4次所有版本历史简洁图形版
`git branch -v`#查看本地多少分支，与`git branch -av`有什么区别
`git help --web log`#从浏览器打开git help关于git log的说明文档
`git push origin master`推送到github。
`git reset HEAD readme.txt`#把转存区的修改撤销掉(unstage),重新放回工作区
 `git reset --hard HEAD^`#此命令下去后，暂存区、工作目录下所有的变更都会被清除。
    - `HEAD`表示指向当前版本，`HEAD^`#上一版本，`HEAD^^`#上上版本，`HEAD~100`#上100个版本，
    - `git reset`# 版本回退命令
    - `git reset --hard commit_id`#在版本的历史之间穿梭 `git reflog`#查看命令历史，确定回到未来哪个版本
`git rm`#删除命令操作，用于删除一个文件
`git status` # 查看仓库当前状态
### vi/vim命令
mac自带vim编辑器
`vi test.txt`# 在当前目录创建test.txt文本，并打开该文本。或用`vim test.txt`，vim是vi的升级版，指令更多，功能更强。
**模式切换**
    - 从命令模式->编辑模式: i ,a , o , I , A , O 
    - 从编辑模式->命令模式: esc
    - 从命令模式->末行模式: 输入`：`
2. 模式内编辑
    - 末行模式:
        - w 保存
        - q 退出
        - ！强制退出(切换进出)
    - 命令模式
        - hjkl控制上下移动
        - m中间位置
        - l 当前屏幕的最后一行
**一般模式：删除、复制与粘贴类命令**
**编辑模式命令**
`i,I` #i为在当前光标所在处插入输入的文字，I为在光标所在行第一个非空字符插入输入的文字
`a,A` # a为在当前光标所在处下一个字符插入输入的文字，A为在光标所在行最后一个字符的下一个字符处插入输入的文字
`o,O ` # o为在光标所在行的下一行行首开始插入字符，O为在光标所在行的上一行行首开始插入字符
`r,R `# r为替换光标所在那一个字符，R为一直替换光标所指的文字，直到退出
`Esc`#退出，回到一般模式
**输入模式**
在命令模式下按下 i 就进入了输入模式
在输入模式中，可以使用以下按键：
`ENTER`# 换行
`BACK SPACE`# 删除光标前一个字符
`方向键 ` # 在文本中移动光标
`HOME/END`# 移动光标到行首/行尾
`Page Up/Page Down`#上/下翻页
`ESC`退出输入模式，切换到命令模式
**底线命令模式**
在命令模式下按下 `:`（英文冒号）就进入了底线命令模式。
底线命令模式可以输入单个或多个字符的命令，可用的命令非常多。
在底线命令模式中，基本的命令有（已经省略了冒号）：
    `q`# 退出程序
    `w` # 保存文件
    按`ESC`键可随时退出底线命令模式
**一般模式切换到指令行模式**
`:w ` # 将编辑的数据写入硬盘档案中
` :w!` # 强制将编辑的数据写入硬盘档案中
 `:q ` # 离开
 `:q!` # 为强制离开不储存档案
 `:wq ` # 储存后离开
`:wq!` # 强制储存后离开
 `:set nu ` # 显示行号，设定之后，会在每一行的前缀显示该行的行号
`:set nonu `# 取消行号

### 创建仓库
repository #仓库
`mkdir learngit` #新建目录，make directions
`cd learngit` #进入learngit目录(文件夹)
`git init` #把这个目录变成git可以管理的仓库，`.git` 用户跟踪管理版本
### 把文件添加到仓库
**在`learngit`目标下编写一个`readme.txt`文件**
1. `pwd`
2. `vi readme.md` # 在当前目录下创建readme.md文本，vi是vim编辑器语言，mac系统自带vim编辑器
3. `git add readme.txt`  #把新创建的reademe.md从工作区提交到暂存区
4. `git commit -m "wrote a readme file"` #`git commit`是提交命令，`-m`后面输入本次提交的说明，


### 工作区和暂存区
**概念理解**
- 工作区(working directory):电脑的目录，如`learngit`文件夹是一个工作区。
- 版本库(repository): 工作区有一个隐藏目录`.git`，是git 的版本库。git版本库存有很多内容:
    - stage(或叫index)暂存区
    - git自动创建的第一个分支`master`
    - 指向`master`的指针`HEAD`
![](/_images/2019-04-29/2019-04-30-09-35-58.png)
- 把文件往git版本库添加，两步骤:
    1. `git add`把文件添加到暂存区；`git add -u`#把当前git管理的所有工作区内容添加到暂存区
    2. `git commit`把暂存区**所有内容**提交到当前分支。
    3. `git mv`#重命名，运行后只要`git commit`就行
**任务**
1. `readme.txt`做个修改
2. 在工作区新增一个`LICENSE`文件文件
3. `git add`添加到暂存区，`git commit`提交，`git status`查看状态
**操作**
1. `vi readme.txt`#打开编辑文本，保存退回命令模式；
2. `vi LICENCE`#创建新文本，保存退回命令模式；
3. `git status`#查看当前状态
4. `git add LICENCE`#把新创建文本添加到暂存区
5. `git add readme.txt`#把修改后的文本添加到暂存区
6. `git status`#查看当前状态
7. `git commit -m"understand how stage works`
8. `git status`
###管理修改
**概念**
- git 管理的是修改，而不是文件。
**任务**
- 以`readme.txt`进行修改、添加、再修改、提交操作，查看状态，对比工作区和版本库的区别
**操作**
1. `vi readme.txt`#修改内容
2. `cat readme.txt`#查看文件内容
3. `git add readme.txt`#添加内容
4. `git status`#查看状态
5. `vi readme.txt`#再添加内容
6. `git commit -m"git tracks changes`#提交内容
7. `git status`#查看状态
8. `git diff HEAD -- readme.txt`#对比工作区和版本库里最新版本的区别
### 撤销修改
**概念**
- `git checkout -- file`#丢弃工作区的修改全部撤销，让这个文件回到最近一次`git commit`或`git add`, 含以下两种情况：
    1. 修改后还没放到暂存区，撤销后回到和版本库一样的状态
    2. 已经添加到暂存区，又作了修改，撤销修改就回到添加到暂存区的状态
- `git reset HEAD <file>`#把暂存区修改丢弃回工作区，再用`git checkout --file`丢弃
- 版本已提交，请参考### 版本控制
**操作**
1. `vi readme.txt`#编辑保存
2. `git status`#查看状态
3. `git checkout -- readme.txt`#丢弃工作区修改
4. `cat readme.txt`#查看文件内容
5. `vi readme.txt`#编辑修改保存
6. `cat readme.txt `#查看文件内容
7. `git add readme.txt`#添加到暂存区
8. `git status`#查看状态
9. `git reset HEAD readme.txt`#把转存区的修改撤销掉(unstage),重新放回工作区
10. `git checkout -- readme.txt`#丢弃工作区的修改内容
11. `git status`#查看状态
12. `cat readme.txt`#查看文件内容
### 删除文件
**概念**
- `git rm`#删除命令操作，用于删除一个文件,思考，删除一个目录怎么输入？
**操作**
- `ls` #列出当前目录文件名
- `vi test.txt`#创建添加test文本
- `ls`#列出当着文件名
- `git add test.txt`#添加文件到暂存区
- `git commit test.txt`#提交文
- `rm test.txt`#在工作区删除test文本,(属常规mac命令行操作？)
- `git status`#s查看状态
- `git rm test.txt`# 添加删除操作到暂存区
- `git commit -m"remove test.txt`#提交删除操作到版本库
- `git status`#查看状态
- `ls`#列出文件名
### 版本控制
**概念**
比喻：版本的时光穿梭机
**修改`readme.txt`内容**
1. `vi readme.txt`#打开`readme.txt`文件，修改后，`esc`退出编辑模式，输入`:wq!`回车# 强制储存后退出。
2. `git status`#查看仓库当前状态
3. `git diff` #工作区与暂存区的对比，查看具体修改内容，diff=difference
4. `git add readme.txt`
5. `git status`
6. `git commit -m"add distributed"`
7. `git status`
**版本回退**
1. `vi readme.txt` #打开文件编辑，输入`i`进入文件编辑模式，按`esc`退出编辑模式， 末行输入`: wq!`回车，强调保存并退出文件模式，返回命令模式 
2. `git add readme.txt`
3. `git commit -m"append GPL"`
4. `git log`#查看版本提交历史，确定回退到哪个版本
5. `git log --pretty=oneline`
6. `git reset --hard HEAD^`#此命令下去后，暂存区、工作目录下所有的变更都会被清除。
    - `HEAD`表示指向当前版本，`HEAD^`#上一版本，`HEAD^^`#上上版本，`HEAD~100`#上100个版本，
    - `git reset`# 版本回退命令
    - `git reset --hard commit_id`#在版本的历史之间穿梭
7. `git reflog`#查看命令历史，确定回到未来哪个版本


### 远程仓库
**操作**
1. 创建SSH Key: `ssh-keygen -t rsa -C "youremail@example.com"`
2. 登陆GitHub,打开"Account settings","SSH Keys"页面
**添加远程库**
1. 登陆GitHub,创建'"learngit"新仓库
2. 把GitHub上的新仓库与本地仓库关联：`$ git remote add origin git@github.com:000Ken000/learngit.git`
3. 把本地库的所有内容推送到远程库: `$ git push -u origin master `#本地内容推送到远程用`git push`命令(实际是把当前`master`推送到远程)，因远程库是空的，第一次推送`master`分支时，加上`-u`参数，相当把本地内容推送到远程新`master`分支，且把本地`master`分支和远程`master`分支关联起来，以后推送或拉取就可简化命令。
4. SSH警告: 第一次使用git 的`clone`或`push`命令连接github时，会有一警告，输入`yes`回车
5. 从现在起，只要本地作了提交，可以通过命令:`$ git push origin master`推送到github。
**概念**
- 要关联一个远程库，使用命令`git remote add origin git@github.com:000Ken000/learngit.git`
-  关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容
- 上线后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改
**从远程库克隆**
- 登陆GitHub，创建一个新仓库`gitskill`，勾选`initialize this repository with a README`
- 在电脑本地合适目录用命令`git clone`克隆 一个本地库:`$ git clone git@github.com:000Ken000/gitskill.git`
- 进入`gitskill`目录查看文件:`$ cd git skill`,`ls`
**概念**
- 要克隆一个仓库，首先必须知道仓库的地址，然后用`git clone`命令克隆。
- git支持多种协议，包括`https`,但通过`ssh`支持的原生`git`协议速度最快。(使用`https`速度慢，每次推送必须输入口令)
**思考**
- 仓库及目录重命名
- 移动仓库及目录文件
- 让本地Share、Blog仓库与github远程仓库关联
    - `git push origin master:master`
    - 输入github登陆口令
    - 把git 连接协议从https改成SSH`git remote set-url origin git@github.com:000Ken000/Share.git`
![](/_images/2019-04-30/2019-04-30-16-32-35.png)
- 本地删除仓库及目录文件，同步远程
    - 删除`gitskill`本地仓库，再同步`push`到远程库
    - `pwd`
    - `cd ..`
    - `git branch`#显示当前目录所有分支
    - `git init`#初始化本地版本库
    - `ls -a`#找到目录下.git
    - `rm -rf .git`#删除目标目录下的.git文件
    - `pwd`,`cd ..` #返回上一级目录
    - `rm -rf gitskill`#删除gitskill文件夹
    - `git rm gitskill`
    - `ls` `git status`
    - `git commit -m"remove gitskill`
    - `git status` `ls`
    - `git remote rm origin git@github.com:000Ken000/gitskill.git`
**补充**
`git diff`#对比工作区与暂存区
`git diff --cached`#对比暂存区与HEAD
 对多个文件进行命令操作，用英文空格隔开
`git log -n8`# 查看最近8个commit记录
### .gitignore
指定不需要git管理的文件
**操作**
- `vi .gitignore`

### 解读git返回代码
`1 file changed`#一个文件被改动；
`2 insertions`#插入两行内容
### 问题思考
- git log --oneline返回结果后，在复制输入代码后发现粘贴太多，分行了，无法删除
![](/_images/2019-04-30/2019-05-24-09-27-18.png)

- **思考**
为什么git添加文件需要`add`和`commit`两步 #`commit`可以一次提交多文件，所以可多次`add`不同文件。

