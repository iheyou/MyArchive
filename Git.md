#Git的使用命令
##Git的安装（两种方式）
* 1.如果使用mac电脑，直接从AppStore安装Xcode，Xcode集成了Git，默认情况下并没有安装，需要运行命令：

	xcode-select --install
	
	点Install安装“Command Line Tools”。

* 2.第二种方式是直接在命令窗口中输入

	sudo apt-get install git
	
	完成安装。
	
##创建版本库
* 1.创建仓库目录
	
	mkdir xxx
* 2.初始化仓库

	git init
* 3.将文件提交到仓库

	git add xx文件名xx
	
	如果是所有文件都要添加
	
	git add *
	

##提交修改
* git status 查看仓库当前状态，修改情况
* git diff xx文件名xx 查看对文件做了什么修改
* git add xx文件名xx 提交修改文件
* git commit “修改描述” 将修改问价提交到仓库

###配置连接Github远程库
* 创建SSH key。在用户目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key，输入命令ssh-keygen -t rsa -C "youremail@example.com",你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，由于这个Key也不是用于军事目的，所以也无需设置密码。如果一切顺利的话，可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。
* 登陆GitHub，打开“Account settings”，“SSH Keys”页面.然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：


##添加到远程库
* 首先github已经配置好，并且在github上添加了同名仓库（不同名也可以，下一步自动建立联系）
* git remote add origin git@github.com:XXGithub账户名XX/文件名.git
* 此后，每次本地提交后，只要有必要，就可以使用git push origin master 推送最新修改

##从远程库克隆
* 首先要将要克隆的库fork到自己的账号下
* cd 远程库的名字  进入克隆下来的本地库
* ls -al 可以看到本地的克隆库里面适合远程库里面一样的
* 多人开发就从远程没人克隆一份就OK
