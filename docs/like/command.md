## 命令列表

与点赞相关的一共五个命令。

```cmd
like:add       the 添加点赞任务 command
like:alter     the 修改点赞任务 command
like:delete    the 删除点赞任务 command
like:run       the 运行点赞任务 command
like:view      the 查看点赞任务 command
```

## 查看命令帮助

我们只需在命令最后加上`--help`即可获得相关命令的帮助信息，比如：

参考`评论`>`命令`>`查看命令帮助`。

## like:add

> 该命令为添加点赞任务命令，支持七个参数：

```cmd
--weibo_id       必须，微博ID
--interval       可选，每点赞论间隔时间，单位：秒
--sleep          可选，每轮休息时间，单位：秒
--round          可选，轮数
--remark         可选，备注
```

## like:view

> 该命令为查看点赞任务命令，没有任何参数。

## like:delete

> 该命令为删除点赞任务命令，支持一个参数：

```cmd
--task_id       必须，任务ID
```

## like:alter

> 该命令为修改点赞任务命令，支持八个参数：

```cmd
--task_id        必须，任务ID
--weibo_id       可选，微博ID
--interval       可选，每条点赞间隔时间，单位：秒
--sleep          可选，每轮休息时间，单位：秒
--round          可选，轮数
--remark         可选，备注
```

## like:run

> 该命令为运行点赞任务命令，支持五个参数：

```cmd
--account_id     必须，账号ID
--task_id        必须，任务ID
--interval       可选，每条点赞间隔时间，单位：秒
--sleep          可选，每轮休息时间，单位：秒
--round          可选，轮数
```

本节相对简略，但是可以比照参考`评论`>`命令`。