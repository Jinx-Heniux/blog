## ǰ��

���� git ��ʹ���ձ黯�����ڸ���Ҫ��עʹ�õĹ淶���̣��ڴ˼�¼��

## �Զ�������

```bash
[user]
	name = xiaoyueyue165
	email = 1656800216@qq.com
	signingkey = ""
[credential]
	helper = store
[http]
	postBuffer = 1048576000
	sslBackend = openssl
[color]
	diff = auto
	status = auto
	branch = auto
	ui = true
[alias]
	br = branch
	ci = commit
	unstage = reset HEAD
	co = checkout
  st = status
	last = log -1
	last5 = log -5
	last10 = log -10

  logs = log --pretty=format:'%Cred%h%Creset %Cgreen[%an - %ar]%Creset : %s'
	logsr = log --pretty=format:'%Cred%h%Creset %Cgreen[%an - %ar]%Creset : %s' --reverse
	lg = log --color --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
	lgr = log --color --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --reverse

	back = checkout master
	rh = reset --hard HEAD
	pr = pull --rebase
	prs = pull --rebase --autostash
[format]
	pretty = %C(yellow)%h%Creset %s %C(red)(%an, %cr)%Creset
[help]
	autocorrect = 1

```

## ���õ� pull

**����**

![](http://ww1.sinaimg.cn/large/df551ea5ly1gakqqkarerj20os0b1q3p.jpg)

![Snipaste_2020-01-04_19-13-11.png](http://ww1.sinaimg.cn/large/df551ea5ly1gakqrk8yjjj20vo0dtmyb.jpg)

```bash
git pull --rebase
```

## ���ô���ȡ������

>Error: Filed to connecto to github.com port 443: Time out
```bash
# ����
git config --global http.proxy http://127.0.0.1:51349

# ȡ��
git config --global --unset http.proxy
```

#### �ο�����

- [Git ʹ�ù淶����, by ��һ��](http://www.ruanyifeng.com/blog/2015/08/git-use-process.html)
- [GitԶ�̲������, by ��һ��](http://www.ruanyifeng.com/blog/2014/06/git_remote.html)
- [Understanding the GitHub flow](https://guides.github.com/introduction/flow/)
- [Learn Git Branching](https://learngitbranching.js.org/) / [���ѻش�](https://www.jianshu.com/p/6e94b5592c40)