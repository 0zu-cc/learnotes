# 极富盛名的分布式VCS

>相关名词  
>1.分支branch与合并merge:分支从原版本拷贝分离出来,**在合并之前与原版本完全独立**  
>2.存储库**repo**(repository),**serve**(存储repo的主机),**client**(连接repo的主机)  
>3.编辑改动对比**diff**,标记**tag**和取出**checkout**

### 0.核心认知:  
**对git来说,每个人的工作区(目录)都是一个完整的存储库**  
**<font color=#69bfff>本地仓库: 版本库.git的上一级文件夹  
暂存区index/stage: 版本库.git下的index文件(2进制)  
版本记录区HEAD: 版本库下的HEAD文件
</font>**<br>
master　　默认分支(除master外其他分支一般可任意命名)  
<font color=red>各分区之间互不影响</font>

### <font color=#69bad9>1.基本命令(IDE中都是按钮/选项)</font>
|命令|含义|
|:-|-|
|**git config --list** |列出所有设置信息|
|git config --global user.name |设置协作者信息,**不加global则只为项目设置**|
|git config --global user.email|设置协作邮箱|
|**git init {repo name}** |初始化repo 加repo name在当前目录建立repo<br>不加则以当前目录为repo|
|**git add <filename/\*/.>** |暂存,选择*或.表示暂存全部修改过的文件(对于上次暂存)|
|**git status -s** |查看repo状态,不加-s查看完整状态(比较啰嗦)|
|**git commit -m** "提交目的" |提交到HEAD,HEAD指向最近一次提交后本地仓库的版本|
|git branch {name} |查看当前存在的分支,加name创建一个叫name的新分支|
|**git checkout <branch name>**|**切换到name分支**|
|git checkout -b <name> |**创建并切换到name分支**|
|git merge {name} |把name分支合并到master(主分支,不一定是master)<br>**不加name则直接提交到远程仓库**|
|git branch -d name |<font color=red>**删除分支**</font>|
