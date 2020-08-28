## 命令列表

与评论相关的一共五个命令。

```cmd
comment:add       the 添加评论任务 command
comment:alter     the 修改评论任务 command
comment:delete    the 删除评论任务 command
comment:run       the 运行评论任务 command
comment:view      the 查看评论任务 command
```

## 查看命令帮助

我们只需在命令最后加上`--help`即可获得相关命令的帮助信息，比如：

```cmd
glory comment:add --help
```

执行该命令，如图：

![](https://api.superbed.cn/static/images/2020/08/28/5f48988a160a154a679f99ea.jpg)

显示出了该命令的所有参数，从上图看出`comment:add`命令一共支持七个参数，前三个为必选参数，后面四个为可选参数，被`[`和`]`包围的为可选参数，可以不填写。

## comment:add

该命令为添加评论任务命令，支持七个参数：

```cmd
--weibo_id       必须，微博ID
--comment_id     必须，评论ID
--comment_sign   必须，评论标识
--interval       可选，每条评论间隔时间，单位：秒
--sleep          可选，每轮休息时间，单位：秒
--round          可选，轮数
--remark         可选，备注
```

添加一个任务，微博ID为`ABCDEFG`，评论ID为`1010101010101010`，评论标识为`232323`，如图：

![](https://p.pstatp.com/origin/138220000f967118211a4)

也可带上可选参数，备注为`无聊博`，如图：

![](https://p.pstatp.com/origin/fef600029fba43f5a674)

## comment:delete

## comment:alter

## comment:view

## comment:run

