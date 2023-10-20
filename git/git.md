# 1.	git简介：
>开源的、分布式的版本控制系统。其他工具，CVS、Subversion。作用如下：
>>1.1 代码托管保存

>>1.2 团队协作功能
# 2.	Github仓库介绍
	Git是一门技术(操作代码仓库的工具)，而github是通过git技术来创建的一个公共代码仓库。Git指分布式版本控制，Hub指中心，合起来就是一个可以存放许多用git进行版本控制的项目的网站。Gitee是国内版Github
# 3.	Git版本控制入门
	a)	Git下载安装：测试cmd输入git –version
	b)	Git分两部分：
		i.	操作仓库核心代码部分：
		ii.	Git仓库：本地仓库和远程仓库(分公有仓库：gitee、github；私有仓库：gitlab、gitblit，常用于公司内部)
	c)	Git仓库创建和删除
	d)	下载git项目代码，git clone 仓库链接。Git登录一次后，会在本地保存账户密码，下次不需要登录，这样会有个问题是，新的单位给的私有仓库指定用户访问时，会拒绝老账户的clone，所以需要把之前的登录信息删掉。通过下面方式：
		控制面板—>用户账户—>凭据管理器—>windows凭据—>gitee.com删除
	e)	提交代码
		i.	设置用户名和邮箱：
			git config --global user.name ‘Erick’
			git config --global user.email ‘445108134@qq.com’
		ii.	查看配置信息：
			git config --list
		iii.	提交(本地仓库)：a-all,表示全部提交。m-message,表示提交说明信息
			git commit -a -m ‘第一次提交’
		iv.	提交(远程仓库)：
			git push
		v.	本地新建文件后，需要先git add . 将本地创建文件，添加到git队列中，作为项目成员。删除文件，直接本地删除然后提交就可以，不过还可以在远程仓库追溯到。	
# 4.	Vue项目仓库的使用:
	vue就是Vue.js，它是一款较为流行的JavaScript前端框架，用于创建用户界面的开源JavaScript框架，旨在更好地组织与简化Web开发。Vue所关注的核心是MVC模式中的视图层，同时，它也能方便地获取数据更新，并通过组件内部特定的方法实现视图与模型的交互。（js框架就是对js代码一层封装,提供了一些教常用的方法）
		a) .gitignore文件内容，代表当前项目会忽略提交的文件。因为代码仓库中一般只会提交源代码和依赖列表，并不会把项目所有依赖文件同时提交到服务器因为依赖文件数量多占用空间大，不光传输慢，而且依赖是会更新的，不同阶段依赖包版本号都会有变更，所以依赖仓库不需要提交到代码仓库，还有就是打包生成的dist文件不需要提交到代码仓库
	b)	先安装依赖：npm install
	c)	增加所有文件到提交队列：git add .
	d)	提交到本地仓库，git commit -a -m ‘测试忽略文件是否生效
	e)	git push 查看远程仓库，忽略文件是否生效(.gitignore中的安装包,未上传,即生效)
# 5.	git的分支管理
	分支就是开发过程中，一个项目会衍生多个端或者类型，虽然核心代码就是一个，但是不同版本有不同功能，这时需要核心代码部分生成多个分支来实现不同版的app开发。
	a)	分支概念：团队或个人开发中，同一项目会衍生多个分支版本，如3人合作项目，一般不允许在master分支上开发，而是先在主分支克隆一份，个人开发完后合并到主分支，可以防止对主分支造成破坏。在个人项目中，比如一个app的标准版、vip版，程序主体大都一样。因此可将相同部分开发完毕之后，通过创建分支方式创建出多个版本。
	b)	创建分支：git branch Eric(分支名)，git branch -d Erick删除分支
	c)	查看分支列表：git branch -a
	d)	切换分支：git checkout Erick，再查看分支列表是否已经切换到创建分支
	e)	将当前的Erick分支创建到远程仓库上，同时远程仓库的分支也叫Erick
		git push --set-upstream origin test。分支要上线，需要合并到主分支
	f)	将分支代码合并到主分支master
		git checkout master	//切换到主分支
		git merge Erick		//当前分支与Erick分支代码合并
		git push				//更新到远程仓库代码
	g)	
# 6.	团队仓库
	a)	团队协作的提交顺序
		i.	开始写项目git pull 拉取更新(如果控制台提示commit，还需要commit一次)
		ii.	 写完项目git add . ，git commit提交到本地仓库
		iii.	push前再使用一次git pull保证当前的所有更新都获取到
		iv.	最后在通过git push推送代码到远程仓库


	切记，每次push前一定要pull一次拉取最新更新，避免覆盖掉别人的代码，若同一文件有修改冲突，需要找到提交人进行协商后，再决定是否push

