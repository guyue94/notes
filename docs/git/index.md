<!--
 * @Description: 记录git命令
 * @Author: guyue94
 * @LastEditors: Please set LastEditors
 * @Date: 2019-03-19 11:37:46
 * @LastEditTime: 2019-03-19 15:56:28
 -->
## git命令

记录平时用到的git命令，不定时更新~~

### 提交文件

	保存到暂存区: git add .<文件名>
	提交本地仓库: git commit -m "备注"

### 分支管理

	新建分支: git checkout -b branchName<分支名称>< -b, 直接切换 >
	切换分支: git checkout branchName<分支名称>
	删除分支: git branch -d(-D) branchName<分支名称>

### commit操作

#### 修改最近一次commit的message

	git commit --amend

#### 修改老旧commit的message
	git rebase -i 父级commit id
	修改pick为reword或者r, 保存
	修改message, 保存

#### 合并连续的commit
	git rebase -i id<父级commit id>
	修改pick为s, 保存
	修改message, 保存

#### 合并不连续的commit

1. git rebase -i id<父级commitId>
2. 将不连续的commit复制粘贴到连续的顺序,如果需要合并到最初的提交，手动添加第一次commit
3. 修改pick为s, 保存
4. 修改message, 保存

### 查看文件差异

1. 查看暂存区和HEAD文件差异

	git diff --cached

2. 查看工作区和暂存区

	git diff