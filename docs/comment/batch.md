## 进一步简化

对于整个配置过程来说，是相当繁琐的，即使是到了最后一步，执行运行命令，比如输入：

```cmd
glory comment:run --task_id=1 --account_id=1
```

对这种运行命令，就算是复制粘贴，但如果你有二十个账号，也要打开二十个命令行窗口，粘贴二十次命令。

很明显，这与`Glory`解放双手的的宗旨是相悖的，我们使用批处理，只要你的任务已经配置完成，只需轻轻一点鼠标，就能让整个任务跑起来。

## 自定义批处理

我们首先在`Glory`目录下创建一个`comment.bat`文件（不一定非要叫这个名字），然后编辑这个文件，如图：

![](https://p.pstatp.com/origin/ffe50002208fecb4cf91)

这里要阐释一个同步任务的概念，就是几个任务同时进行，不管是评论任务还是点赞或者转发，同时处于运行状态的任务都不能超过五个，屏幕上内容在不停更新，没有显示距离下一轮还有多少秒的任务就是处于运行状态的任务，如果同时处于运行状态的任务达到了6个或以上，该台电脑的IP就很容易被微博的服务器暂时封禁，通过这台电脑不能再评论，或者完全不能访问微博，不过这种封禁是临时的，一般十分钟左右会解禁。

但是我们在运行脚本时一定要避免这种情况发生，避免这个问题很简单，错开任务的运行时间就行了，我们的批处理一定也要解决这个问题，所以批处理会把所有任务分批打开，而不是全部同时开启。

假设我们有15个账号，使用批处理开启评论任务，批处理内容如下：

```bat
start cmd /k "glory comment:run --task_id=2 --account_id=1"
start cmd /k "glory comment:run --task_id=2 --account_id=2"
start cmd /k "glory comment:run --task_id=2 --account_id=3"
start cmd /k "glory comment:run --task_id=2 --account_id=4"
start cmd /k "glory comment:run --task_id=2 --account_id=5"

choice /c YN /d Y /t 240

start cmd /k "glory comment:run --task_id=2 --account_id=6"
start cmd /k "glory comment:run --task_id=2 --account_id=7"
start cmd /k "glory comment:run --task_id=2 --account_id=8"
start cmd /k "glory comment:run --task_id=2 --account_id=9"
start cmd /k "glory comment:run --task_id=2 --account_id=10"

choice /c YN /d Y /t 240

start cmd /k "glory comment:run --task_id=2 --account_id=11"
start cmd /k "glory comment:run --task_id=2 --account_id=12"
start cmd /k "glory comment:run --task_id=2 --account_id=13"
start cmd /k "glory comment:run --task_id=2 --account_id=14"
start cmd /k "glory comment:run --task_id=2 --account_id=15"
```

上面这个批处理表示我们把十五个账号分批打开，每次打开五个，然后等待240秒，再打开下五个。

具体说明一下这个批处理内容：

`start cmd /k "命令"`表示打开一个命令行窗口，并执行命令。

`choice /c YN /d Y /t 秒数`就理解为等待多少秒再执行后面的内容就行了，因为批处理没有提供睡眠功能，这是一个有效的替代办法。

我们在`comment.bat`的中保存好我们自定义的内容，只要任务命令没变，直接点击运行它就行了。但是如果任务命令发生了变化，还是要修改批处理文件的内容。