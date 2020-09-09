## 获取 Cookie

打开 Chrome 无痕窗口。

打开方式一，点击 Chrome 地址栏末端的三点图标，打开新的无痕窗口，如图：

![](https://p.pstatp.com/origin/1373500019341fc327d3a)

打开方式二，打开开始菜单，右击 Google Chrome 图标，打开新的无痕出口，如图：

![](https://p.pstatp.com/origin/ff3b000324d4b9b92dbc)

打开方式三，右击任务栏的 Chrome 图标，打开新的无痕窗口，如图：

![](https://p.pstatp.com/origin/fe8600031039938a249b)

> 1.使用无痕窗口的目的是无需手动清理 Cookie，直接关闭无痕窗口即可，下次打开新的无痕窗口与上一次打开的无痕窗口不会有任何联系，也不会与普通窗口有任何联系。

> 2.没有必要同时打开多个无痕窗口，因为若多个无痕窗口共存，则它们之间的 cookie 是共享的。

地址栏输入：`https://m.weibo.cn`，登录账号（小号），登录成功后如图：

![](https://p.pstatp.com/origin/fe82000244ac40399f8e)

按下`F12`，或者同时按下`Ctrl + Shift + I`，进入开发者工具模式。

点击`Network`，按`F5`刷新网页，如图：

![](https://p.pstatp.com/origin/1380f00027b077d532fde)

在资源列表里找到`⚙ m.weibo.cn`，点进去，点击`Headers`，下拉找到`cookie`，复制划线内容，如图：

![](https://p.pstatp.com/origin/1384f00004cb4c05b6a54)

## 添加小号

进入后台，`账号管理`>`小号列表`，如图：

![](https://p.pstatp.com/origin/137f800011315ff2b93f2)

点击右上角`+ New`按钮，如图：

![](https://p.pstatp.com/origin/138590000610fb5a1869f)

输入账号名称，输入上一个步骤复制的 cookie，点击`Submit`提交，如图：

![](https://p.pstatp.com/origin/137240001803f0a455f0a)

这样我们就能在小号列表中看到我们的帐号了，如图：

![](https://p.pstatp.com/origin/ff8300028c56425842b8)

## 其他操作

修改账号信息，点击`Action`栏操作按钮（三点），点击`Eidt`修改该账号的信息，如图：

![](https://p.pstatp.com/origin/fee10002b75dc93850ed)

---

删除账号，点击`Action`栏操作按钮（三点），点击`Delete`删除该账号，如图：

![](https://p.pstatp.com/origin/138380000aa10b7bd7e55)

---

## 批量导入与导出

批量导入：

新建 Excel 文档，在第一个 sheet 里面以如图格式输入各账号的信息：

![](https://p.pstatp.com/origin/1000b00031706baec6606)

注意第一行必须为`name`、`cookie`、`comment_times`、`forward_times`和`like_times`，其中除了`name`和`cookie`，其余都填`0`。

最后点击`导入账号`按钮，选择 Excel 文件，Submit 提交即可，如图：

![](https://p.pstatp.com/origin/1384400011bf7d25de99d)

稍等两秒，可以看到 Excel 中的账号已经被成功导入，如图：

![](https://p.pstatp.com/origin/1376e0000ff78caf3f064)

---

批量导出：

点击右上角`Export`按钮即可导出所有账号：

![](https://p.pstatp.com/origin/1371d000340ed0b5dab09)

也可点击下拉按钮，手动选择导出当前页账号或者指定账号，如图：

![](https://p.pstatp.com/origin/1380300011d035b2799e0)

> 导出的 Excel 文档的格式和导入应该保持的格式不出意外是一致的，可以直接用于导入，因此导出功能也相当于备份。
