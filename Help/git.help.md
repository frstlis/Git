github上分支的合并
几个人合作用开发项目时，代码保存到GitHub上，我们不可能在原有代码上直接修改调试，这时就要创建一个新的分支，在分支上改自己的代码，修改完成后，把分支上修改的代码合并到主分支master上就好了。这个过程需要经过以下几个步骤：

1、创建一个分支test

　　git branch test

2、查看分支创建是否成功，下面的命令可以得到现在仓库中的分支列表

　　git branch

3、master分支是仓库默认的主分支，把工作从master分支下切换到test分支下

　　git checkout test

4、内容修改完成后，通过下面命令把内容提交给test分支下

　　git add -a

　　git push -u origin test

5、再把工作从test分支下切换到master下

　　git checkout master

6、因为是合作开发项目，这时远程仓库中的内容有可能已经发生了变化，所以我们需要将远程仓库中的内容和本地分支中的内容进行合并

　　git pull origin master

7、接下来要做的是将test分支合并到master上

　　git merge test

8、查看分支中内容提交的状态

　　git status

9、最后一步，我们把修改的内容提交到主分支上

　　git push origin master

如果你感觉合并后的内容有问题，你可以通过撤销合并恢复到以前状态。

　　git reset --hard HEAD

代码已经提交，撤销的方法是

　　git reset --hard ORIG_HEAD

删除本地分支：

　　git branch -d dev  【git branch -参数 本地分支名称】

删除远程分支：

　　git push origin --delete dev  【git push origin --参数 远程分支名称】