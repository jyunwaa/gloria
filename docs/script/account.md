## 管理方式

所有账号的Cookie保存在`Glory/identities`文件夹中，每个账号以`账号名称.txt`命名，以文本文档的形式存在，文件内容是账号的Cookie。

每新增或者删除一个账号只需新建一个文件或者删除对应的文件即可。

`identities`文件夹的目录结构：

```
Glory
├─identities
│  ├─帐号一.txt
│  ├─帐号二.txt
│  ├─...
├─...
```

## Cookie

简单来说，可以把cookie看作是每个账号登陆后获得的唯一的身份信息，每次向新浪发出请求时，都会附带上cookie，新浪的服务器因此也能识别出具体的用户。

## 获取 Cookie

### 登录新浪

浏览器输入：

```
https://weibo.cn/
```

如图：

![](https://p.pstatp.com/origin/1380200010bcce54abaa4)

点击登录，输入账号密码，登陆新浪微博。

有可能会跳转到如图页面：

![](https://api.superbed.cn/static/images/2020/08/27/5f479abc160a154a67635ac2.jpg)

如果跳转到该页面，则再次手动输入刚才的地址，如图：

![](https://p.pstatp.com/origin/febf0002785510a6cd7a)

若登陆成功，则该页面会显示自己的信息，如上图：账号名为`GEM迷183003`。

### 复制 Cookie

此时按下`F12`，进入开发者选项，点击`Network`，如图：

![](https://p.pstatp.com/origin/fea20002cdab7b52d93f)

按`F5`刷新网页，如图：

![](https://p.pstatp.com/origin/13778000165ad193a8192)

如上图，点击`weibo.cn`，再点击`Headers`，找到`cookie`，然后复制划蓝线的部分（已打码）。

## 添加账号

打开`Glory/identities`文件夹，新建文件`GEM迷183003.txt`（这里的文件名根据自身实际情况更改，不一定必须和微博名相同，注意后缀`.txt`必须有），如图：

![](https://p.pstatp.com/origin/1379f0000dbeb4d9e4188)

打开`GEM迷183003.txt` 将刚才复制的 cookie 粘贴进去，`Ctrl` + `S` 保存，如图：

![](https://p.pstatp.com/origin/ffe40002668fe870f5ed)

## 退出账号

因为我们往往不止有一个账号，所以需要获取多个账号的 cookie，但是前一个账号登陆后需要退出，此时不能点击首页的`退出`链接，这个链接会使 cookie 立马失效，我们需要通过手动清除浏览器的 cookie 的方式进行退出。

保持刚才的开发者选项，点击`Application`，找到`Storage`下的`Cookies`，右击`https://weibo.cn`，点击`Clear`，如图：

![](https://p.pstatp.com/origin/1389a0000055cb2d0498d)

按`F12`退出开发者选项，再按`F5`刷新网页，登陆状态已经消失，如图：

![](https://p.pstatp.com/origin/ffe30002cad77a7144b9)

> Cookie 的有效期一般在一个月以上。

## 查看所有账号

进入`Glory`文件夹，地址栏输入`cmd`，如图：

![](https://p.pstatp.com/origin/1383300009a39d90a81a4)

按下回车，在弹出的命令行窗口中输入：

```cmd
glory account:view
```

按下回车，如图：

![](https://p.pstatp.com/origin/1372100018c17f8306aad)

注意每个帐号的`AccountID`，它在执行命令时用于指定账号，此外，在`Glory/identities`文件夹内部发生变化时它可能会变化。


