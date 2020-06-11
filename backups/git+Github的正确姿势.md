## ǰ��

�������Ǳ����� github ʹ���е�һЩ�������ܽᣬѧϰ�������ƻ�ͬ�����£���¼��

### ѧϰ����

**1. �����Ƽ�**

- [Git �̳�-��ѩ��](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
- [�汾�������� �C ��� Github](http://www.imooc.com/learn/390)

**2. �����ĵ�**

- [Git --fast-version-control ](https://git-scm.com/book/zh/v2)
- [�ٷ���վ](https://help.github.com/) / [�������ķ���](https://github.com/waylau/github-help)
- [Git ���й���(Flight Rules)](https://github.com/k88hudson/git-flight-rules/blob/master/README_zh-CN.md)
- [GitHub �ؼ�](https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.zh-cn.md#%E8%B4%A1%E7%8C%AE%E8%80%85%E6%8C%87%E5%8D%97)
- [GotGitHub: an open source E-book about GitHub in Chinese](https://github.com/gotgit/gotgithub)
- [git-recipes](https://github.com/geeeeeeeeek/git-recipes) - �������� Git ���Ľ̳�
- [GitHub ����ָ�� by phodal](https://github.com/phodal/github)

## һ��github markdown �﷨����

> д�� md ����Ҫ !!!

- [���ļ����ĵ���д���淶 by ruanyifeng](https://github.com/ruanyf/document-style-guide)
- [guodongxiaren/README README �ļ��﷨���](https://github.com/guodongxiaren/README)
- [emoji-list/ github ֧�ֵ� emojj ����](https://github.com/caiyongji/emoji-list)
- [GitHub �� README �е�Ư������](https://shields.io/)

## ������֤����ʹ��

### 1. �ڹ�˾����������Ҫ���ô���

github �Ͽ���ʹ�� https ���з��ʡ�

```bash
$ git config --global http.proxy http://web-proxy.oa.com:8080
```

> ������������ clone �ˡ��������Ҫ push ���룬�Ǿ��鷳�ˡ�ÿ�ζ���Ҫ��������,�������¿���

### 2. �ϴ�ǰ����`.gitignore` ����

�������ܣ���ǰ�� ��Ŀ�г��������Ӵ������ļ���`node_modules`�����ǲ���Ҫ�ϴ�����`package.json`�ļ������������Ϳ���

```bash
*.DS_Store
node_modules # ������Ŀ����Ϊ node_modules ���ļ��У����ϴ��������
bower_components
.sass-cache
npm-debug.log
.idea
.vscode
```

```bash
# git-���԰汾������ĳЩ�ļ����޸�
git update-index --assume-unchanged application/Everything/Everything.ini
```

### 3. git commit log

���ŵ��ύ `code`��Ϊ commit �Լ���ÿ�� commit ���úõ���־, �����պ�׷��:

- Head
  - type: feat ������, fix �޸�����, docs �ĵ�, style ��ʽ, refactor �ع�, test ��������, chore �����޸�, ���繹������, ��������.
  - scope:Ӱ�췶Χ�� ����: route, component, utils, build... ��ʡ��
  - subject:��̵��ύ��Ϣ
- Body
  - what����ϸ����ʲô
  - why�� Ϊʲô������
  - how�� ��ʲô���
- Footer
  - �������

> ���䣺ʹ�� svn С�ڹ��ύ����û��ǿ����Ҫд commit log , �����Ҷ�д

### 4. git push ������

ÿ���ύ����ʱ��Ҫ�����û������룬��˵�����ڴӲֿ��� clone ����ʱʹ�õ��� HTTPS �� key ������ȡ���롣��ʹ�� SSH key ��ȡ����ʱ������Ҫ��

(1). �����ļ� `.git-credentials` �洢 GIT �û���������

```bash
# ����
touch .git-credentials
# ��vim�д�
vim .git-credentials
# �ļ�����
https://{username}:{password}@github.com
```

(2). ���ڴ洢����,���� git bash �նˣ� ������������:

```bash
git config --global credential.helper store
```

��������������Ϳ���`���ܵ�¼`��

**ע������**

�ļ��ṹҪ���ʼ������ `github` ��`.gitconfig`�ļ���ͬ����Ŀ¼��

## ������Ŀ github ƽ̨չʾ

### 1. `gh-pages` ��֧�������߷���

���Լ��� github ��Ŀ�����`gh-pages`��֧������֤��������Ҫչʾ�Ĵ��룬��`index.html`��Ϊ��ھ� ok������չʾ��Ŀ��

- �ο���������Ŀ�µ� dist �ļ������ݷ�����Զ�˵� `gh-pages` ��֧

```bash
git subtree push --prefix=dist origin gh-pages
```

#### ����

- [��Ŀ vip](https://github.com/xiaoyueyue165/vip) [���߷���](https://xiaoyueyue165.github.io/vip/ΨƷ����ҳ/)
- [��Ŀ react-yanxuan](https://github.com/xiaoyueyue165/react-yanxuan) [���߷���](https://xiaoyueyue.org/react-yanxuan/)

### 2. github �޸���Ŀ������ʾ

����Ŀ��Ŀ¼����ļ���Ϊ`.gitattributes`���ı��ļ�:

```bash
touch .gitattributes
```

д��:

```js
*.js linguist-language=javascript
*.css linguist-language=javascript
*.html linguist-language=javascript
```

��˼���ǽ�`.js`��`.css`��`.html`���� **javascript** ������ͳ��,����Ч

> �鿴��������չʾ�����Ա�Ϊ`javascript`=> [King-of-glory](https://github.com/xiaoyueyue165/King-of-glory)

### 3. �ϴ��ļ�����

(1). **git ���ͳ��� "fatal: The remote end hung up unexpectedly"**

ԭ���ϴ����ļ�����,�����ļ���С�� `100M`
����취������Ŀ.`git`�ļ�����Ѱ��`config`�ļ���������´��룺

```bash
[http]
postBuffer = 524288000
```

(2). �����ϴ������ļ����� 100M ʧ��ʱʹ��

- [git-lfs](https://github.com/git-lfs/git-lfs)

### 4. rebase �����޸� commit �ύ��ʷ

�ϲ�����ύ����ʷ���� `ba4358d`�� `a549037` ��Ϊһ�� commit

```bash
# ����
git log --online

# ���
ba4358d (HEAD -> master, origin/master, origin/HEAD) docs: ��
ba4358d Update README.md
ba4358d Update README.md # ����Ŀ���Ϻϲ�Ϊһ��
36f95d9 docs
0312afb init
```

׼���ϲ�

```bash
git rebase -i 36f95d9 | git rebase -i HEAD~3
```

ѡ��ϲ�

```bash
# ���

pick ba4358d   'ע��**********'

pick ba4358d   'ע��*********'

pick ba4358d   'ע��**********'

# pick ����˼��Ҫ��ִ����� commit
# squash ����˼����� commit �ᱻ�ϲ���ǰһ��commit (ʡ��д�� s)
# �� vim ���������� i ����༭ģʽ���༭��ɺ� :eq �����˳�

# ����

pick 3ca6ec3   'ע��**********'

s 1b40566   'ע��*********'

s 53f244a   'ע��**********'
```

������ɺ���������ѡ��

```bash
git rebase --continue  #  ȷ�� rebase
git rebase --abort     # ȡ�� rebase

#ȷ�Ϻ󣬾Ϳ����ϴ���Զ���ˡ�
```

���û�г�ͻ�����߳�ͻ�Ѿ���������������µı༭����, ����`:wq` ���沢�Ƴ�:

```bash
# This is a combination of 4 commits.
#The first commit��s message is:
ע��......
# The 2nd commit��s message is:
ע��......
# The 3rd commit��s message is:
ע��......
# Please enter the commit message for your changes. Lines starting # with ��#�� will be ignored, and an empty message aborts the commit.
```

�鿴��ʷ���Ѿ��ı�

```bash
git log --oneline
d2d71a5 (HEAD -> master) Update README.md
36f95d9 docs
0312afb init
```

```bash
git push -f  # ǿ�Ƹ���Զ��
```
### 5.�޸����µ� git commit ע��

```bash
# ����µ�ע��
git commit --amend -m "�µ�ע��"

# ������Զ��
git push -f
````
### 5. github ����Զ�̷�֧ʱ����������ͬ�����Լ�����Ŀ���ύ `PR`����α��⣿

## �ġ�github �Ŷ���֯

- [google](http://github.com/google)
- [facebook](http://github.com/facebook)
- [apache](http://github.com/apache)
- [microsoft](https://github.com/microsoft)
- [mozilla](http://github.com/mozilla)
- [codrops](http://github.com/codrops)
- [twitter](https://github.com/twitter)
- [square](http://github.com/square)
- [googlesamples](https://github.com/googlesamples)
- [Netflix](https://github.com/Netflix)
- [github](https://github.com/github)
- [airbnb](https://github.com/airbnb)


#### �ο�����

- [���ŵ��ύ��� Git Commit Message](https://zhuanlan.zhihu.com/p/34223150)
- [Git �ύ����ȷ���ƣ�Commit message ��дָ��](https://www.oschina.net/news/69705/git-commit-message-and-changelog-guide)
- [����� Github �� gh-pages ��֧չʾ�Լ�����Ŀ](https://www.cnblogs.com/MuYunyun/p/6082359.html)
- [��Git���ϲ���� Commit](https://www.jianshu.com/p/964de879904a)
- [Git log ��̫�ÿ����������ϲ� commit ��](https://learnku.com/articles/9377/git-log-is-not-very-good-lets-merge-commit)
- [����github�ŶӵĿ�Դ��ַ](https://github.com/niezhiyang/open_source_team)