

### 1 安装客户端

官网下载：https://git-scm.com/downloads

一直点击下一步安装即可

在桌面空白处右键出现红框中的内容即安装成功。

![image-20210719230718238](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210719230718238.png)

### 2 配置git的用户名和邮箱

点击“Git Bash Here”,打开命令窗口

1. 设置用户名

   ![image-20210719230949398](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210719230949398.png)

2. 设置邮箱

   ![image-20210719231011521](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210719231011521.png)

3. 查看配置的用户名和邮箱

   ```
    git config --global --list
   ```

   

### 3 创建项目

​	

### 4 上传文件

#### 1 配置忽略文件、文件夹上传

1. 创建.gitignore文件

   

2. 初始化项目

   在当前项目目录下，打开命令终端,Shift+右键

   ![image-20210719231953304](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210719231953304.png)

   

   执行命令：

   ```
   git init
   ```

   如图：

   ![image-20210719232115325](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210719232115325.png)

2. 将文件放到暂存区

   执行命令

   ```
   git add .
   ```

   ![image-20210719232353783](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210719232353783.png)

3. 将暂存区的代码提交到远程仓库

   执行命令

   ```
   git commit -m 第一次上传文件
   ```

   

   ![image-20210719232529055](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210719232529055.png)

4. 远程服务

   ```
   git remote add origin git@gitee.com:dml111727/testGit.git
   ```

   推送到GitHub

   ```
   git push -u origin master
   ```

   如果出现以下错误：

![image-20210719234213510](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210719234213510.png)

​		https://www.cnblogs.com/janve/p/10946630.html解决上述问题

 5. 验证上传是否成功

    刷新gitee的页面，我们的项目代码在上面即可

### 5 删除文件

1. 手动删除

   1. 手动删除文件
   2. 查看文件状态

   ``` git status
   git status
   ```

   ![image-20210720000111252](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210720000111252.png)
   3. 把所有剩余的文件加到暂存区

   ```
   git add .
   ```

   4. 再次查看项目状态

   ```
   git status
   ```

   ![image-20210720000319102](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210720000319102.png)
   5. 提交到远程仓库

   ```
   git commit -m 第一次上传文件
   ```

2. 命令删除

   1. 删除

   ```
   git rm .\aaa.txt
   ```

   2. 把所有剩余的文件加到暂存区

      ```
      git add .
      ```

   3. 提交到远程仓库

      ```
      git commit -m 第一次上传文件
      ```

### 6 文件重命名

1. 手动重命名

   1. 本地手动重命名文件

   2. 将文件提交到远程仓库

      ```
      git add 文件名
      git commit -m 备注
      ```

      ![image-20210722235455928](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210722235455928.png)

2. 命令

   1. 重命名

   ```
   mv 原来的文件名 新的文件名
   ```

   2. 提交

   ```
   git add 文件名
   git commit -m 备注
   ```

   

   ![image-20210722235718983](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210722235718983.png)

### 7 查看文件前后变化

1. 查看文件修改记录

   ```
    git log --pretty=oneline 文件名
   
   ```

   ![image-20210723000158076](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210723000158076.png)

2. 查看文件具体的一次提交的修改记录

   ```
   git show 提交的编码
   ```

   ![image-20210723000407588](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210723000407588.png)

3. 查看文件具体的变化

   ```
   git log -p 文件名
   ```

   ![image-20210723000706982](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210723000706982.png)

### 8 在未提交前还原到上一次提交状态(即清除当前修改未提交的内容)

1. 对比修改

   1. 查看文件修改前后内容

   ```
   git diff
   ```

   ![image-20210723001325887](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210723001325887.png)

   红色内容为之前提交的内容，绿色内容为当前修改未提交的内容

2. 回退到未提交的状态

   ```
    git checkout -- 要回退的文件名
   ```

###  9 追踪文件回退到最后一次提交

1. 追踪 

   ```
   git add 文件名
   ```

2. 撤销追踪

   当文件执行1的命令之后，我们如果想回退到未提交的版的内容时，是没有效果的，即执行

   ```
   git checkout -- 文件名
   ```

   需要执行下面的命令撤销追踪

   ```
   git reste HEAD 文件名
   ```

   ![image-20210726215819023](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726215819023.png)

3. 回退到最后一次提交的状态

   ```
   git checkout -- 文件名
   ```

### 10 回退到指定版本

![image-20210726220507349](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726220507349.png)

1. 回退到上一次版本,有多少个^就代表回退到几个版本

   ```
   git reset --hard HEAD^
   ```

![image-20210726220521053](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726220521053.png)

2. 回退到指定版本

   ```
   git reset --hard 提交的版本id
   ```

   ![image-20210726220740351](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726220740351.png)

