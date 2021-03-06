# 1. 架构设计框架设计
# 2. 大文件存储
百度云盘共享链接

# 3. 项目说明书
语鹊文档

# 4. 代码工作流程

在主库已经存在的情况下，日常操作流程如下：
1、开发人员从develop主库建立分支
可以选择4种分支名字：

- feature-xxx  ：新功能
- hotfix-xxx   ：修复存在问题
- release-xxx ：即将发布新版本，通过release-xxx添加说明文档等辅助材料
- develop-自己的名字 ：主线开发任务推进

2、开发人员通过

- 拉取gitlab的全部数据

```shell
git pull origin 
```

git pull <远程主机名> <远程分支名>

注意： git fetch origin命令，从远程获取最新版本到本地，但不会自动git merge。如果需要有选择的合并git fetch是更好的选择。效果相同时git pull将更为快捷。

- **切换到你的创建的分支（这个很重要，否则你可能在别的分支进行了修改）**，例如

```shell
$ git checkout . 
$ git checkout hotfix-xxx
```

3、**在文件夹中解决需求（这个是核心工作）**

4、将修改好的文件上传git

```shell
git add *
git commit -m "Header：fix_xxx；Body：Issue #1, #2 和 Footer：Closes #1" 
git push origin hotfix-xxx
```

5、提交融合到develop的请求。Open a pull request

6、您的工作已经结束，感谢您的支持。
后续的工作是被有权限的开发人员进行文件融合，以及发布Tags，这个您不用担心。他们可以很好的完成这个任务。

7、若是需要创建分支

```shell
git checkout -b feature-branch    //创建并切换到分支feature-branch  
```

8、若是只需提交分支对应内容

```shell
git checkout  feature-branch    # 创建并切换到分支feature-branch  
git push origin feature-branch:feature-branch    # 推送本地的feature-branch(冒号前面的)分支到远程origin的feature-branch(冒号后面的)分支(没有会自动创建)
```

9、若是只需拉取对应分支的内容

```
git checkout  feature-branch    # 切换到分支feature-branch  
git pull origin feature-branch2    # 拉取远程的feature-branch2分支到本地feature-branch 分支中
```

