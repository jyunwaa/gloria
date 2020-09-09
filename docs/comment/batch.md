## 进一步简化

对于整个配置过程来说，是相当繁琐的，即使是到了最后一步，执行运行命令，比如输入：

```cmd
glory comment:run --task_id=1 --account_id=1
```

对这种运行命令，就算是复制粘贴，但如果你有二十个账号，也要打开二十个命令行窗口，粘贴二十次命令。

很明显，这与`Glory`解放双手的的宗旨是相悖的，我们使用批处理，只要你的任务已经配置完成，只需轻轻一点鼠标，就能让整个任务跑起来。

## 自定义批处理

我们首先打开`Glory`目录下的`comment.bat`文件（不一定非要叫`comment`这个名字，你可以改成其他名字，但是后缀一定要是`.bat`），然后右这个文件，点击`Edit with Notepad++`，如图：

![](https://p.pstatp.com/origin/1376c00017b29af16cfa3)

假设我们有15个账号，使用批处理开启评论任务，批处理内容如下（任务 ID 和账号 ID 根据自身实际情况做更改）：

```bat
@echo off
start cmd /k "glory comment:run --task_id=2 --account_id=1"
start cmd /k "glory comment:run --task_id=2 --account_id=2"
start cmd /k "glory comment:run --task_id=2 --account_id=3"
start cmd /k "glory comment:run --task_id=2 --account_id=4"
start cmd /k "glory comment:run --task_id=2 --account_id=5"
start cmd /k "glory comment:run --task_id=2 --account_id=6"
start cmd /k "glory comment:run --task_id=2 --account_id=7"
start cmd /k "glory comment:run --task_id=2 --account_id=8"
start cmd /k "glory comment:run --task_id=2 --account_id=9"
start cmd /k "glory comment:run --task_id=2 --account_id=10"
start cmd /k "glory comment:run --task_id=2 --account_id=11"
start cmd /k "glory comment:run --task_id=2 --account_id=12"
start cmd /k "glory comment:run --task_id=2 --account_id=13"
start cmd /k "glory comment:run --task_id=2 --account_id=14"
start cmd /k "glory comment:run --task_id=2 --account_id=15"
```

<!-- 上面这个批处理表示我们把十五个账号分批打开，每次打开五个，然后等待240秒，再打开下五个。 -->

批处理内容解释：

`@echo off`请忽略这一行。

`start cmd /k "命令"`表示打开一个命令行窗口，并执行该命令。

<!-- `choice /c YN /d Y /t 秒数`就理解为等待多少秒就行了，因为批处理没有提供睡眠功能，这是一个有效的替代办法。 -->

<!-- 具体的间隔时间结合自身实际设定，但是一定要保证上一批任务运行完，已经进入了等待下一轮的时间或者运行结束。 -->

我们在`comment.bat`的中保存好我们自定义的内容，只要任务命令没变，直接点击运行它就行了。但是如果任务命令发生了变化，直接查找替换修改批处理文件的内容。