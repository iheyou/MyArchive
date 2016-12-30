
#Git的使用命令
##Git的安装（两种方式）
* 1.如果使用mac电脑，直接从AppStore安装Xcode，Xcode集成了Git，默认情况下并没有安装，需要运行命令：

	<code>xcode-select --install</code>
	
	点Install安装“Command Line Tools”。

* 2.第二种方式是直接在命令窗口中输入

	<code>sudo apt-get install git</code>
	
	完成安装。
	
##创建版本库
* 1.创建仓库目录
	
	<code>mkdir xxx</code>
* 2.初始化仓库

	<code>git init</code>
* 3.将文件提交到仓库

	<code>git add "文件名"</code>
	
	如果是所有文件都要添加
	
	<code>git add *</code>
* 4.如果发生意外：
	* 错误1 fatal: remote origin already exists
	先
	
	<code>git remote rm origin</code>
	

##提交修改
* <code>git status</code> 查看仓库当前状态，修改情况
* <code>git diff "文件名"</code> 查看对文件做了什么修改
* <code>git add "文件名"</code> 提交修改文件
* <code>git commit -m“修改描述”</code> 将修改提交到仓库

##删除文件
* <code>git rm "文件名"</code>
* 如果删除错了，但版本库仍然还存在
	<code>git checkout -- "文件名"</code>

###配置连接Github远程库
* <p>创建SSH key。在用户目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key，输入命令:</p>
		<code>ssh-keygen -t rsa -C "youremail@example.com"</code>
	<p>你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，由于这个Key也不是用于军事目的，所以也无需设置密码。如果一切顺利的话，可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。</p>
* <p>登陆GitHub，打开“Account settings”，“SSH Keys”页面.然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容</p>


##添加到远程库
* 首先github已经配置好，并且在github上添加了同名仓库（不同名也可以，下一步自动建立联系）
* 与远程仓库关联

	<code>git remote add origin git@github.com:"Github账户名"/文件名.git</code>

* 关联后，使用命令 

	<code>git push -u origin master</code>

 第一次推送master分支的所有内容；
* 此后，每次本地提交后，只要有必要，就可以使用git push origin master 推送最新修改

##从远程库克隆
* 首先要将要克隆的库fork到自己的账号下
* 克隆一个本地库:

	<code>git clone git@github.com:iheyou/"远程库的名字"</code>
	
* cd 远程库的名字  进入克隆下来的本地库
* ls -al 可以看到本地的克隆库里面是和远程库里面一样的
* 多人开发就从远程仓库每人克隆一份就OK
##更新本地仓库
*如果当前分支只有一个追踪分支，则：
<code>git pull</code>
##删除本地仓库
* 找到本地目录下的.git仓库

	<code>ls -a</code>
	
* 删除.git

	<code>rm -rf .git</code>
	
* 删除本地仓库目录

	<code>rm -rf "本地仓库名字"</code>
	
	至此就把本地仓库完全删除了
	


