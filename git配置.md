###1. git 安装
```
sudo apt-get install git
```

###2. git 全局配置
```
git config --global user.name "月落追魂"
git config --global user.email "350810375@qq.com"
```

###3 Linux上生成SSH key
```
ssh-keygen -t rsa -C "350810375@qq.com"
```

###4 打开SSH公钥
```
cat /home/zjw/.ssh/id_rsa.pub 
```

###5 公钥添加测试
```
ssh -T git@git.oschina.net
```

###6常用命令

1. **git add**

- git add：作用就是将我们需要提交的代码从工作区添加到暂存区，就是告诉git系统，我们要提交哪些文件，之后就可以使用git commit命令进行提交了。

2. **git commit**

- git commit 主要是将暂存区里的改动给提交到本地的版本库。

- git commit -m ”xxxx“

- -m参数表示可以直接输入后面的”message“， 如果不加-m参数，那么是不能直接输入xxx的，而是会调用一个编辑器一般是vim来让你输入这个xxx， xxx即是我们用来简要说明这次提交的语句。

3. **git push**

- 在使用git commit命令将修改从暂存区提交到本地版本库后，只剩下最后一步将本地版本库的分支推送到远程服务器对应的分支上。
git push 的一般形式为 pit push <远程主机名> <本地分支名> <远程分支名>，例如：

- git push origin master: refs/for/master,即将本地的master分支推送到远程主机origin上的对应的master分支， origin是远程主机名。第一个master是本地分支名，第二个master是远程分支名。

- git push origin master
如果远程分支被省略，如上则表示将本地分支推送到与之存在追踪关系的远程分支（通常两者同名），如果该远程分支不存在，则会被新建

- git push origin ：refs/for/master

- 如果省略本地分支名，则表示删除指定的远程分支，因为这等同于推送一个空的本地分支到远程分支，等同于 git push origin –delete master

- git push origin

- 如果当前分支与远程分支存在追踪关系，则本地分支和远程分支都可以省略，将当前分支推送到origin主机的对应分支

- git push

- 如果当前分支只有一个远程分支，那么主机名都可以省略，形如 git push，可以使用 git branch -r ，查看远程的分支名

- 关于 refs/for：
refs/for 的意义在于我们提交代码到服务器之后是需要经过code review 之后才能进行merge的，而refs/heads 不需要

4. **git clone**
- 克隆下载