## 命令列表

與評論相關的一共五個命令。

```cmd
comment:add       the 添加評論任務 command
comment:alter     the 修改評論任務 command
comment:delete    the 刪除評論任務 command
comment:run       the 運行評論任務 command
comment:view      the 查看評論任務 command
```

## 查看命令幫助

我們只需在命令最後加上`--help`即可獲得相關命令的幫助信息，比如：

```cmd
glory comment:add --help
```

執行該命令，如圖：

![](https://api.superbed.cn/static/images/2020/08/28/5f48988a160a154a679f99ea.jpg)

顯示出了該命令的所有參數，從上圖看出`comment:add`命令一共支持七個參數，前三個為必選參數，後面四個為可選參數，被`[`和`]`包圍的為可選參數，可以不填寫。

## comment:add

> 該命令為添加評論任務命令，支持七個參數：

```cmd
--weibo_id       必須，微博ID
--comment_id     必須，評論ID
--comment_sign   必須，評論標識
--interval       可選，每條評論間隔時間，單位：秒
--sleep          可選，每輪休息時間，單位：秒
--round          可選，輪數
--remark         可選，備註
```

添加一個任務，微博ID為`ABCDEFG`，評論ID為`1010101010101010`，評論標識為`232323`，如圖：

![](https://p.pstatp.com/origin/138220000f967118211a4)

也可帶上可選參數，備註為`無聊博`，如圖：

![](https://p.pstatp.com/origin/fef600029fba43f5a674)


## comment:view

> 該命令為查看評論任務命令。

執行該命令，查看所有評論任務，如圖：

![](https://p.pstatp.com/origin/ff7c000229d536345409)

## comment:delete

> 該命令為刪除評論任務命令，支持一個參數：

```cmd
--task_id       必須，任務ID
```

首先查看所有任務，記住需要刪除的任務的`TaskID`，然後執行該命令，如圖：

![](https://p.pstatp.com/origin/137d80000efc5df38cf2e)

## comment:alter

> 該命令為修改評論任務命令，支持八個參數：

```cmd
--task_id        必須，任務ID
--weibo_id       可選，微博ID
--comment_id     可選，評論ID
--comment_sign   可選，評論標識
--interval       可選，每條評論間隔時間，單位：秒
--sleep          可選，每輪休息時間，單位：秒
--round          可選，輪數
--remark         可選，備註
```

`--task_id`為必須，因為我們需要制定需要修改的任務，七個可修改項為可選參數，比如我們修改評論標識為`989898`和備註為`新歌博`，如圖：

![](https://p.pstatp.com/origin/137a30001d00320232436)

## comment:run

> 該命令為運行評論任務命令，支持五個參數：

```cmd
--account_id     必須，賬號ID
--task_id        必須，任務ID
--interval       可選，每條評論間隔時間，單位：秒
--sleep          可選，每輪休息時間，單位：秒
--round          可選，輪數
```

`--account_id`是賬號列表的賬號ID，也是賬號的序號，查看所有賬號時可以看到賬號的ID。

關於三個可選參數，這裡涉及到一個配置優先級問題，一共有四種，優先級由低到高分別是`系統配置`、`全局配置`、`任務配置`，`運行配置`。

運行配置是在運行時為單獨個別賬號指定的間隔時間、休息時間等，優先級最高。

任務配置是在添加任務時設定的各屬性，優先級次之。

全局配置是在`Glory/src/config/task.php`中所作的設定，優先級更低。

系統配置是默認的配置，不可修改，它的優先級最低，在以上三種配置都沒有的情況下生效。

運行一個評論任務，如圖：

![](https://p.pstatp.com/origin/1385700005a8a96def5d6)

測試賬號陷入頻繁狀態，不過這不重要，重要的是這麼做就可以讓刷評論的任務跑起來。