## 進一步簡化

對於整個配置過程來說，是相當繁瑣的，即使是到了最後一步，執行運行命令，比如輸入：

```cmd
glory comment:run --task_id=1 --account_id=1
```

對這種運行命令，就算是複製粘貼，但如果你有二十個賬號，也要打開二十個命令行窗口，粘貼二十次命令。

很明顯，這與`Glory`解放雙手的的宗旨是相悖的，我們使用批處理，只要你的任務已經配置完成，只需輕輕一點鼠標，就能讓整個任務跑起來。

## 自定義批處理

我們首先在`Glory`目錄下創建一個`comment.bat`文件（不一定非要叫`comment`這個名字，但是後綴一定是`.bat`），然後編輯這個文件，如圖：

![](https://p.pstatp.com/origin/ffe50002208fecb4cf91)

這裡要闡釋一個同步任務的概念，就是幾個任務同時進行，不管是評論任務還是點贊或者轉發，同時處於運行狀態的任務都不能超過五個，屏幕上內容在不停更新，沒有顯示距離下一輪還有多少秒的任務就是處於運行狀態的任務，如果同時處於運行狀態的任務達到了6個或以上，該台電腦的IP就很容易被微博的服務器暫時封禁，通過這台電腦不能再評論，或者完全不能訪問微博，不過這種封禁是臨時的，一般十分鐘左右會解禁。

但是我們在運行腳本時一定要避免這種情況發生，避免這個問題很簡單，錯開任務的運行時間就行了，我們的批處理一定也要解決這個問題，所以批處理會把所有任務分批打開，而不是全部同時開啟。

假設我們有15個賬號，使用批處理開啟評論任務，批處理內容如下：

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

上面這個批處理表示我們把十五個賬號分批打開，每次打開五個，然後等待240秒，再打開下五個。

具體說明一下這個批處理內容：

`start cmd /k "命令"`表示打開一個命令行窗口，並執行命令。

`choice /c YN /d Y /t 秒數`就理解為等待多少秒就行了，因為批處理沒有提供睡眠功能，這是一個有效的替代辦法。

具體的間隔時間結合自身實際設定，但是一定要保證上一批任務運行完，已經進入了等待下一輪的時間或者運行結束。

我們在`comment.bat`的中保存好我們自定義的內容，只要任務命令沒變，直接點擊運行它就行了。但是如果任務命令發生了變化，還是要修改批處理文件的內容。