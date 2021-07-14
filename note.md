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




