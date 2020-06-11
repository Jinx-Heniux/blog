# git ������ʵ��

###### �Ƽ�

- [���Ӷ��ܶ���GIT����](https://backlog.com/git-tutorial/cn/)
- [Git --everything-is-loca �ٷ��ĵ�](https://git-scm.com/book/zh/v2)
- [Git �̳�-��ѩ��](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)

git �ͻ�����ͼ�λ���С�ڹ� �����������У�git bash����...

## ��������

### �����û���������:

```bash
git config --global user.name "�Լ�������"  # �û���
git config --global user.email "�Լ�������" # ����
git config --list
```

> ���䣬��ʵ�Ǳ������û��������䵽 C:\Users\[�û���]\.gitconfig �ļ���

### ���õĵ���������(github)(Զ�˲ֿ�)

github �����Ǹ���վ,���������վ���ڵĵ��Կ�����Ϊ���õĵ��������ݴ���!

1. ע�� github �˺ţ�����½
2. ��ʹ�� git bash ���ڣ�����

```bash

ssh-keygen -t rsa || ssh-keygen
```

> �������ͻ�����һ����ʶ,������Ҫ�������ʶ�ϴ������������� ��/c/Users/[�û���]/.ssh��Ŀ¼�����������ļ�:��id_rsa, id_rsa.pub��, �����ñ༭���� id_rsa.pub,�������ݲ��ر�

3.�� github ��վ��,�Ѹ��Ƶ���Կ,��ӵ� github ��ȥ!

4.���� `$ ssh -T git@github.com`

> ����ܿ���������**Hi XXXX! You've successfully authenticated, but GitHub does not provide shell access.**��������ʾ�����ʾ ssh key ���óɹ���

## Git ���������ݴ����Ͱ汾��

������������� Git ���������ݴ����Ͱ汾�����

- ���������������ڵ������ܿ�����Ŀ¼��
- �ݴ�����Ӣ�Ľ� stage, �� index��һ������"git Ŀ¼"�µ� index �ļ���.git/index���У��������ǰ��ݴ�����ʱҲ����������index����
- �汾�⣺��������һ������Ŀ¼.git��������㹤���������� Git �İ汾�⡣

�������ͼչʾ�˹��������汾���е��ݴ����Ͱ汾��֮��Ĺ�ϵ��

![201609291519223166.png](http://ww1.sinaimg.cn/large/df551ea5ly1g8f09hs019j20je093djl.jpg)

## ������

1. ����Ŀ��Ŀ¼�´���`.git`�ļ����ݴ����Ͱ汾��Ĵ��붼�ڴ��ļ�����

```bash

git init
```

2. ����ļ����ݴ���

```bash

git add A4.txt //��ӵ�һ�ļ�
git add -A    //������һ��git commit���޸Ĺ����ļ�ȫ����ӵ��ݴ���
```

3. �ŵ��ֿ�

```bash

git commit -m "ע��" // �ǰ��ݴ����Ĵ��룬�ŵ��ֿ�
```

4. git �ϴ����뵽Զ�˷�֧

```bash
git push git@github.com:yanyue404/fed02.git master
```

##### ������

```bash
git remote add origin git@github.com:yanyue404/fed02.git
git push origin master
```

> // ��� origin �����, ���൱������`var origin = "git@github.com:yanyue404/fed02.git"`,�����ص� master ��֧���͵� origin ������ master ��֧

5.  �����嵥�ļ�(.gitignore)

����Ŀ��Ŀ¼���½�һ����Ϊ .gitignore ���ļ� �����磬����ϣ�� test �ļ��е����ݲ�������, ����.gitignore �ļ������һ��

```bash
# ������Ŀ��Ŀ¼��test�ļ����е�����
/test
# ������Ŀ��������Ϊtest���ļ��У������ļ�
test
# ������Ŀ�е���Ϊapp.js���ļ�
app.js
# ������Ŀ�е�����js
*.js
/test/*.*
```

### ��������:

- `git status` // �鿴����Щ�޸ĺ���ļ����ݴ�������Щ����
- `git log` //ֻ�ܿ��� head ָ��֮ǰ���ύ��¼
- `git reflog` // �鿴���еĲ�����¼

## �汾����

Ĭ�� head ָ�� master,�ͻ�� master �е��ύ�Ĵ����õ�������

- `git reset --hard �ύ��id`
- `git reset --hard 53bd6a3cd5b9ff5782af4837985c1e3023412d23`

ǿ���ύ:

```bash
git push -f
```

> ע�⣬����ǻ��˵������һ���ύ��״̬������Ҫ��� commit_id��ֱ�� `git reset --hard head`

## ��֧

Ĭ��ֻ��һ�� master ��֧������֧�������Դ����µķ�֧��Ȼ���ڷ�֧���ύ����!��ֱ�������������ˣ��Ϳ��Իص� master ��֧��Ȼ��ϲ���

```bash
git branch # �鿴���ط�֧
git branch -r # �鿴����Զ�̷�֧
git branch -a # �鿴����Զ�̷�֧�ͱ��ط�֧

git branch [branch-name]  # �½�һ����֧������Ȼͣ���ڵ�ǰ��֧
git checkout [branch-name]  # �л���ָ����֧�������¹�����
git checkout -b [branch-name] #  ����һ����֧���л����÷�֧��,�൱��������������

git merge [branch-name] # �ϲ�ָ����֧����ǰ��֧

git branch -d [branch-name] # ɾ����֧
git push origin --delete [branch-name] # ɾ��Զ�̷�֧
```

## ��ǩ

```bash
git tag # �г�����tag
git tag [tag] # �½�һ��tag�ڵ�ǰcommit
git tag [tag] [commit] # �½�һ��tag��ָ��commit
git tag -d [tag] # ɾ������tag
git push origin :refs/tags/[tagName] # ɾ��Զ��tag
git show [tag] #�鿴tag��Ϣ
git push [remote] [tag] # �ύָ��tag
```

## Զ��ͬ��

```bash

git fetch [remote] # ����Զ�ֿ̲�����б䶯

git remote -v # ��ʾ����Զ�ֿ̲�
git remote show [remote] # ��ʾĳ��Զ�ֿ̲����Ϣ
git remote add [shortname] [url] # ����һ���µ�Զ�ֿ̲⣬������

git pull [remote] [branch] # ȡ��Զ�ֿ̲�ı仯�����뱾�ط�֧�ϲ�

git push [remote] [branch] # �ϴ�����ָ����֧��Զ�ֿ̲�
git push [remote] --force # ǿ�����͵�ǰ��֧��Զ�ֿ̲⣬��ʹ�г�ͻ
git push [remote] --all # �������з�֧��Զ�ֿ̲�
```

## ����(�����һ����Ŀ project)

```bash
git init # �ǵ�һ�ν����汾��
git clone [url] # ����һ����Ŀ����������������ʷ

git pull origin master    # ��Զ�̻�ȡ���°汾��merge�����ص�ͬ��
git checkout -b dev       # �������·�֧�Ͽ���������ʵ���Ƿ���Ҫ
git add -A, git commit -m # һ������������������֮��ص� master ��֧
git checkout master
git merge dev

# ɾ������ dev��֧��Զ�̵�dev��֧
git branch -d dev
git push origin --delete dev
```

## git ���������ٲ��

![1486348362884912.jpg](http://ww1.sinaimg.cn/large/df551ea5ly1g8ezswhp6wj21lo14qgqu.jpg)

#### �ο�����

- http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html
- [Git workflow ��̸](https://juejin.im/post/5844507761ff4b006c3359a9)
