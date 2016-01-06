#Git 团队协作方案
##分支管理
```
master线上也是最稳定分支
develop 开发分支 fork from master
feature 团队开发功能分支 fork from develop
hotfix 线上紧急bug---fork from master
```
##Pull Requests 方式
### develop 受保护分支(在gitlabe上设置)，developer 不可push代码到此分支
```
管理员
1.git checkout -b develop master//在master分支上新建develop分支
开发者
1.git clone https://git.boqii.com/**/**.git
2.git checkout -b feature-001(禅道任务编号) origin/develop
3.git add .
4.git commit -am ""
5.git push origin issue-001
6.在gitab 上 申请合并 issue-001 分支到 develop上
管理员
收到合并申请，overview代码，合并issue-001 代码到develop上
```
##非Pull Requests 方式
###此时develop分支非 受保护分支
```
开发者
1.git clone ssh://user@host/path/to/repo.git
2.git checkout -b develop origin/develop
3.git checkout -b feature-001 develop
4.git add <some-file>
5.git commit

6.git pull origin develop
7.git checkout develop //此时开发者可以使用develop分支
8.git merge feature-001
9.git push
10.git branch -d feature-001
```

##产考资料
+ [Git工作流指南](https://github.com/xirong/my-git/blob/master/git-workflow-tutorial.md)

