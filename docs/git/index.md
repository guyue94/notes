## git命令

记录平时用到的git命令，不定时更新~~

### 1. 提交文件

	保存到暂存区: git add .<文件名, . 代表所有>
	提交本地仓库: git commit -m "备注"

### 2. 分支管理

	新建分支: git checkout -b branchName<分支名称>< -b, 直接切换 >
	切换分支: git checkout branchName<分支名称>
	删除分支: git branch -d(-D) branchName<分支名称>

### 3. commit操作

#### 修改最近一次commit的message

	git commit --amend

#### 修改老旧commit的message

	1. git rebase -i id<准备修改commit的父级commit id>
	2. 修改pick为reword或者r, 保存
	3. 修改message, 保存

#### 合并连续的commit
	1. git rebase -i id<准备合并commit的父级commit id>
	2. 修改pick为s, 保存
	3. 修改message, 保存

#### 合并不连续的commit

	1. git rebase -i id<准备合并commit的父级commit id>
	2. 将不连续的commit复制粘贴到连续的顺序,如果需要合并到最初的提交，手动添加第一次commit
	3. 修改pick为s, 保存
	4. 修改message, 保存

### 4. 查看文件差异

	查看暂存区和HEAD文件差异: git diff --cached
	查看工作区和暂存区: git diff
	仅查看特定文件差异: git diff -- filename<文件名, 可以为多个, 空格隔开>
	查看不同提交的特定文件差异: git diff id<commit id> anid<anthor commit id> -- filename<文件名>


### 5. 恢复文件

	恢复暂存区和HEAD一致: git reset HEAD 
	取消暂存区部分文件的更改: git reset HEAD -- filename<文件名>
	恢复工作区和暂存区一致: git checkout -- filename<文件名>
	恢复commit到某一次提交: git reset --hard id<要恢复到的commit id>

### 6. 删除文件

	git rm filename<文件名>

### 7. 暂时缓存更改

	缓存工作区更改: git stash
	查看stash: git stash list
	恢复工作区更改: git stash apply(保留stash list)
	恢复工作区更改: git stash pop(不保留stash list)