### 11 将指定文件回退到指定版本

并不是把所有文件都回退，指定的文件才会被回退

```
git checkout  版本id -- 要回退的文件名
```

### 12 将文件提交到远程仓库

```
git push origing 分支名称
```

### 13 添加标签

1. 添加到最后一次提交的代码中

   ```
   git tag 标签名称
   ```

   ![image-20210726222817882](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726222817882.png)

2. 查看所有的标签

   ```
   git tag
   ```

   ![image-20210726222917945](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726222917945.png)

3. 给之前提交的代码添加标签

   ```
   git tag 标签名 提交的id
   ```

   ![image-20210726223242745](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726223242745.png)

4. 删除标签

   ```
   git tag -d 标签名
   ```

   ![image-20210726223414339](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726223414339.png)

5. 将标签推送到远程仓库

   ```
   git push origin 标签名
   ```

   ![image-20210726223618848](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726223618848.png)

![image-20210726223655750](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726223655750.png)



![image-20210726223716089](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726223716089.png)

### 14 分支操作

#### 14.1 查看已有分支

```
git branch
```

#### 14.1 创建分支

1. 创建分支

   ```
   git branch 分支名
   ```

![image-20210726224133138](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726224133138.png)

​	注意：分支的顺序由名字排序，而不是创建时间。

​	*的分支为当前所在分支

#### 14.2 切换分支

```
git checkout 分支名
```



#### 14.3 删除分支

```
git branch -d 分支名
```

![image-20210726224421699](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726224421699.png)



​	注意：不能删除当前所在的分支

#### 14.4 创建并切换分支

在哪个分支下面执行这条命令，代码就是那个本地分支的内容到新的分支中

```
git checkout -b 分支名
```

![image-20210726224548705](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726224548705.png)

#### 14.5 强制删除分支

```
git branch -D test
```

![image-20210726225139022](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726225139022.png)



#### 14.6 创建分支并与远端仓库进行关联

```
git fetch
git branch -av
```

![image-20210726235038562](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726235038562.png)

红色部分为远程分支()

```
git checkout -b 分支名  远程分支
```

![image-20210726235131909](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726235131909.png)



### 15  合并分支

将指定分支合并到当前分支

```
git merge 分支名
```

![image-20210726225634414](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726225634414.png)

注意：被合并的分支是不受影响的，如上图，dev的分支代码不受影响

### 16 解决合并分支冲突

```
git merge dev
```



![image-20210726230046736](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726230046736.png)

打开冲突文件bbb.txt

![image-20210726230750925](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726230750925.png)

1. 忽略其他分支，保留当前分支的代码

   ```
   git merge --abort
   ```

2. 手动解决冲突

   - 删除文件的<<<<HEAD和=====和>>>> dev，看是否保留那些内容，当前是保留了两个分支的内容

   ![image-20210726230819173](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726230819173.png)

   - ```
     git staus
     ```

     ![image-20210726231048151](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726231048151.png)

     两个地方被修改

   - ```
     git add 文件名
     ```

   - ```
     git commit
     ```

     ![image-20210726231228828](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726231228828.png)

     输入解决冲突的文件和说明等，如：

     按下i可以进行输入：

     ![image-20210726231427885](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726231427885.png)

输入完成后，按esc按钮，输入`:wq`进保存

```
git status
```

![image-20210726231651274](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726231651274.png)

没有文件是发生改变了

```
git commit -m 提交说明
```

![image-20210726231754081](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726231754081.png)

### 17 查看版本路线

1. 查看版本路线

   ```
    git log --online --graph
   ```

   ![image-20210726232256640](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726232256640.png)

### 18 删除远程仓库不想要的分支

1. 拉取所有的远程仓库

   ```
   git fetch
   ```

2. 查看所有的仓库

   ```
   git branch -av
   ```

   ![image-20210726233425459](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726233425459.png)

红色字体为远程仓库

删除远程仓库：确保不需要了，确保已经合并

```
git push origin --delete test3
```

### 19 解决本地推送到远程仓库时代码冲突

1. 拉取远程仓库

   ```
   git fetch
   ```

2. 查看所有仓库

   ```
   git branch -av
   ```

3. 合并他人新提交的代码

   ```
   git merge origin/分支名
   ```

   编辑合并信息保存

   再执行

   ```
   git push
   ```





### 常用命令

#### 查看项目改动

```
git staus
```

​	红色代表还没加到暂存区

​	绿色为暂存区的文件 unstage 

#### 查看提交记录

1. 查看所有人的提交记录

```
git log
```

2. 查看指定人员的提交记录

   ```
   git log --author='用户名'
   ```

3. 查看简略日志

   ```
   git log --online
   ```

   ![image-20210726232057585](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210726232057585.png)

