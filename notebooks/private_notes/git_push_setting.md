
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
# 这一步很重要是要指定使用 ssh 远程地址

  122  git remote -v
# 验证远程地址

  123  ssh -T git@github.com
  # 验证远程地址
  
  124  git push
# 推送更新到远程地址

```


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
