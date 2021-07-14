# 一、合并 commit 记录
1. `git rebase -i <commit-id>` : 合并 commit-id 之前所有的 commit log
2. 此时会进入 vim 的交互界面
3. 按 `i` 切换到编辑模式
4. 使用 Squash 策略进行合并
```
p  ... ...
s  ... ... 
s  ... ... 
s  ... ... 

```
5. 按 `Esc` 切换到底线命令模式
6. 按 `:wq` 保存并退出
6. 此时会进入 commit message 的编辑界面
7. 按 `i` 切换到编辑模式
8. 将之前的 commit message 修改成合并后的新的  commit message
9. 按 `Esc` 切换到底线命令模式
10. 按 `:wq` 保存并退出
11. `git push -f origin`：强制推送到远程

# 二、合并指定 commit
1. 定义：不合并一个分支所有的 commit, 只合并相要的 commit
2. 方法: `git cherry-pic <commit-id>`


# 三、git reset Vs git revert
1. git reset: `git reset <commit-id>`: 将提交记录回退到指定的 commit-id 上
2. git revert: `git revert <commit-id>`: 新建一条 commit, 撤回之前 commit-id 的修改
> 对于个人的 feature 分支而言，可以使用 git reset 来回退历史记录，之后使用 git push --force 进行推送到远程，但是如果是在多人协作的集成分支上，不推荐直接使用 git reset 命令，而是使用更加安全的 git revert 命令进行撤回提交。这样，提交的历史记录不会被抹去，可以安全的进行撤回。
