## С��ʿ

- `ctrl+p` chrome ���ҵ�ǰ��վ�Ѽ��ص���Դ�ļ�

## CLI

### create-react-app

- Vscode ����

���Ȱ�װ `Debugger for Chrome` ��������ú�`launch.json`

```
// launch.json
{
  // ʹ�� IntelliSense �˽�������ԡ�
  // ��ͣ�Բ鿴�������Ե�������
  // ���˽������Ϣ�������: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "type": "chrome",
      "request": "launch",
      "name": "��������",
      "url": "http://localhost:9009",
      "webRoot": "${workspaceRoot}/src"
    }
  ]
}

```

Ȼ��������Ŀ, `yarn dev`, �ȴ���Ŀ�ɹ�������ʾ��

```bash
<s> [webpack.Progress] 100%

  App running at:
  - Local:   http://localhost:9009/
  - Network: http://10.64.101.37:9009/
```

�� `F5` ��������ģʽ����ϵ㣬���� debug��������� `Breakpoint set but not yet bound`˵�� ���öϵ㵫��δ��, ����ǿ��ʹ�� `debugger` ȷ��׼ȷ�ϵ㶨λ��

## �������

�󲿷ֽӿ�ʹ�����Ϸ��񣬲��ֽӿڴ��������ش�����ԣ�ǰ�������������

ԭ��ȫ��ʹ�����ϣ�

```js
// http.js
axios.defaults.baseURL = '/prod-api';

// vue.config.js
module.exports = {
  proxy: {
    [process.env.VUE_APP_BASE_API]: {
      target: `http://h5.baishi360.cn/`,
      changeOrigin: true,
      pathRewrite: {
        '^/api': '',
      },
    },
  },
};
```

���ֽӿڴ������أ�

```js
// http.js
axios.defaults.baseURL = '';

// vue.config.js
module.exports = {
  proxy: {
    // ���ش��� 1
    '/api/cms/cmsActivity': {
      target: `http://10.64.101.55:18011/`,
      changeOrigin: true,
    },
    // ���ش��� 2
    '/api/cms/searchA': {
      target: `http://10.64.101.55:18011/`,
      changeOrigin: true,
    },
    // ���ϴ���
    '': {
      target: `http://h5.baishi360.cn/prod-api/`,
      changeOrigin: true,
    },
  },
};
```

## Node.js

Inspector ԭ��

- WebSockets ���񣨼������
- Inspector Э��
- Http ���񣨻�ȡԪ��Ϣ��

### Chrome DevTools

- ���� `chrome://inspect`,���`����`��ť��ȷ�� Host Port ��ȷ��Ȼ���� �·�`inspect`��ť�������ҳ�棬���϶ϵ������������ڴ򿪼�����ԭʼ�˿ڼ��ɵ���
- ���� vscode ��ӡ�Ķ˿ں� ��`node --inspect app.js`�����ʶ˿� `localhost:9229/json`��ȡԪ��Ϣ,��������з��� `devtoolsFrontendUrl`
- �� chrome `http://localhost:3000/`�򿪿�����ҳ�棬ѡ�� `Elements`Ԫ�ذ�ť���� `Node.js`ͼ�꣬�ɽ������ҳ��

  - `Profiler`������¼����Ŀ����ʱ�䣬�Ż���Ŀ

### Vscode

- ���ļ�������ʽ�� F5
- ��Ŀʽ������ launch.json��������Ű�ť
- vscode `ctrl+shift+p`��`�Զ�����`��Ȼ���ն����� `node --inspect app.js` ���򿪵���ģʽ

```bash
node --inspect app.js

# �����õĶϵ㴦������ִͣ��
node --inspect-brk app.js
```

## ���ϵ���

### fiddler ������ǰ����Դ

ʹ��`fiddler` ��������Դ�������ص���,�磺`css`, `js` , `image` �ļ��ȵȣ������[�ο�](https://blog.csdn.net/hahavslinb/article/details/78791219)

![](http://ww1.sinaimg.cn/large/df551ea5ly1g2kp8yr5mnj21ha0s3jxf.jpg)

> ע��
> fiddler �޷�ץȡ chrome �������,������ѡ��ʹ��ϵͳ�������á�ѡ��
> ��fiddler ���Զ������������һ������ 127.0.0.1 �˿� 8888�����Ҽ���������Ĵ������ã����е��������� fiddler �����������������
> ���ʹ�ò�������ܻ�ֱ�������� fiddler �Ĵ�������޷������������ˡ�

### [spy-debugger](https://github.com/wuchangming/spy-debugger)

΢�ŵ��ԣ����� WebView ��ʽ���ԡ��ֻ��������ҳ��������ԡ���ݵ�Զ�̵����ֻ�ҳ�桢ץ�����ߣ�֧�֣�HTTP/HTTPS������ USB �����豸��

### [eruda](https://github.com/liriliri/eruda)

> Console for mobile browsers

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no"
      id="densityDpi"
    />
    <link rel="icon" href="<%= BASE_URL %>favicon.ico" />
    <title>Console for mobile browsers</title>
  </head>
  <body>
    <div id="app"></div>
    <script src="https://cdn.bootcss.com/eruda/1.4.3/eruda.min.js"></script>
    <script>
      eruda.init();
    </script>
  </body>
</html>
```

### sourcemap

TODO...

#### �ο�����

- [imooc - node.js ��������](https://www.imooc.com/learn/1093)
- [node-in-debugging](https://github.com/nswbmw/node-in-debugging)
- [�ϵ����](https://www.zhihu.com/question/43687153/answer/149944688)
- [stackoverflow - vscode-debugging-with-create-react-app](https://stackoverflow.com/questions/42714449/vscode-debugging-with-create-react-app)
- [ϸ˵ js ѹ����sourcemap��ͨ�� sourcemap ����ԭʼ������Ϣ](https://github.com/senntyou/blogs/blob/master/web-extend/8.md)
