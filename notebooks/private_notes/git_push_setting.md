
这里的部分是使用chatGPT找到的方法，测试后发现是好用的：

```
  109  ssh-keygen -C  "da*h@i*d.com"
  # 配置了github的邮件账户，并生成SSH key
  
  110  cat /Users/d*h*g/.ssh/id_*.pub
  # 获取ssh key
  
  111  ssh -T git@github.com
  # 测试连接是否正常
  
  115  git status
  116  git add -A
  117  git commit -m "test"
  118  git push
  119  git remote -v
  120  git push

  121  git remote set-url origin git@github.com:davehuang2021/*.git
# 这一步很重要是要指定使用 ssh 远程地址: 操作之后就可以正常的git push了

  122  git remote -v
# 验证远程地址

  123  ssh -T git@github.com
  # 验证远程地址
  
  124  git push
# 推送更新到远程地址

```

## 2025-5-21
### 使用 GitHub CLI 自动生成 Token 并登录后使用private repositories

**重要信息：私有的repositories是免费账户也可以使用的**：这笔订阅费用大可以生下来。

```bash
brew install gh

gh auth login
### 交互式验证方式，使用 gh 生成的验证码在网页端验证

```
> 整个过程其实很简单。但不知道过一年多，github会不会再改。。。

## 2025-5-21

[git ignore 全局配置](https://orianna-zzo.github.io/sci-tech/2018-01/mac%E4%B8%ADgit%E5%BF%BD%E7%95%A5.ds_store%E6%96%87%E4%BB%B6/)
```
vi .gitignore

vi ~/.gitignore_global

**/.DS_Store

```
## 2025-5-21

- ~/.jupyter/jupyter_lab_config.py配置修改，避免和VPN的端口冲突影响网络使用
- 保存data文件夹的文件结构[[data-dir_files]]，兼顾轻量化和文件同步
- 保存文件的md5，方便同步数据double check[[data-dir_files-md5]]
- 使用的命令见[[data-dir_files-cmd.sh]]
## 2025-5-15

经过测试，可以通过obsidian较好地推送到远程更新中。

```
git add -A; git commit -m "obsidian"

git push

```


```
git clone https://github.com/davehuang2021/RNAseq4dave.git

git remote set-url origin git@github.com:davehuang2021/RNAseq4dave.git

# make some edit

git add -A; git commit -m "mbpa"

git push

```
